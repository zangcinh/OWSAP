# OVERALL #

$${\color{green}Summary}$$

Improper file permissions can expose sensitive information or allow unauthorized modifications. This is particularly risky for configuration files, executable files, or files containing sensitive user data. 

$${\color{green}Test \space Objectives}$$

Review and identify any improper or overly permissive file permissions.

# HOW TO TEST #

**1.Check Permissions:**

- Linux: Use the `ls` or 'namei` command to check file permissions
  >ls -l /PathToCheck/
  >
  >namei -l /PathToCheck/

**2.Files and Directories to Test:**
- Web files/directories
- Configuration files/directories
- Sensitive files (e.g., encrypted data, passwords, keys)
- Log files (e.g., security logs, operation logs, admin logs)
- Executables (e.g., scripts, EXE, JAR, class, PHP, ASP)
- Database files/directories
- Temporary files/directories
- Upload files/directories
