# perform a SQL injection attack that logs in to the application as the `administrator` user #

Use `administrator'--` as user name and type some random password

![image](https://github.com/user-attachments/assets/14414024-929b-4f7f-8b16-7d1b74d18239)

Now you successfully login as `administrator`

![image](https://github.com/user-attachments/assets/efa6de52-2929-4a0e-b82b-184f7db9cb87)

# Explaination #

- When you input `administrator'--`, the SQL query behind the login form may look something like this:
  `SELECT * FROM users WHERE username = 'administrator'--' AND password = 'password'`
- The `--` symbol comments out the rest of the query, including the password check. As a result, the query will only check for the username `administrator` and ignore the password validation, allowing you to log in as the administrator without knowing the correct password.
