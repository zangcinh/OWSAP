# OVERALL #

$${\color{green}Summary}$$

 Understanding the structure of an application is crucial before starting security testing. Without this understanding, thorough testing is challenging.

**How to test**

 In black-box testing, it is often impractical to test the entire codebase. Even if testers could view the code paths, testing every possible path would be very time-consuming. Instead, documenting the paths discovered and tested can be a practical approach.

 $${\color{green}Methods \space to \space Approach \space Testing \space and \space Measure \space Code \space Coverage}$$

**1. Path Testing**

- Description: Test each possible path through the application. This includes combinatorial testing and boundary value analysis for each decision path.
- Advantages: Provides thorough coverage of the application.
- Disadvantages: The number of testable paths grows exponentially with each decision branch, making it complex and time-consuming.

**2. Data Flow (or Taint Analysis)**

- Description: Focuses on how data is assigned and flows through the application. It maps the flow, transformation, and use of data based on external interactions (usually from users).
- Advantages: Helps in understanding how data is manipulated and used across the application.
- Disadvantages: May not cover all possible paths or edge cases.

**3. Race Testing**

- Description: Tests the application under conditions of concurrent data manipulation by multiple instances.
- Advantages: Identifies issues related to concurrency and data integrity.
- Disadvantages: Complex to set up and may not be feasible for all applications.

# CODE REVIEW #

 Ensuring sufficient code coverage for the application owner is much easier with gray-box and white-box approaches to testing. Information requested and provided to the tester will ensure that minimum code coverage requirements are met.

 $${\color{green}Modern \space Tools \space and \space Methods}$$

 **Dynamic Application Security Testing (DAST) Tools**: Many modern DAST tools facilitate the use of a web server agent or can be paired with a third-party agent to monitor web application coverage specifics.

 - Web Server Agents: Monitor requests and responses between the application and users, providing insights into covered areas.
- Third-Party Agents: Can be integrated to collect more detailed information and analyze security vulnerabilities that basic DAST tools might miss.
 
# AUTOMATIC SPIDERING #

Automatic spidering is a technique used to automatically discover new resources (such as URLs) on a website. It works by starting with a set of initial URLs (called seeds) and systematically exploring the links found on each page. This process helps in identifying the structure and content of the site that might not be immediately visible. One popular tool for this is the Zed Attack Proxy (ZAP), which offers various spidering options.

>Spidering tự động là một kỹ thuật được sử dụng để tự động phát hiện các tài nguyên mới (như URL) trên một trang web. Công cụ bắt đầu với một danh sách các URL ban đầu (được gọi là seeds) và hệ thống sẽ khám phá các liên kết tìm thấy trên mỗi trang. Quá trình này giúp xác định cấu trúc và nội dung của trang web mà có thể không dễ dàng nhìn thấy ngay lập tức. Một trong những công cụ phổ biến để thực hiện điều này là Zed Attack Proxy (ZAP), với nhiều tùy chọn spidering khác nhau.

![image](https://github.com/user-attachments/assets/9a13774e-7026-4718-9fb9-f7639fbdf23d)


