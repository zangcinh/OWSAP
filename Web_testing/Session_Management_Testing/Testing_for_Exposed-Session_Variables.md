# OVERALL #

$${\color{green}Summary}$$

 Exposed session tokens (like cookies, session IDs, or hidden fields) can allow attackers to impersonate users and gain unauthorized access. Protecting these tokens is crucial, especially during transmission between the client and server.

 >Các token phiên (như cookie, SessionID, hoặc trường ẩn) bị lộ có thể cho phép kẻ tấn công mạo danh người dùng và truy cập trái phép vào ứng dụng. Việc bảo vệ các token này là rất quan trọng, đặc biệt khi chúng được truyền giữa trình duyệt khách và máy chủ.

 $${\color{green}Test \space Objective}$$

- Ensure session data is encrypted properly.
- Review caching settings to avoid exposure.
- Assess the security of communication channels and methods.

# HOW TO TEST #

$${\color{green}Encryption \space and \space Secure \space Transmission \space of \space Session \space Tokens}$$

- Ensure that Session IDs are always transmitted securely using encryption (e.g., SSL/TLS
- **Test Steps**:
 - Attempt to change URLs from HTTPS to HTTP to see if the Session ID can still be sent unencrypted
 - Modify form submissions or hidden fields to determine if Session IDs are transmitted securely
- **Expected Results:**
 - Session IDs should always be sent via an encrypted channel
 - Each successful authentication should generate a new Session ID to prevent reuse.

$${\color{green}Proxies \space & \space Caching \space Vulnerabilities}$$

-  Ensure that Session IDs are not exposed through caching or proxies
-  **Test Steps:**
 - Review the application’s behavior when accessed through various proxies (e.g., corporate, ISP).
 - Check for proper cache control headers like `Cache-Control: no-cache` and `Expires: 0` to prevent caching of Session IDs.
- **Expected Results:**
 - Session IDs should not be cached by proxies or local caches
 - All cache-control headers should be correctly set to prevent Session ID exposure

$${\color{green}GET \space & \space POST \space Vulnerabilities}$$

-  Test the transport mechanism to ensure Session IDs are not exposed in URLs or logs
- **Test Steps:**
 - Check if Session IDs are being sent in GET requests, which can be logged by proxies or firewalls.
 - Test if POST requests containing sensitive information can be manipulated and sent as GET requests.
- Expected Results:
 - Session IDs should not be used in GET requests due to logging risks.
 - Server should not accept Session ID data sent via GET if it was designed for POST

$${\color{green}Transport \space Layer \space Vulnerabilities}$$

- Validate the security of the transport layer for Session ID transfers
- **Test Criteria:**
 - Examine how Session IDs are transferred (GET, POST, hidden fields).
 - Verify that Session IDs are always sent over encrypted channels by default
 - Check if cache-control directives are properly set for each request/response containing Session IDs
 - Test if GET and POST methods can be interchanged, which can expose vulnerabilities
   

