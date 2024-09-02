# OVERVIEW #

$${\color{green}Test \space Objectives}$$

Ensure that the session is managed securely and does not put user credentials at risk.

# HOW TO TEST #

- Some applications store credentials in an encoded form in the browser's storage, which can be verified through web storage testing and session analysis. Credentials should not be stored on the client side and should be replaced by server-generated tokens.
- Applications that automatically inject user credentials can be exploited through ClickJacking or CSRF attacks.
- Tokens should be analyzed for their lifetime, ensuring that they do not persist indefinitely, which could pose a risk if stolen.
