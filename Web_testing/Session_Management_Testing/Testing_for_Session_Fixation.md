# OVERVIEW #

$${\color{green}Summary}$$

Session fixation vulnerabilities occur when session cookies retain the same value before and after user authentication. This issue arises when cookies are used to store state information, such as items in a shopping cart, before login. An attacker can exploit this by setting a session cookie in the victim’s browser before login. If the victim logs in without the session cookie being refreshed, the attacker can use these cookies to impersonate the victim.

> Lỗ hổng session fixation xảy ra khi giá trị của cookies phiên (session cookies) không thay đổi trước và sau khi người dùng đăng nhập. Vấn đề này thường xảy ra khi cookies được sử dụng để lưu trữ thông tin trạng thái, chẳng hạn như các mặt hàng trong giỏ hàng trước khi đăng nhập. Kẻ tấn công có thể khai thác lỗ hổng này bằng cách đặt một cookie phiên trong trình duyệt của nạn nhân trước khi đăng nhập. Nếu nạn nhân đăng nhập mà không làm mới cookie phiên, kẻ tấn công có thể sử dụng cookie này để giả mạo nạn nhân.

$${\color{green}Test \space Objectives}$$
- Analyze the authentication mechanism and its flow.
- Force cookies and assess the impact.

# HOW TO TEST #

$${\color{green}Initial \space Check}$$

- Identify whether the application renews the session cookie after the user logs in.
- Steps:
  - Send a GET request to the target site (e.g., `GET / HTTP/1.1`).
  - Observe the server's response. For example:
>HTTP/1.1 200 OK
>Set-Cookie: JSESSIONID=0000d8eyYq3L0z2fgq10m4v-rt4:-1; Path=/; secure
  - The `JSESSIONID` cookie is set before the user logs in
- `Authentication Check`: Log in to the application and observe the server’s response again. If no new cookie is issued after login, it means the application retains the old session cookie, which poses a session fixation risk.

$${\color{green}Forced \space Cookies \space Testing \space Strategy}$$

- Simulate an attack scenario by reusing the old session cookie to access another user's account.
- Detailed Steps:
  - Reach the Login Page: Access the login page of the website and save the session cookies set before logging in.
  - Log in as the Victim: After logging in, navigate to a secure page that requires authentication.
  - Reuse the Old Cookie: Clear all current cookies, set the saved cookies from before login, and try to trigger the secure function.
  - Observe the Results: If the secure function executes successfully without requiring re-authentication, the session fixation vulnerability exists.
  - Log in Again as the Attacker: Repeat the test with the attacker’s account to further verify the ability to hijack the victim’s session.
- Use Two Browsers or Separate Machines: This minimizes false positives if the web application uses device fingerprinting to verify access attempts using a specific cookie.


