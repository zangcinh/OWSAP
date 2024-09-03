# OVERVIEW #

$${\color{green}Summary}$$

**1.Purpose of Cookies:**
- Cookies are used to manage sessions, keeping track of the user’s state across multiple requests. They store information about the user, their actions, preferences, etc.

**2.Security Risks:**
- Weak cookies can be predicted and forged by attackers, leading to session hijacking, privilege escalation, and other unauthorized actions.

**3.Attack Patterns:**
- Cookie Collection: Gather a sufficient number of cookie samples.
- Cookie Reverse Engineering: Analyze the cookie generation algorithm.
- Cookie Manipulation: Forge a valid cookie to perform attacks (may require numerous attempts).

$${\color{green}Test \space Objectives}$$

**1.Gather Session Tokens:**
- Collect session tokens for the same user and different users where possible.

**2.Analyze Randomness:**
- Ensure that there is enough randomness in the session token generation to prevent session forgery attacks.

**3.Modify Cookies:**
- Test if cookies that are not signed and contain manipulable information can be altered.

 # HOW TO TEST #

$${\color{green}Black-Box \space Testing \space and \space Example}$$

 **Criteria to Check:**

**1.Secure Cookie Directives:**
- Verify that all`Set-Cookie` directives are tagged as `Secure`.

**2.Transport Encryption:**
- Ensure that cookie operations do not occur over unencrypted transport.

**3.Forced Unencrypted Transport:**
- Determine if cookies can be forced over unencrypted channels and assess how the application maintains security.

**4.Persistent Cookies:**
- Identify any persistent cookies, check their Expires times, and evaluate if they are reasonable.

**5.Transient Cookies:**
- Confirm that cookies meant to be transient are configured correctly.

**6.Cache-Control Settings:**
- Review HTTP/1.1 and HTTP/1.0 `Cache-Control` settings to protect cookies.

**Cookie Collection:**

**1.Number of Cookies:**
- List all cookies used by the application, noting their creation events, associated pages, domains, values, and characteristics.

**2.Cookie Generation and Modification:**
- Identify which parts of the application generate or modify cookies and what events trigger these changes.

**3.Cookie Dependency:**
- Determine which parts of the application require specific cookies and test access with and without cookies or with modified values.

**4.Spreadsheet Mapping:**
- Create a spreadsheet mapping cookies to application parts and related information.

**Session Analysis:**

**1.Token Structure & Information Leakage:**
- Examine session ID structure and content to identify any clear-text data or obfuscation methods.

**2.Session ID Predictability and Randomness:**

- Test if session IDs are random and resistant to statistical or cryptographic analysis. Analyze patterns and potential predictability.

**2.Brute Force Attacks:**
- Assess the feasibility of brute-force attacks based on the length and randomness of session IDs.

**Cookie Reverse Engineering:**

**1.Unpredictability:**
- Ensure cookies contain hard-to-guess data using random values or cryptography.

**2.Tamper Resistance:**
- Check if cookies resist malicious modification, and if necessary, use encrypted hashes to secure values.

**3.Expiration:**
- Verify that critical cookies have appropriate expiration times and are removed afterward.

**4.Secure Flag:**
- Ensure critical cookies have the Secure flag enabled to transmit only over encrypted channels.

# Gray-Box Testing and Examples:#

**1.Random Session Token:**
- Session IDs or cookies should not be predictable and should use cryptographic algorithms with a key length of 256 bits.

**2.Token Length:**
- Session IDs should be at least 50 characters long.

**3.Session Time-out:**
- Session tokens should have a defined time-out based on the application's data criticality.

**4.Cookie Configuration:**
- Ensure cookies are non-persistent (RAM memory only), `Secure`, and `HttpOnly`.
