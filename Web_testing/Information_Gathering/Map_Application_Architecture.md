# OVERALL #

$${\color{green}Summary}$$

Understanding the architecture of web applications is crucial for identifying vulnerabilities and managing configurations effectively. This involves mapping out the different components and how they interact, from simple setups to complex infrastructures with multiple servers and security layers.

$${\color{green}Objectives}$$

Create a detailed map of the application architecture based on research and testing.

$${\color{green}How \space to \space test}$$

**1.Mapping the Architecture:**

- Simple Setups: Identify components like a single server handling both the application and authentication.
- Complex Setups: Recognize multiple components such as reverse proxies, front-end web servers, application servers, and database servers. Analyze network zones and security layers.

>- Thiết Lập Đơn Giản: Xác định các thành phần như một máy chủ duy nhất xử lý cả ứng dụng và xác thực.
>- Thiết Lập Phức Tạp: Nhận diện các thành phần khác nhau như reverse proxy, máy chủ web phía trước, máy chủ ứng dụng, và máy chủ cơ sở dữ liệu. Phân tích các khu vực mạng và lớp bảo mật.

**2.Information Gathering:**

- Firewall Detection: Determine if a firewall is protecting the web server through network scans and response analysis.
- Reverse Proxy Detection: Look for signs of a reverse proxy, such as changes in error messages or discrepancies in server responses.
- Network Load Balancer Detection: Identify if load balancing is in use by analyzing multiple requests and server responses for variations.
- Application Web Server Detection: Check if responses and cookies suggest an application server, such as JSESSIONID for J2EE servers.
- Authentication Backend Detection: Determine the presence of authentication backends like LDAP or databases through application behavior and responses.

>- Phát Hiện Tường Lửa: Xác định xem một tường lửa có bảo vệ máy chủ web hay không thông qua quét mạng và phân tích phản hồi.
>- Phát Hiện Reverse Proxy: Tìm dấu hiệu của reverse proxy, chẳng hạn như thay đổi trong thông báo lỗi hoặc sự khác biệt trong phản hồi của máy chủ.
>- Phát Hiện Cân Bằng Tải Mạng: Xác định nếu có cân bằng tải bằng cách phân tích nhiều yêu cầu và phản hồi của máy chủ để phát hiện sự phân phối tải.
>- Phát Hiện Máy Chủ Ứng Dụng: Kiểm tra các tiêu đề phản hồi và cookie để tìm dấu hiệu của máy chủ ứng dụng, chẳng hạn như JSESSIONID cho các máy chủ J2EE.
>- Phát Hiện Hệ Thống Xác Thực: Xác định sự hiện diện của các hệ thống xác thực như LDAP hoặc cơ sở dữ liệu qua hành vi và phản hồi của ứng dụng.

- **3.Examples:**

- Firewall: Use network scans to check for firewall presence and configuration.
- Reverse Proxy: Look for changes in error messages or discrepancies in server responses.
- Load Balancer: Compare responses from multiple requests to detect load balancing.
- Application Server: Observe response headers and cookies for application server indicators.
- Database Backend: Look for dynamic content generation or vulnerability indicators like SQL injection.
