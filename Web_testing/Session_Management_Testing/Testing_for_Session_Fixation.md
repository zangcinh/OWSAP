# OVERVIEW #

$${\color{green}Summary}$$

Session fixation vulnerabilities occur when session cookies retain the same value before and after user authentication. This issue arises when cookies are used to store state information, such as items in a shopping cart, before login. An attacker can exploit this by setting a session cookie in the victim’s browser before login. If the victim logs in without the session cookie being refreshed, the attacker can use these cookies to impersonate the victim.

> Lỗ hổng session fixation xảy ra khi giá trị của cookies phiên (session cookies) không thay đổi trước và sau khi người dùng đăng nhập. Vấn đề này thường xảy ra khi cookies được sử dụng để lưu trữ thông tin trạng thái, chẳng hạn như các mặt hàng trong giỏ hàng trước khi đăng nhập. Kẻ tấn công có thể khai thác lỗ hổng này bằng cách đặt một cookie phiên trong trình duyệt của nạn nhân trước khi đăng nhập. Nếu nạn nhân đăng nhập mà không làm mới cookie phiên, kẻ tấn công có thể sử dụng cookie này để giả mạo nạn nhân.

$${\color{green}Test \space Objectives}$$
- Analyze the authentication mechanism and its flow.
- Force cookies and assess the impact.
