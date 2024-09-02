$${\color{green}Summary}$$

Applications use role-based access control (RBAC) to manage permissions based on user roles, such as administrator, auditor, support engineer, and customer.

$${\color{green}Test \space Objectives}$$

- Identify and document application roles.
- Attempt to switch, change, or access other roles.
- Review the permissions and granularity of roles.


$${\color{green}Testing \space Steps:}$$

- Identify Roles: Check documentation, developer guidance, or fuzz for roles in cookies, account variables, hidden directories, etc.
- Switch Roles: Test access to different roles to validate permissions.
- Review Permissions: Ensure roles have appropriate permissions; prevent unauthorized access or excessive privileges.
