# OVERALL #

$${\color{green}Summary}$$

- Verify that the application automatically logs out users after a period of inactivity to ensure session security.
  - Implement Timeout: Confirm that the session closes and is invalidated after a defined period of inactivity.
  - Server-Side Management: Ensure session timeout is enforced on the server side to prevent extending the session.
  - Security: Ensure session tokens are destroyed after timeout.
 
$${\color{green}Test \space Objectives}$$

Validate that the application properly implements session timeout

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$

- Testers check if a session timeout exists by logging in and waiting for automatic logout.
- After timeout, all session tokens should be destroyed or unusable.
- Determine if the timeout is enforced by the client, server, or both:
  - If the session cookie lacks time data, the server enforces the timeout.
  - If the cookie contains time-related data, the client might be involved, and testers can attempt to manipulate the cookie to prolong the session.
- Server-side checks should invalidate sessions, making old session cookies useless.

$${\color{green}Gray-Box \space Testing}$$

- Verify that the logout function destroys or invalidates session tokens.
- Ensure the server checks session state, preventing replay attacks with destroyed tokens.
- The timeout must be enforced server-side, especially if time data comes from a client-side token, which should be cryptographically protected.
- Key is server-side session invalidation, making client-side cookie clearance optional but recommended.

