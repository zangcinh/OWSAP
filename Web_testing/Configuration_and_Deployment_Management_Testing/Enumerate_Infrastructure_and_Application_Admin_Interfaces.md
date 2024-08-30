# OVERALL #

$${\color{green}Summary}$$	

Testing administrator interfaces aims to discover and assess whether privileged functionality can be accessed by unauthorized or standard users. The goal is to identify hidden admin interfaces and functions that might be inadequately protected, which could allow changes to site configuration, design, data, and user account management.

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$	

**1.Directory and File Enumeration:**

- Attempt to access common administrative paths like /admin or /administrator. Sometimes, these paths can be quickly identified using [Google dorks](https://www.exploit-db.com/google-hacking-database).
- Use tools for brute-forcing server directories and filenames to find hidden administrative pages.
 
**2.Comments and Links in Source Code:**

- Inspect the HTML and JavaScript source code for links or comments that may reveal administrative functionality.
  
**3.Reviewing Server and Application Documentation:**

- Check default configuration or help documentation for potential administrative interface paths and default credentials.

**4.Publicly Available Information:**

- Look for default administrative interfaces in widely used applications like WordPress.
  
**5.Alternative Server Port:**

- Try accessing administrative interfaces on different ports from the main application, such as port 8080 for Apache Tomcat.

**6.Parameter Tampering:**

- Test for administrative functionality by modifying GET or POST parameters, or cookie values. Look for hidden fields or cookies that indicate admin access
  
Example:

 `<input type="hidden" name="admin" value="no">`
 
or

 `Cookie: session_cookie; useradmin=0.`

 $${\color{green}-Box \space Testing}$$	

 - Examine Server and Application Components: Ensure that administrative pages are not accessible to unauthorized users.
 - Verify Default Credentials and Configurations: Ensure that no components use default credentials or configurations.
 - Review Source Code:  Ensure that the authorization and authentication model clearly separates normal users from site administrators.
 - Assess Shared User Interface Functions:  Ensure clear separation between normal user and administrator interfaces.
 - Each web framework may have its own admin default pages or path.
  - WebSphere:
    
    ![image](https://github.com/user-attachments/assets/f5cebba0-e466-4cb3-af7e-4cda1f15ac3a)
    
  - PHP:
    
    ![image](https://github.com/user-attachments/assets/f97dcba5-2934-4ab7-9774-7073fd58e784)
    
  - FrontPage:
    
    ![image](https://github.com/user-attachments/assets/18eda04b-456b-4202-bce0-de07f78f049a)

  - WebLogic:
    
    ![image](https://github.com/user-attachments/assets/b5f5200d-4405-4017-b0ee-140c6181fe18)

  - WordPress:
    
    ![image](https://github.com/user-attachments/assets/02b6e494-c907-41c4-8395-9433dad457bf)
