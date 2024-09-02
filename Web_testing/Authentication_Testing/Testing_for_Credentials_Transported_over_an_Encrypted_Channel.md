# OVERALL #

$${\color{green}Summary}$$

Ensure that web applications encrypt authentication data during transit to prevent attackers from capturing sensitive information using network sniffing tools.

$${\color{green}How \space to \space Test}$$

- Check if credentials are always encrypted during key interactions, such as login requests, session token exchanges, and password reset processes.
- Verify that HTTPS is used consistently for encrypting data between client and server.
- Assess the encryption algorithms and key strength used to ensure data protection.

$${\color{green}Test \space Objectives}$$

 Protect against attackers who may intercept unencrypted credentials using tools like Wireshark or proxies.

# HOW TO TEST #

**1.Setup:**

- Use tools like browser developer tools or proxies (e.g., OWASP ZAP).
- Disable any HTTPS-enforcing extensions.

**2.Test Steps:**

- Inspect captured traffic for sensitive data (passwords, tokens).
- Ensure all requests that involve credentials are sent via HTTPS.

**3.Testing Scenarios:**

- Login: Attempt to access the login page using HTTP. Ensure credentials are only sent using HTTPS.
- Account Creation: Force browsing to HTTP and check if account creation still uses HTTPS.
- Password Reset/Change: Test all account manipulation forms for HTTPS enforcement.
- Session Management: Check if session tokens are always transmitted securely.

**4.Pass/Fail Criteria:**

- Pass: All sensitive interactions occur over HTTPS.
- Fail: Any credentials sent over HTTP.

**5.Remediation:**

-  Implement site-wide HTTPS with HSTS.
- Redirect all HTTP traffic to HTTPS.
- Use free certificate authorities like Let’s Encrypt
