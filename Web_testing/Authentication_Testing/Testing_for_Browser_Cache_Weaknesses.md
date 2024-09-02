# OVERVIEW #

$${\color{green}Summary}$$

- Applications must instruct the browser not to store sensitive data like addresses, credit card details, Social Security Numbers, or usernames.
- Browsers may cache information to enhance performance or store history for user convenience, which can lead to risks if sensitive data is stored and can be retrieved later.

$${\color{green}Test \space Objectives}$$

- Check if the application stores sensitive information on the client-side.
- Check if access to stored data can occur without proper authorization.

# HOW TO TEST #

**1.Browser History:**

- Objective: Verify if sensitive information can be accessed through the browser's Back button after logout.
- How to Test: Enter sensitive information, log out, and click the Back button to see if previously displayed sensitive information is accessible without authentication.
- Mitigation: Use HTTPS and set Cache-Control: must-revalidate.

**2.Browser Cache:**

- Objective: Ensure that sensitive data is not stored in the browser cache.
- How to Test:
  - Use a proxy tool like OWASP ZAP to inspect server responses and verify that pages containing sensitive information are not cached.
  - Check for HTTP response headers that include:
      - `Cache-Control: no-cache`, `no-store`
      - `Expires: 0`
      - `Pragma: no-cache`
  - Verify that sensitive information is not stored in browser cache directories.
- Mitigation: Ensure all sensitive pages enforce `no-cache` directives.

**3.Review Cached Information:**

- Use browser developer tools or external applications to inspect cached data.
- In Firefox, use `about:cache` to check cache details.

**4.Check for Mobile Browsers:**

- Mobile browsers may handle cache directives differently. Start a new session with a clean cache and test using mobile browser emulators or user-agent settings in proxies.

**5.Gray-Box Testing:**

- Similar to black-box testing, but with additional access to account credentials to test sensitive pages that require authentication.
