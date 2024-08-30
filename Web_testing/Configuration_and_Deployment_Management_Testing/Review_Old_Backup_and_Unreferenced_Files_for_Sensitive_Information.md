# OVERALL #

$${\color{green}Summary}$$

Old and unreferenced backup files can contain sensitive information and pose security risks. These files might include old versions, automatic or manual backups, and snapshots, potentially revealing source code, administrative interfaces, or credentials.

$${\color{green}Key \space Points}$$

- Backup Files and Snapshots: Can automatically or manually be created and might contain sensitive information.
- File Extensions and Execution: Backup files might be served as plain text instead of executed, exposing source code.
- Security Risks: Can expose business logic, source code, or credentials if accessed improperly.

$${\color{green}Threat}$$

**1.Sensitive Information Disclosure**: Unreferenced files might contain sensitive data like credentials or configuration details that could facilitate targeted attacks.

**2.Powerful Functionality Exposure**: Unreferenced pages may include administrative or powerful features that can be exploited if discovered.

**3.Outdated Vulnerabilities:** Backup files may contain old vulnerabilities that have been fixed in newer versions.

**4.Source Code Exposure:** Backup files can reveal source code for server-side scripts, potentially exposing vulnerabilities.

**5.Complete Application Enumeration:** Backup archives might include all application files, exposing source code and unreferenced pages.

**6.Filename Modifications:** Files with modified names (e.g., "Copy of") may still contain outdated or incorrect logic that can lead to errors or information leakage.

**7.Sensitive Log Information:** Log files might reveal sensitive data such as session IDs and URLs that could disclose additional content.

**8.File System Snapshots:** Snapshots may contain old code with vulnerabilities that have been patched in newer versions.

# HOW TO TEST #

**1.Black-Box Testing**

$${\color{green}Inference \space from \space the \space Naming \space Scheme \space Used \space for \space Published \space Content}$$

- Enumerate Pages and Functionality: Use a browser or an application spidering tool to identify all pages and functionalities.
- Naming Conventions: Applications often use recognizable naming conventions. For example, if you find a page named viewuser.asp, look for related pages like 1edituser.asp`, `adduser.asp`, or `deleteuser.asp.` Similarly, if you find a directory `/app/user`, check for related directories such as `/app/admin` or `app/manager`

$${\color{green}Other \space Clues in \space Published \space Content}$$

- Programmers' Comments: Comments in HTML or JavaScript source code might reference hidden content. For example:

  ![image](https://github.com/user-attachments/assets/0ff5a22e-024b-4b4b-aeb2-0cefe7d37107)

- JavaScript Links: JavaScript code may include links to pages or functionality visible only under certain conditions. For example:

  ![image](https://github.com/user-attachments/assets/da547c84-2041-422f-b409-03e8e9eba38f)

- Hidden Forms: HTML forms may exist but be hidden by disabling form elements. For example:

  ![image](https://github.com/user-attachments/assets/9023acf1-2e2c-43f1-a0af-9fff3b02fa05)

- Robots.txt File: This file can reveal unreferenced directories by listing paths that are disallowed for web robots

$${\color{green}Blind \space Guessing}$$

- Basic Attack: Use a script to run a list of common filenames through a request engine to guess files and directories. The provided script uses `netcat` to perform this task and outputs response codes to identify valid resources or errors.
- Advanced Attack:
  - File Extensions: Identify common file extensions used by the application and append these to a wordlist to guess filenames (e.g., .jsp, .aspx, .html).
  - Custom Wordlists: For identified files, create custom wordlists using various common extensions (e.g., ~, bak, old, tmp) and apply these to filenames.
  - Windows Filenames: Be aware of how Windows file copying operations can affect filenames (e.g., “Copy of ” prefix) which might still reveal useful information if errors occur.
 
  $${\color{green}Information \space Obtained \space Through \space Server \space Vulnerabilities \space and \space Misconfiguration}$$

- Directory Listing: Misconfigured servers may allow directory listing, revealing unreferenced pages.
- Known Vulnerabilities: Be aware of specific vulnerabilities in web servers such as Apache and IIS that can expose hidden content.

$${\color{green}Use \space of \space Publicly \space Available \space 
Information}$$

- Search Engine Archives: Old or removed pages might still be indexed by search engines or cached. Use search operators (e.g., site:www.example.com) and cache versions to find hidden content.
- Third-Party Links: External websites may link to hidden pages or functionality within the target application.

$${\color{green}Filename \space Filter \spaceBypass}$$

- Obscure Filename Parsing: Exploit filename parsing discrepancies by using unconventional filename conventions. For example, Windows 8.3 filename expansion can bypass filters.
- Common Techniques:
  - Remove incompatible characters.
  - Convert spaces to underscores.
  - Use truncated and uppercase names with ~<digit>.

**2.Gray-Box Testing**

- Manual Examination: Thoroughly examine files in web directories manually or script searches for common backup or old file naming conventions.
- Scheduled Checks: Implement regular background jobs to identify files with predictable backup or old file extensions and perform periodic manual reviews.
