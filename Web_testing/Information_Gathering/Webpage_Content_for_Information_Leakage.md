# OVERALL #

$${\color{green}Objective}$$

- Review HTML comments and metadata to detect information leakage.
- Collect and review JavaScript files to understand the application and identify any sensitive information leakage.
- Identify if source map or other debug files are present in the front end

# Review webpage comments and metadata #

1. Inspect HTML Code: Use the browser's "Inspect Element" or "View Page Source" feature (right-click on the page > Inspect or Ctrl+U) to look through the HTML code.
2. Search for Comments: Look for HTML comments (<!-- comment -->). Check if they contain sensitive information like server paths, internal notes, or version numbers.
3. Check Metadata: Review the <meta> tags for sensitive information, such as version details (<meta name="generator" content="XYZ CMS">) or internal configurations.

# Identifying JavaScript Code and Gathering JavaScript Files #

1. Locate JavaScript Code:

- Inline JavaScript: Check <script> tags in the HTML source for sensitive information.
- External JavaScript Files: Identify files linked in <script src="file.js"></script> and review their content.

2. Locate JavaScript Code:

- Hardcoded Credentials: Watch for API keys, internal IP addresses, and credentials.
  Example :

![image](https://github.com/user-attachments/assets/aa1ed6ec-7f36-432c-a3ea-18a0a4591ea0)

- Sensitive Routes: Identify hidden or internal URLs and routes.

![image](https://github.com/user-attachments/assets/640a2dc7-2b6d-452f-8cc4-1047b048d1f9)

3. Check API Key Restrictions:

- Verify Restrictions: Ensure API keys are restricted by IP, HTTP referrer, or other constraints to prevent misuse.

# Identifying Source Map Files #

1. Check DevTools:

- Source map files are often loaded when DevTools are opened if they are available and configured to display.

2. Find Source Map by Appending “.map” Extension:

- Locate external JavaScript files by examining <script> tags in the HTML or through linked JavaScript files.
- Append the `.map` extension to the JavaScript file’s extension.

# Black-Box Testing #

1. Review Source Map Files:

- Identify and open source map files linked with JavaScript files to check their content.

2. Inspect for Sensitive Information:

- Look for internal file paths and other details that could reveal the application's structure or code
