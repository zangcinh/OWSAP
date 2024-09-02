# OVERVIEW #

$${\color{green}Summary}$$

The password change and reset function is a self-service mechanism that allows users to change or reset their passwords without administrator intervention. Password changes typically occur within the application, while resets may be displayed within the application or sent via email, indicating that passwords may be stored in plain text or a decryptable format.

$${\color{green}Test \space Objectives}$$

- Determine the application's resistance to account change process subversion, allowing unauthorized password changes.
- Assess the resistance of the password reset functionality against guessing or bypassing attempts.

# HOW TO TEST #

**Testing Password Change and Reset:**

- Ensure that non-admin users cannot change or reset passwords for accounts other than their own.
- Check if users can manipulate the password change or reset process to alter the password of another user or an admin.
- Verify whether the process is vulnerable to CSRF attacks.

**Testing Password Reset:**

- Verify the information required to reset a password: whether secret questions are asked or if a link is sent directly to the email.
- Assess how reset passwords are communicated to the user: directly displayed, immediate change required, or sent via email.
- Ensure that reset passwords are randomly generated securely and are not the old passwords shown in clear text.
- Confirm the reset process by sending a link with a random token to limit denial-of-service attacks.

**Testing Password Change:**

- Check if the old password is required to change the current password, preventing attackers from changing passwords during a compromised session.
