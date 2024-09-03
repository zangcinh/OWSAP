# OVERVIEW #

$${\color{green}Summary}$$

This test aims to verify how the authorization schema is implemented for each role or privilege to access restricted functions and resources.

>Bài kiểm tra này nhằm xác minh cách hệ thống ủy quyền được triển khai cho các vai trò và quyền hạn để truy cập các chức năng và tài nguyên bị giới hạn.

$${\color{green}Key \space Checks}$$

- Can resources be accessed without authentication?
- Can resources be accessed after logging out?
- Can users access functions meant for other roles or privileges?

$${\color{green}Testing \space Administrative \space Access}$$

- Check if non-admin users can access admin functions.
- Verify if users with incorrect roles can perform restricted actions.

# HOW TO TEST #

**1.Horizontal Authorization Bypass**

- Horizontal bypass occurs when a user accesses resources or functions of another user with the same role or privilege.
- Testing Steps:
  - Register two users with identical privileges and maintain two active sessions.
  - Swap session identifiers between requests to test if private data or operations are accessible across users.
  - An application is vulnerable if a user can access or operate on another user's data or resources.
Example: If a request meant for "user A" can be performed using "user B's" session, then horizontal bypass is present.

**2.Vertical Authorization Bypass**
- Vertical bypass happens when a user accesses resources or performs actions reserved for higher privileges.
- Testing Steps:
  - Register users with different roles, keep two sessions, and swap session identifiers.
  - Attempt higher-privilege actions with lower-privilege sessions.
  - The system is vulnerable if a lower-privilege session can access higher-privilege resources or functions.
Example: If a "customer" can perform "admin" functions, such as deleting events, the application is vulnerable.

**3.Administrative Access Testing**
- Verify if lower roles can access admin functions directly through URLs or functions without proper authorization checks.
- Testing Steps:
  - Access admin-specific functions using non-admin sessions.
  - Applications that rely on GUI-level validation are often vulnerable.
- Special Headers Testing
  - Check if headers like `X-Original-URL` or `X-Rewrite-URL` can be used to override URL paths, bypassing access control.
- Headers to Test:
  - `X-Forwarded-For`
  - `X-Remote-IP`
  - Use values like `127.0.0.1`, `localhost`, or internal IP ranges to test access to protected resources.
  
**4.Key Points**
- Test horizontal bypass by swapping session identifiers for similar roles.
- Test vertical bypass by accessing higher privilege functions with lower privilege sessions.
- Check admin access vulnerabilities through direct URL manipulation.
- Test for special header handling that might override or bypass access controls.
