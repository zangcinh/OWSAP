# OVERALL #

$${\color{green}Summary}$$	

- HSTS is a security feature that instructs web browsers to always use HTTPS instead of HTTP for a domain, preventing unsecured connections and protecting against certificate errors. This is crucial for ensuring encrypted communication between the browser and server.

$${\color{green}HSTS \space Header \space Directives}$$	

- `max-age`: Specifies how long (in seconds) the browser should enforce HTTPS.
- `includeSubDomains`: Ensures that all sub-domains also use HTTPS.
- `preload` (Unofficial): Indicates that the domain is included in the browser preload list to enforce HTTPS from the first visit.

** Example **

>Strict-Transport-Security: max-age=31536000; includeSubDomains

$${\color{green}Test \space Objectives}$$	

- Verify the presence and correctness of the HSTS header to ensure it is properly configured and functioning.

 # HOW TO TEST #

- To confirm the presence of the HSTS header, you can examine the server's response using an intercepting proxy or by using `curl` with the following command:

$ curl -s -D- https://owasp.org | grep -i strict

![image](https://github.com/user-attachments/assets/d4e55f39-865f-489d-b5b7-da8334e8ddc7)

This command sends an HTTPS request to the server and displays the HTTP headers in the response.
