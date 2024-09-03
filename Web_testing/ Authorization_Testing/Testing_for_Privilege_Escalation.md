# OVERALL #

$${\color{green}Summary}$$

Identify and prevent users from escalating their access rights beyond what is allowed.

$${\color{green}Types \space of \space Escalation}$$

- Vertical Escalation: Accessing resources granted to higher privilege accounts (e.g., admin privileges).
- Horizontal Escalation: Accessing resources of another user with similar privileges (e.g., viewing another user's data in an online banking app).

- $${\color{green}Test \space Objectives}$$

- Identify injection points, attempt to bypass security measures, and manipulate privileges to check if unauthorized privilege changes are possible.

# HOW TO TEST #

**1.Function Access Verification:**
- Test functions like creating, receiving, or deleting information.
- Attempt to access these functions as a different user or role to check for unauthorized access.

**2.User Group Manipulation:**
- Example: A user with `groupID=grp001` can access a specific order.
- Check if modifying `groupID` allows unauthorized access to data.

**3.User Profile Manipulation:**
- Test if altering hidden parameters, like a `profile` field, can elevate privileges (e.g., from regular user to `SysAdmin`).

**4.Condition Value Manipulation:**
- Example: Modifying error codes or session state values to bypass restrictions or escalate privileges.

**5.IP Address Manipulation:**
Adjust headers like `X-Forwarded-For` to bypass IP-based restrictions.

**6.URL Traversal:**
- Check for access to unauthorized pages using traversal techniques (e.g., `/../.././userInfo.html`).
- Test partial URL checks and encoding techniques to bypass URL-based authorization.

**7.Weak Session ID:**
- Check if session IDs are predictable or vulnerable to brute force (e.g., using MD5 hash of `Password + UserID`).
