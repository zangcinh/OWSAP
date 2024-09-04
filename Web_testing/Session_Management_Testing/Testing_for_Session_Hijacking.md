# OVERALL #

$${\color{green}Summary}$$

- Attackers can steal user session cookies and impersonate them. This is known as session hijacking.
- Cookies can be exposed over HTTP, especially if not marked with the Secure attribute, allowing attackers to intercept them.

$${\color{green}Key \space Points}$$

- Secure Attribute: Cookies should be marked as Secure to ensure they are sent only over HTTPS, protecting them from being exposed over HTTP.
- HSTS (HTTP Strict Transport Security): Enforces HTTPS use, preventing cookies from being sent over HTTP. Full HSTS adoption protects the main domain and all its sub-domains

$${\color{green}Example \space Attack \space Scenario}$$

- An attacker manipulates a response to trigger a request to an unsecured site or sub-domain, causing the browser to send cookies in clear text over HTTP, exposing them to the attacker.

$${\color{green}Test \space Objectives}$$

- Identify cookies vulnerable to hijacking.
- Attempt to hijack these cookies to assess security risks.

# HOW TO TEST #

**1.Đăng Nhập Như Nạn Nhân:** Đăng nhập vào trang web và truy cập một trang yêu cầu xác thực bảo mật.

**2.Chuẩn Bị Cookie:**

- Xóa các cookie có thuộc tính Secure (nếu không có HSTS) hoặc có thuộc tính Secure/không có thuộc tính Domain (nếu có HSTS một phần).
- Lưu lại trạng thái cookie.

**3.Kích Hoạt Chức Năng Bảo Mật:** Thực hiện chức năng bảo mật và kiểm tra xem nó có thành công không. Nếu có, có thể trang web bị lỗ hổng.

**4.Thử Tấn Công:**

- Xóa cookie.
- Đăng nhập như kẻ tấn công và truy cập trang tương tự.
- Thêm các cookie đã lưu vào cookie jar.
- Kích hoạt lại chức năng bảo mật.

**5.Xác Minh Kết Quả:**

- Xóa cookie, đăng nhập lại như nạn nhân.
- Kiểm tra xem chức năng bảo mật có hoạt động trong tài khoản của nạn nhân không. Nếu có, tấn công thành công; nếu không, trang web an toàn.

=> Quá trình này giúp bạn xác định liệu các cookie có thể bị chiếm đoạt và sử dụng để truy cập vào tài khoản của người khác hay không.







