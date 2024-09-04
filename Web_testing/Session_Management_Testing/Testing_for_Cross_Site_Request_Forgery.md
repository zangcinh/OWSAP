# OVERALL #

$${\color{green}Summary}$$

Cross-Site Request Forgery (CSRF) is an attack that forces a user to perform unintended actions on a web application in which they are authenticated. A successful CSRF exploit can compromise user data and operations, especially if the target is an administrator account, potentially compromising the entire application.

>CSRF là một cuộc tấn công buộc người dùng thực hiện các hành động không mong muốn trên ứng dụng web mà họ đã xác thực. Khi khai thác thành công, CSRF có thể làm tổn hại dữ liệu và hoạt động của người dùng, đặc biệt nghiêm trọng nếu mục tiêu là tài khoản quản trị viên.

$${\color{green}How \space CSRF \space Works}$$

- Browsers automatically send authentication information like cookies with requests to the web application.
- Attackers exploit knowledge of valid application URLs and functionalities.
- The application’s session management relies solely on information known by the browser.
- HTML tags like `<img>` can automatically send HTTP requests, facilitating the attac

$${\color{green}Examples \space and \space Attack \space Techniques}$$

- Attackers send malicious links via email or chat to trick users into clicking, leading to unintended actions on the web application (e.g., money transfers or configuration changes).
- An `<img>` tag can automatically send a request to the application’s URL when the page loads, without requiring the user to click any link.

$${\color{green}Common \space Vulnerabilities}$$

- CSRF can exploit applications like firewall management consoles that rely on cookie-based session authentication.
- Attacks can be executed through GET-accessible URLs embedded in HTML pages or emails, automatically triggering actions when accessed.

$${\color{green}Testing \space Objectives}$$

Determine if it is possible to initiate requests on behalf of the user without their explicit action

# HOW TO TEST #

$${\color{green}Check \space Session \space Management}$$

- If the application’s session management relies on cookies or automatically sent browser authentication information, the application may be vulnerable to CSRF.
- Resources accessed via GET requests are easily vulnerable, but POST requests are also not fully secure as they can be automated using JavaScript.

$${\color{green}Testing \space with \space POST \space Requests}$$

- Create an HTML page with malicious code that automatically submits a POST request to the target application.
- Example:
  
![image](https://github.com/user-attachments/assets/20b1443f-d27c-49b5-a55f-7af12587cc8b)

- Host this HTML page on a malicious or third-party website and send the link to the victim, who will unknowingly trigger the request.

$${\color{green}Testing \space with \space JSON Data}$$

- For applications using JSON for browser-server communication, use a self-submitting form with JSON payloads and change the encoding type to `text/plain` to send data as-is.
- Example exploit code:

  ![image](https://github.com/user-attachments/assets/86122ae4-9665-47e4-8edb-dc133c1bd1bf)

- When sent as a POST request, the server will process the name and password fields, while ignoring unnecessary data.

=> If the requests are accepted without the user’s actual interaction, the application is vulnerable to CSRF and needs to be made more secure. Common mitigation strategies include adding CSRF tokens to requests or re-authenticating the user before executing critical actions.
