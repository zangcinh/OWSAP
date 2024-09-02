# OVERALL #

$${\color{green}Summary}$$

Many modern web applications use popular open-source or commercial software that can be installed on servers with minimal configuration. Additionally, many hardware devices like routers and database servers offer web-based administrative interfaces. Often, these applications are not configured properly, and the default credentials provided for initial setup remain unchanged. These default credentials are well known to both penetration testers and malicious attackers, who can use them to gain unauthorized access.

>Nhiều ứng dụng web hiện nay sử dụng phần mềm mã nguồn mở hoặc thương mại, dễ dàng cài đặt trên máy chủ nhưng không được cấu hình đúng cách, khiến thông tin đăng nhập mặc định không bị thay đổi.

$${\color{green}Common \space causes}$$

- Inexperienced IT personnel unaware of the importance of changing default passwords.
- Developers leaving backdoors for easy access and forgetting to remove them.
- Applications with non-removable default accounts.
- Applications not forcing users to change default credentials after the first login.

$${\color{green}Test \space Objectives:}$$

- Enumerate applications for default credentials and check if they still exist.
- Review new user accounts for default or predictable passwords.

# HOW TO TEST #

**1.Testing for Default Credentials of Common Applications:**

- Identify application interfaces, such as router admin pages, and check known usernames/passwords.
- Use known usernames like “admin”, “root”, and try common passwords like “password”, “12345”.
- Check for verbose error messages that may reveal valid usernames.

**2.Testing for Default Passwords of New Accounts:**

- Examine the registration page to determine username/password patterns.
- Create multiple new accounts to identify if the system generates predictable passwords.
- Try blank passwords or use the username as the password.

**3.Gray-Box Testing:**

- Speak with IT personnel to learn about administrative access practices.
- Check if default credentials are changed and if default accounts are disabled.
- Review the codebase and configuration files for hardcoded usernames and passwords.
