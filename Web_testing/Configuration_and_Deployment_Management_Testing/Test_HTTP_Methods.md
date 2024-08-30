# OVERALL #

$${\color{green}Summary}$$	

HTTP supports several methods besides GET and POST, such as PUT, DELETE, CONNECT, OPTIONS, TRACE, etc. These methods can be misused if the web server is misconfigured, leading to security risks. The testing objectives include enumerating supported methods, checking for access control bypass, testing XST vulnerabilities, and exploring HTTP method overriding techniques.

$${\color{green}Test \space Objectives}$$

- Enumerate supported HTTP methods.
- Test for access control bypass.
- Check for Cross-Site Tracing (XST) vulnerabilities.
- Evaluate HTTP method overriding techniques.

# HOW TO TEST #

$${\color{green}Discover \space the \space Supported \space Methods}$$

**1.Objective of the Test:** Identify the HTTP methods supported by the web server to ensure that only necessary methods are allowed, thereby reducing security risks.

**2.How to Perform the Test:**

- **Using the OPTIONS Method**: This is the most direct way to identify the HTTP methods supported by the server. OPTIONS sends a request to the server and receives a list of supported methods in response.
- **Verify Server Response with Different Methods**: Manually send requests using different HTTP methods (e.g., GET, POST, PUT, DELETE) to see how the server responds.
- **Using Nmap with the http-methods Script**:
  - Tool: Nmap is a powerful tool for scanning vulnerabilities and listing supported HTTP methods.
  - **Command**:
    >nmap -p 443 --script http-methods --script-args http-methods.url-path='/index.php' localhost

![image](https://github.com/user-attachments/assets/58e8c296-e5c8-4026-a922-fdd46f2a6b1f)

**3. Thoroughly Test Endpoints Accepting Specific Methods**:

- For applications that need to accept various methods (like RESTful Web Services), thoroughly check to ensure that only the required methods are allowed at each endpoint.

$${\color{green}Testing \space the \space PUT \space Method}$$	

**1.Capture the Base Request:** Use a web proxy to capture the base request to the target.

**2.Change the Request Method to PUT:** Modify the request method to PUT and upload a test file (e.g., `test.html`):

![image](https://github.com/user-attachments/assets/520f371c-b4a0-4da3-ab9c-1a5044746430)

**3.Verify the Response:**
 If the server responds with 2XX success codes or 3XX redirections, confirm by making a GET request for the `test.html` file. The application is vulnerable if the file is accessible.

**4.Test Other Paths:** If PUT is not allowed on the base URL, try other paths within the system.

**5.Note:** If successful in uploading a web shell, either overwrite it or inform the target's security team to remove it promptly.

$${\color{green}Testing \space for \space Access \space Control \space Bypass}$$	

**1.Identify the Protected Page:** Find a page that normally requires login or redirects to a login page with a GET request.

**2.Issue Various Requests:** Test the page using different HTTP methods, such as HEAD, POST, PUT, and even arbitrary methods like BILBAO, FOOBAR, or CATS.

**Example** using `ncat`

![image](https://github.com/user-attachments/assets/9972d758-4240-4d8a-9021-044d0f87c371)

**3.Check the Response:** If the response is `HTTP/1.1 200 OK` and the content is not a login page, it might indicate a potential access control bypass issue.

**4.Test for Exploitation:**

- Issue additional requests that simulate Cross-Site Request Forgery (CSRF) attacks to exploit the access control issue:
  >HEAD /admin/createUser.php?member=myAdmin
  >PUT /admin/changePw.php?member=myAdmin&passwd=foo123&confirm=foo123
  >CATS /admin/groupEdit.php?group=Admins&member=myAdmin&action=add

->These commands are designed to create a new user, change passwords, and assign administrative privileges, respectively.

$${\color{green}Testing \space for \space Cross-Site \space Tracing \space Potential}$$	

**1.TRACE Method:**

- The TRACE method is an HTTP command used for testing and debugging. It instructs the web server to send back the exact message it received.
- While it seems harmless, it can be exploited to steal sensitive information, such as cookies, even if they have the HttpOnly attribute set to protect them from JavaScript access.

**2.How to Test:**

- Send a TRACE request to the server to see if it responds with the same content. For example:

  ![image](https://github.com/user-attachments/assets/a4686f80-0d4e-4161-ad3d-d2facef5c6b5)

-> If the server responds with a 200 OK status and reflects the headers or content you sent, it may indicate a security issue.

**3.Exploiting the Vulnerability:**

- Try sending a TRACE request with a script or other malicious payload to see if the server reflects and executes it:

  ![image](https://github.com/user-attachments/assets/d7d942b0-18ef-4b1f-9b11-ae77b8dcd965)

- If the response includes the JavaScript code and it executes in the browser, the vulnerability can be exploited to perform Cross-Site Scripting (XSS) attacks.

$${\color{green}Testing \space for \space HTTP \space Method \space Overriding}$$	

**1.What is HTTP Method Overriding?**
-Some web systems use special headers to override the HTTP method in a request. This allows you to use methods like PUT or DELETE even if they are normally blocked by firewalls or proxies.

**2.Common Headers for Overriding:**

- `X-HTTP-Method`
- `X-HTTP-Method-Override`
- `X-Method-Override`

**3.How to Test:**

- Step 1: Send a request using a method like PUT or DELETE. If the server says “405 Method Not Allowed,” it means these methods are blocked.

![image](https://github.com/user-attachments/assets/a3889ddf-3e26-4cfe-8d97-5b6d6c0c9a6c)

- Step 2: Resend the same request but add one of the overriding headers:

![image](https://github.com/user-attachments/assets/8b814695-2df2-40ff-afdc-e22cd530a027)

- Check the Response: If the server responds with “200 OK,” then the method is allowed when using the overriding header.


