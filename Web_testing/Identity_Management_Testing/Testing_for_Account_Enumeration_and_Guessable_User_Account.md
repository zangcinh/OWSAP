# OVERALL #

$${\color{green}Summary}$$	

The goal is to identify if an application reveals valid usernames during the authentication process, which can help an attacker in brute-force or password-guessing attacks.

# HOW TO TEST #

**1.Account Enumeration:** Applications may reveal whether a username exists through different error messages when submitting valid or invalid usernames. This can expose a list of valid usernames.

**2.Testing Steps:**

- Valid Credentials Test: Submit a valid username and password, record the response.
- Valid Username, Wrong Password: Submit a correct username but an incorrect password and record the error message.
- Nonexistent Username: Use an invalid username and note how the application responds.
- Look for variations in error messages or response codes that differentiate between valid and invalid usernames.

**3.Methods to Enumerate Users:**

- Analyzing login error messages.
- Checking URL and redirection patterns.
- Using URI probing (e.g., 403 Forbidden for existing users, 404 Not Found for nonexistent ones).
- Reviewing web page titles or password recovery messages.
- Monitoring response times for variations based on valid or invalid users.

**4.Guessing User IDs:**
- Usernames can often be guessed based on company policies, patterns (sequential numbers, name conventions), or information found through external sources like LDAP or Google searches.

**5.Gray-Box Testing:**
- Similar to black-box, this involves analyzing the consistency of error messages during authentication attempts.
