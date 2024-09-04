# OVERALL #

$${\color{green}Summary}$$

- Session Puzzling (Session Variable Overloading) is an application-level vulnerability that allows attackers to perform various malicious actions, such as:
  - Bypassing authentication mechanisms and impersonating legitimate users.
  - Elevating privileges of a malicious user account in otherwise secure environments.
  - Skipping qualifying phases in multi-phase processes, even with code-level restrictions.
  - Manipulating server-side values in unpredictable ways.
  - Executing attacks in locations previously considered secure.
- This vulnerability occurs when an application uses the same session variable for multiple purposes, allowing attackers to set a variable in one context and exploit it in another. For example, an attacker might access a public entry point like a password recovery page that sets a session variable similar to one used in authentication, then access privileged areas.

>- Session Puzzling (quá tải biến phiên) là lỗ hổng ở mức ứng dụng cho phép kẻ tấn công thực hiện các hành động nguy hiểm như:
>    - Bypass cơ chế xác thực, mạo danh người dùng hợp lệ.
>    - Tăng quyền truy cập của tài khoản độc hại trong môi trường tưởng chừng như an toàn.
>    - Bỏ qua các giai đoạn trong quy trình nhiều bước, dù có kiểm tra mã.
>    - Thao túng giá trị server-side theo cách không thể dự đoán hay phát hiện.
>    - Thực hiện tấn công tại các vị trí trước đây được coi là an toàn.
>- Lỗ hổng này xảy ra khi ứng dụng dùng cùng một biến phiên cho nhiều mục đích khác nhau, kẻ tấn công có thể thiết lập giá trị biến trong một ngữ cảnh và sử dụng nó trong ngữ cảnh khác để lợi dụng. Ví dụ, kẻ tấn công có thể dùng trang khôi phục mật khẩu để tạo biến phiên tương tự như của phiên xác thực thành công và truy cập vào các trang đặc quyền.

$${\color{green}Test \space Objectives}$$

- Identify all session variables.
- Disrupt the logical flow of session generation.

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$

- Testers try to find and exploit session variables by accessing different entry and exit points of the application.
- This method is challenging and requires multiple attempts since each access sequence might give different results.

**Example:**
- In a password reset function, the app asks for information like an email, then stores it in a session variable. Attackers can use this to access private data without logging in.

$${\color{green}Gray-Box \space Testing}$$

- The most effective way to find these vulnerabilities is by reviewing the source code, which reveals how session variables are set and used.
