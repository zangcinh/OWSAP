# OVERVIEW #

$${\color{green} Objective}$$

- Identify Components: Detect which web frameworks or open-source software are used in the web application by analyzing markers like HTML headers, cookies, and directory structures.
- Use Markers: Look for specific indicators that reveal the framework or application, such as default paths or version information.
- Reduce Effort: Leverage identification to streamline the security testing process and focus on relevant vulnerabilities associated with the identified components.

# Black-Box Testing #

-  Several common locations to consider in order to identify frameworks or components:
  - HTTP headers
  - Cookies
  - HTML source code
  - Specific files and folders
  - File extensions
  - Error messages

# HTTP Headers #

- The `X-Powered-By` header can reveal the web framework or technology in use -> but may not always be present as it can be disabled or obfuscated.
- Other headers, such as X-Generator, can also give clues about the framework. For instance, `X-Generato`: Swiftlet might indicate the use of Swiftlet, while `X-Powered-By` might show PHP version.

# Cookies #

-  Framework-specific cookies can help determine the web framework in use. For example, the presence of a cookie named CAKEPHP suggests that the `CakePHP` framework is being used.
  
>Framework CakePHP là gì? Đó là một Framework PHP được xây dựng dựa theo mô hình MVC (Model-View- Controller) có mã nguồn mở, phát triển các ứng dụng, phần mềm web

- Frameworks allow customization of cookie names, which can be changed in the configuration files. For instance, in CakePHP, the cookie name can be set as follows:

![image](https://github.com/user-attachments/assets/5e1813fb-0ebd-443d-8bca-f4d4f7bc7362)

# HTML Source Code #

- Search for HTML comments, framework-specific paths, and script variables that can reveal the framework or its version.
- Information is often found in the <head> section or at the bottom of the HTML page.
-  Analyze the full HTML response to uncover all potential indicators of the web framework.

# Specific Files and Folders #

1. Understanding File and Folder Structures:

- Unique Paths: Different web components have unique file and folder structures. Identifying these can help pinpoint the application or component used.
- Example Paths: Specific directories like /wp-includes/, /wp-admin/, and /wp-content/ for WordPress.

2. Dirbusting Technique:

- Definition: Dirbusting, or directory brute-forcing, involves using known folder and filename lists to probe a target server and analyze HTTP responses to discover server content.
- Example: A successful dirbusting attack against a WordPress site using Burp Suite might reveal paths and files indicating the presence of WordPress.
- Results: HTTP responses like 403 (Forbidden), 302 (Redirect), and 200 (OK) can confirm the existence of specific directories or components.

2. Additional Tips:

- Check robots.txt: Before starting dirbusting, review the robots.txt file for information about sensitive directories that might be listed there.
- Example File: Sensitive or application-specific directories might be exposed in robots.txt, which can provide additional clues.

3. Utilize Existing Resources:

- FuzzDB Wordlists: Use pre-defined lists like FuzzDB for predictable files and folders during dirbusting to enhance your search.

# File Extensions #

1. File Extensions and Their Associations:

- `.php`– Indicates the use of PHP, a popular server-side scripting language.
- `.aspx` – Associated with Microsoft ASP.NET, a framework for building web applications.
- `.jsp` – Signifies the use of Java Server Pages (JSP), a technology for creating dynamic web content in Java.

2. Example:

![image](https://github.com/user-attachments/assets/7dded92b-8933-4bdc-bd2c-c99668545249)

-> OWASP wiki uses PHP due to the .php extension in its URLs.

# Error Messages #

1. Error Messages Provide Clues:

- File System Paths: Error messages can reveal specific paths like wp-content, indicating the use of WordPress.
- Technology Indicators: Messages showing files such as functions.php suggest the use of PHP.

2. Example:

![image](https://github.com/user-attachments/assets/74e87259-4e9f-4026-9b17-2a1955f75a7c)

# Common Identifiers #

| Framework | Cookie name | 
|--------------|-------|
| Zope | zope3 | 
| CakePHP | cakephp |
|phpBB | phpbb3_ | 
|WordPress| wp-settings | 
|Graffiti CMS |graffitibot | 

# HTML Source Code #

| Application | Keyword | 
|--------------|-------|
| WordPress | `<meta name="generator" content="WordPress 3.9.2" />`| 
| phpBB | `<body id="phpbb" `|
|Mediawiki | `<meta name="generator" content="MediaWiki 1.21.9" />` | 
|Joomla| `<meta name="generator" content="Joomla! - Open Source Content Management" />` | 

# General Markers #

- %framework_name%
- powered by
- built upon
- running

Specific Markers

| Framework | Keyword | 
|--------------|-------|
| Adobe ColdFusion | `<!-- START headerTags.cfm` | 
| Microsoft ASP.NET	 | `__VIEWSTATE` |
|ZK | `<!-- ZK` | 
|Business Catalyst| `<!-- BC_OBNW -->` | 
|Indexhibit |`ndxz-studio` | 

# Tools #

- [WhatWeb](https://github.com/urbanadventurer/WhatWeb)
- [Wappalyzer](https://www.wappalyzer.com/)
