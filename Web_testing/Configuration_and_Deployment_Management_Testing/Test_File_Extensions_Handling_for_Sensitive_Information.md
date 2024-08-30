# OVERALL #

$${\color{green}Summary}$$	

File extensions in web servers help identify the technologies and plugins in use, and their handling can reveal sensitive information if misconfigured.

$${\color{green}Test \space Objectives}$$	

- Identify Sensitive Extensions: Test for extensions that could expose sensitive data (e.g., scripts, credentials).
- Validate Rules: Ensure that framework rules are enforced to prevent bypasses.

# HOW TO TEST #

$${\color{green}Forced \space Browsing}$$	

**1.Summary:**

Forced browsing involves submitting requests with various file extensions to test how they are handled by the server. The goal is to determine how directories and files, particularly those allowing script execution, are managed and to identify potential vulnerabilities.

**2.Test Objectives:**

- Verify File Handling: Submit requests with different file extensions and check how they are processed, especially in directories that allow script execution.
- Check Load-Balancing Configuration: Assess all web servers in a load-balanced architecture, as there might be minor configuration differences between them.
- Identify Sensitive Files: Ensure that certain file extensions, which should not be served by the web server are properly handled. Also, verify that files with extensions that might contain sensitive information are either properly managed or not served.

- **Example**

- If a tester discovers a file named `connection.inc` and accesses it directly, they might see contents like:

- ![image](https://github.com/user-attachments/assets/221ed80f-ff24-43f3-8936-3cebc6c3ac60)

- -> This can reveal the existence of a MySQL database and weak credentials used by the web application.

- **3.File Extensions to Avoid Serving:**

- Sensitive Information: `.asa`, `.inc`, `config`
- Potentially Sensitive: `.zip`, `.tar`, `.gz`, `.java`, `.txt`, `.pdf`, `.docx`, `.bak`, `.old`

**4.Testing Techniques**

- Vulnerability Scanners
- Spidering and Mirroring Tools
- Manual Inspection: To overcome limitations of automated tools
- Search Engines: To find forgotten or unreferenced files.

$${\color{green}File \space Upload}$$	

Windows 8.3 legacy file handling can sometimes be used to defeat file upload filters.

**Example**

1.`file.phtml` gets processed as PHP code.
2.`FILE~1.PHT` is served, but not processed by the PHP ISAPI handler.
3.`shell.phPWND` can be uploaded.
4.`SHELL~1.PHP` will be expanded and returned by the OS shell, then processed by the PHP ISAPI handler.

$${\color{green}Gray-Box \space Testing}$$

**1.Objective:** Assess how web and application servers handle various file extensions within the web application architecture.

>Đánh giá cách các máy chủ web và máy chủ ứng dụng xử lý các phần mở rộng tệp khác nhau trong kiến trúc ứng dụng web.

**2.Scope:**

- Configuration Review: Check the configuration of web and application servers to understand how they are set up to handle different file extensions.
- Load-Balancing Impact: Evaluate if a load-balanced, heterogeneous infrastructure (e.g., combining different types of servers) leads to inconsistent behavior or vulnerabilities.

>- Xem Xét Cấu Hình: Kiểm tra cấu hình của các máy chủ web và ứng dụng để hiểu cách chúng xử lý các phần mở rộng tệp khác nhau.
>- Tác Động Của Cân Bằng Tải: Đánh giá xem cơ sở hạ tầng cân bằng tải, đa dạng (ví dụ: kết hợp các loại máy chủ khác nhau) có dẫn đến hành vi không nhất quán hoặc lỗ hổng bảo mật không.

$${\color{green}Tools}$$

- [Nesus](https://www.tenable.com/products/nessus)
- [Nikto](https://github.com/sullo/nikto)
- [wget](https://www.gnu.org/software/wget/)
- [curl](https://curl.se/)
- web mirroring tools
