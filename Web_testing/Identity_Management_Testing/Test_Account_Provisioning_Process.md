$${\color{green}Summary}$$

Ensure proper identification and authorization during the creation and removal of user accounts to prevent unauthorized access.

$${\color{green}Test \space Objectives}$$

Identify which roles can provision or de-provision accounts and what types they can manage.

$${\color{green}How \space to \space test?}$$

- Determine which roles can provision accounts and what types (e.g., admin or regular user).
- Check if provisioning requests are verified or authorized.
- Verify if de-provisioning requests are validated and authorized.
- Test if administrators can create other admins or accounts with higher privileges.
- Check if users can de-provision themselves.
- Review how resources owned by de-provisioned users are managed (deleted or transferred).
