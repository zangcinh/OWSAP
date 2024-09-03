# OVERVIEW #

$${\color{green}Summary}$$

- Identify vulnerabilities where an application allows direct access to objects (e.g., database records or files) based on user-supplied input, without proper authorization checks, allowing unauthorized access.
- IDOR occurs when an application uses user input to directly access objects without validating authorization.
- This allows attackers to manipulate input parameters (such as IDs or filenames) to access data they shouldn't have access to.

$${\color{green}Test \space Objectives}$$

- Identify Object References: Find points in the application where parameters are used to access objects directly.
- Assess Access Controls: Check if modifying parameters allows access to unauthorized data.
- Example Test: Change parameter values (e.g., `userID=123` to `userID=456`) to see if the application permits access to another user’s data.

# HOW TO TEST #

**1.Identify Object References:**
- Map out all locations in the application where user input is used to access or perform operations on objects directly (e.g., database records, files, application pages).

**2.Testing Process:**
- Multiple Users: Use at least two users with different access levels to test access to different objects and functions. This helps in testing direct object references more efficiently.
- Modify Parameters: Change the values of parameters used to reference objects and check if unauthorized access is possible. Common scenarios include:
  - Database Records: Modify URL parameters (e.g., `invoice=12345`) to access data that should be restricted.
  - System Operations: Change parameters used in operations (e.g., `user=someuser`) to see if you can perform actions on other users' data.
  - File System Resources: Alter file references (e.g., `img=img00011`) to access files that should not be accessible.
  - Application Functionality: Modify parameters controlling application functionality (e.g., `menuitem=12`) to bypass restrictions and access unauthorized features.

**3.Example Scenarios:**
- Database Record Retrieval: Test by changing parameters to access records from other users.
- Password Changes: Attempt to change the password of another user by modifying user parameters.
- File Access: Try to access files not meant for the current user.
- Functionality Access: Test if modifying parameters allows access to restricted application functionality.
