# OVERALL #

$${\color{green}Summary}$$	

- Importance of Proper Configuration: Accurate configuration of application architecture components is crucial to avoid security vulnerabilities.

- Thorough Configuration Review: Default configurations often include unnecessary features, examples, documentation, or test pages, which should be removed to prevent exploitation.

- Remove Unnecessary Components: Ensure that default and unnecessary files are deleted before deployment to avoid potential security issues.

$${\color{green}Test \space Objective}$$	

- Ensure default files and known files are removed.
- Validate that no debugging code or extensions are present in the production environment.
- Review the logging mechanisms implemented for the application.

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$	

**1.Sample and Known Files and Directories**

- Default installations of web and application servers often include sample files and directories for testing purposes.
- These default files may be vulnerable and should be removed. Examples include:
  - CVE-1999-0449: Denial of Service in IIS due to the Exair sample site.
  - CAN-2002-1744: Directory traversal vulnerability in CodeBrws.asp in IIS 5.0.
  - CAN-2002-1630: Use of sendmail.jsp in Oracle 9iAS.
  - CAN-2003-1172: Directory traversal in the view-source sample in Apache Cocoon.
- CGI scanners can identify these files, but a full review is necessary to confirm their relevance.

>- Các cài đặt mặc định của máy chủ web và ứng dụng thường bao gồm các tệp mẫu và thư mục dành cho việc kiểm tra hoặc phát triển.
>- Những tệp này có thể gây ra lỗ hổng bảo mật nếu không bị loại bỏ. Ví dụ:
>  - CVE-1999-0449: Tấn công từ chối dịch vụ trên IIS do trang mẫu Exair.
>  - CAN-2002-1744: Lỗ hổng duyệt thư mục trong CodeBrws.asp trên IIS 5.0.
>  - CAN-2002-1630: Sử dụng sendmail.jsp trong Oracle 9iAS.
>  - CAN-2003-1172: Lỗ hổng duyệt thư mục trong mẫu view-source của Apache Cocoon.
>- Các công cụ quét CGI có thể giúp xác định các tệp này, nhưng cần thực hiện kiểm tra toàn diện để xác nhận tính liên quan của chúng.

**2.Comment Review**

- Programmers often leave comments in HTML or source code, which can unintentionally expose sensitive information.
- Conduct a review of comments in static and dynamic content by analyzing web server output and searching for comments in HTML and code.

**3.System Configuration:**

- Use tools and checklists to assess system configuration against security baselines and benchmarks:
  - [CIS-CAT](https://learn.cisecurity.org/cis-cat-lite) Lite: Evaluates compliance with CIS standards.
  - [Microsoft’s Attack Surface Analyzer](https://github.com/microsoft/AttackSurfaceAnalyzer): Analyzes the attack surface of Microsoft applications.
  - [NIST’s National Checklist Program](https://ncp.nist.gov/repository): Provides detailed checklists for various systems.

$${\color{green}Gray-Box \space Testing: \space Configuration \space Review}$$	

**1.Importance**: Proper configuration of web and application servers is crucial for security. Incorrect configurations can open up security vulnerabilities.

**2.Guidelines:**

- Enable Only Needed Modules: Activate only the necessary modules or extensions for the application to reduce the attack surface.
- Custom Error Pages: Use custom pages for server errors (like 40x, 50x) to avoid leaking information through default error messages.
- Minimize Privileges: Ensure the server software runs with minimal privileges to limit the impact of potential vulnerabilities.
- Logging: Ensure the server logs both legitimate access and errors properly.
- Handle Overloads: Configure the server to manage overloads and prevent Denial of Service (DoS) attacks.
- Secure Configuration Files: Avoid granting non-administrative identities access to critical configuration files. Encrypt sensitive information and limit access to configuration files.

$${\color{green}Logging}$$

**1. Importance**: Logging is crucial for detecting application flaws and attacks. Proper log management helps monitor and analyze issues.

**2.Key Considerations:**

- Sensitive Information: Logs should not contain sensitive data like passwords or personal information.
- Log Storage: Store logs in a separate location to prevent loss if the server is compromised and to facilitate log analysis.
- Log Rotation: Ensure logs are rotated to prevent disk space issues. Rotated logs should be compressed and permissions adjusted as needed.
- Access Control: Protect log access to prevent unauthorized viewing and ensure logs are reviewed for attack detection.

$${\color{green}Sensitive \space Information \space in \space Logs}$$

Avoid logging sensitive information such as source code, session IDs, passwords, and financial data. This helps prevent data leaks and compliance issues.

$${\color{green}Log \space Testing}$$

Verify that logs are stored and rotated properly, and assess if logging can be used to detect suspicious activities, such as error messages indicating possible attacks.

