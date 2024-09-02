# OVERVIEW #

$${\color{green}Summary}$$

- In computer security, authentication is the process of verifying the digital identity of a communication sender, such as during the login process. Testing the authentication schema involves understanding how the authentication process works and using that knowledge to bypass the authentication mechanism.

- Many applications require authentication to access private information or perform tasks, but not all authentication methods provide adequate security. Errors often occur when authentication is bypassed simply by skipping the login page and directly accessing internal pages. Additionally, authentication measures can be bypassed by tampering with requests, such as modifying URL parameters, manipulating forms, or forging sessions.

>Trong bảo mật máy tính, xác thực là quá trình xác minh danh tính kỹ thuật số của người gửi thông tin, như quy trình đăng nhập. Kiểm tra cơ chế xác thực là hiểu cách thức hoạt động và sử dụng thông tin này để vượt qua cơ chế xác thực.
>
>Nhiều ứng dụng yêu cầu xác thực để truy cập thông tin riêng tư hoặc thực hiện tác vụ, nhưng không phải phương pháp xác thực nào cũng đảm bảo an toàn. Sai sót thường xuất hiện khi chỉ cần bỏ qua trang đăng nhập và truy cập trực tiếp vào trang nội bộ. Ngoài ra, có thể vượt qua biện pháp xác thực bằng cách giả mạo các yêu cầu, chỉnh sửa tham số URL, thao tác form, hoặc giả mạo phiên.

- Authentication-related problems can arise at various stages of the software development life cycle (SDLC), including:
  - Design Phase: Errors may include incorrectly defining protected application sections or not using strong encryption protocols for securing credential transmission.
  - Development Phase: Issues can involve improper input validation or failing to follow security best practices for the programming language.
  - Deployment Phase: Problems during installation and configuration can occur due to a lack of technical skills or insufficient documentation.
 
$${\color{green}Test \space Objectives}$$

Ensure that authentication is applied across all services that require it.

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$

**1.Direct Page Request (Forced Browsing):** Test if protected pages can be accessed directly without logging in by entering the URL in the browser’s address bar.

**2.Parameter Modification:** Modify parameter values (e.g., changing `authenticated=no` to `authenticated=yes`) to gain unauthorized access to protected areas.

**3.Session ID Prediction:** Predict or guess session ID values if they are easily predictable (e.g., increasing linearly) to gain access to authenticated sessions.

**4.SQL Injection (HTML Form Authentication):** Use SQL Injection to bypass login forms by injecting malicious code into input fields.

$${\color{green}Gray-Box \space Testing}$$

Review the source code to find vulnerabilities in the authentication process, such as unsafe use of functions like `unserialize()`, allowing bypassing of authentication controls.
