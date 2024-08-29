# OVERALL #

$${\color{green}Summary}$$

- Application entry points are the starting points or URLs through which users interact with a web application. Finding these entry points is crucial for security testing, as they allow you to explore and analyze different parts of the application. Here are some methods to identify these entry points

$${\color{green}Test \sapce Objectives}$$

- Identify Possible Entry Points + Identify Injection Points

# HOW TO TEST #

**1. Understand Application Interaction**

- Analyze HTTP Requests: While navigating through the application, pay attention to all HTTP requests, including GET and POST requests, as well as any parameters and form fields sent to the application.
- Focus on Request Methods:
  - `GET`: Typically used to retrieve data from the application. Parameters are usually in the URL (after the ?).
  - `POST`: Typically used to send data to the application. Parameters are included in the body of the request.
    
**2. Use Supporting Tools**
    
- Proxy Interceptors: Use tools like Burp Suite or OWASP ZAP to intercept and monitor requests and responses between you and the application. This helps in viewing the full content of requests and responses, including hidden parameters that might not be visible otherwise.
- Spreadsheets: Record all important information such as the requested page (including proxy request numbers for future reference), interesting parameters, request type (GET, POST, etc.), whether access is authenticated or not, whether TLS is used, and any other relevant notes.
  
**3. Check the Requests**

- Identify GET and POST Usage:
  - GET: Identify parameters in the URL (query string).
  - POST: Identify all parameters in the request body, including hidden parameters.
- Hidden Parameters: In POST requests, hidden form fields often contain sensitive information and can affect the application's response if altered.
- Query String Parameters: In GET requests, check for parameters in the query string, especially when multiple parameters are separated by & or other special characters.
- Custom Headers: Pay attention to any custom or additional headers (e.g., debug: false) that may provide extra information about the application's configuration.

**4. Check the Responses**
- Cookies: Identify where new cookies are set (via Set-Cookie headers), modified, or deleted.
- Redirects: Look for any redirects (HTTP status code 3xx) and error status codes like 400 (Bad Request), 403 (Forbidden), or 500 (Internal Server Error).
- Interesting Headers: Note any interesting HTTP headers that could provide insights into server configuration or how the application handles requests.

# BLACK BOX TESTING #

$${\color{green}Overview}$$

Black-box testing involves evaluating the functionality of an application without knowledge of its internal code or logic. The focus is on testing the application based on its inputs and outputs. When testing for application entry points, you are identifying points where inputs are accepted by the application, which could potentially be exploited.

>Kiểm thử hộp đen liên quan đến việc đánh giá chức năng của một ứng dụng mà không cần biết mã nguồn hoặc logic nội bộ của nó. Mục tiêu là kiểm tra ứng dụng dựa trên các đầu vào và đầu ra. Khi kiểm tra các điểm vào của ứng dụng, bạn đang xác định các điểm mà ứng dụng chấp nhận đầu vào, những điểm này có thể bị khai thác.

$${\color{green}Step \space for \space Testing}$$

**1.Identify Parameters**: Note all parameters in both GET and POST requests
**2.Analyze Request and Response**:  Check how the parameters affect the application. For instance, changing a parameter might result in different application behavior.
**3.Custom Headers**: Pay attention to custom headers and cookies, as they may influence application behavior or contain sensitive data.

$${\color{green}Example \space 1: \space GET \space Request \space for \space Purchasing \space an \space Item}$$

![image](https://github.com/user-attachments/assets/04344322-237c-4bd9-b49e-eb4003878f6d)

- Parameters to Note:
  - CUSTOMERID=100
  - ITEM=z101a
  - PRICE=62.50
  - IP=x.x.x.x
  - Cookie: Encoded parameter or used for session state

$${\color{green}Example \space 2: \space POST \space Request \space for \space Logging \space In}$$

![image](https://github.com/user-attachments/assets/67dabd78-2d8b-4309-8b91-e537d653564b)

- Parameters to Note:
  - user=admin
  - pass=pass123
  - debug=true
  - fromtrustIP=true
  - Custom HTTP Header: CustomCookie

$${\color{green}Key \space Points \space to \space Observe}$$

**1.Parameters in GET Requests:**

- Parameters are included in the URL query string.
  - Example: CUSTOMERID, ITEM, PRICE, IP.
  - 
**2.Parameters in POST Requests:**

- Parameters are included in the body of the request.
  - Example: user, pass, debug, fromtrustIP.
  - Custom HTTP Headers: Observe any custom headers like CustomCookie.
  - 
**3.Cookies:**

- Cookies might carry session information or encoded parameters.
- Example: SESSIONID.

# GRAY-BOX TESTING #

$${\color{green}Overview}$$

Gray-box testing is a methodology that combines aspects of both black-box and white-box testing. It allows testers to evaluate the application from an external user perspective (as in black-box testing) while also leveraging some knowledge of the internal structure or operations of the application, which may be obtained from documentation or meetings with developers.

>Kiểm thử hộp xám là phương pháp kết hợp giữa kiểm thử hộp đen và kiểm thử hộp trắng. Nó cho phép kiểm tra ứng dụng từ góc độ của người dùng bên ngoài (như trong kiểm thử hộp đen), nhưng cũng sử dụng thông tin về cấu trúc hoặc hoạt động nội bộ của ứng dụng mà có thể thu thập được từ tài liệu hoặc từ các cuộc họp với các nhà phát triển.

$${\color{green}Steps \space \space for \space Testing \space Application \space Entry \space Points \space in\space Gray-Box \space Testing}$$

**1.Apply Black-Box Testing Techniques:**

- Perform the steps similar to black-box testing: identify and document application entry points through HTTP request analysis, parameters, and headers.

**2.Investigate External Data Sources:**

- External Sources: Determine if the application receives data from external sources such as SNMP traps, syslog messages, SMTP, or SOAP messages from other servers.
- Developer Meetings: Arrange meetings with developers to understand which functions accept or expect user input and how these inputs are formatted.

**3.Specific Example:**

- SOAP Requests: If the application accepts SOAP requests, developers could help you understand how to formulate a valid SOAP request that the application will accept and where the web service is located (if the web service or any other function hasn't already been identified during black-box testing).
- 
>Simple Object Access Protocol (SOAP) là một giao thức mạng để trao đổi dữ liệu có cấu trúc giữa các nút. Giao thức này sử dụng định dạng XML để truyền tải thông điệp. Giao thức này hoạt động trên các giao thức lớp ứng dụng như HTTP và SMTP để ghi chú và truyền tải. SOAP cho phép các quy trình giao tiếp trên khắp các nền tảng, ngôn ngữ và hệ điều hành, vì các giao thức như HTTP đã được cài đặt trên tất cả các nền tảng

