# DEFINITION #
$${\color{green}What \space is \space a \space web \space applicatiton \space security \space test? \space(WAST)}$$

Web application security helps identify vulnerabilities that could lead to data breaches, malware attcks, access control issues,compromising safety. The application's code is analyzed to find vulnerabilities like XSS, SQL injections, privilege escalation, broken access control, and more.

> Kiểm tra bảo mật ứng dụng web giúp xác định các lỗ hổng có thể dẫn đến vi phạm dữ liệu, tấn công phần mềm độc hại, các vấn đề kiểm soát truy cập, làm ảnh hưởng đến sự an toàn. Mã nguồn của ứng dụng được phân tích để tìm các lỗ hổng như XSS, SQL injection, leo thang đặc quyền, kiểm soát truy cập bị phá vỡ và hiều vấn đề khác.

$${\color{green}What \space are \space the \space three \space types \space of \space web \space application \space testing?}$$

The three typpes of web app testing are black box, gray box and white box testing. Black box tests are conducted blindly with only publicly available information, gray box tests with some target information, and in a white box test, the tester goes very in-depth and knows all the details about the target.

> Có 3 loại kiểm tra ứng dụng web là kiểm thủ black box, gray box và white box. Black box được thực hiện mà không có thông tin nội bộ, chỉ dựa trên thông tin công khai. Gray box đượcc thực hiện với một số thông tin về mục tiêu. White box thì người kiểm thử sẽ đi rất sâu và biết tất cả các chi tiết về mục tiêu

$${\color{green}Types \space of \space WAST}$$	
1. Static Appplication Security Testing (SAST) is a security measure integrated into development cycle before application deployment. [Bandit](https://www.jit.io/resources/appsec-tools/how-to-run-a-sast-test-with-bandit-and-jit) is one example of this measure. SAST can be automated and run during the build process to ensure security measures are in place.[Best SAST tools](https://www.jit.io/resources/appsec-tools/best-sast-tools)analyze the application's code and identify potential vulnerabilities without the application needing to run. They look for vulnerabilities like SQL injection, cross-site scripting (XSS), and cross-site request forgery (CSRF).  

> Kiểm thử bảo mật ứng dụng tĩnh (SAST) là một biện pháp bảo mật được tích hợp vào chu kỳ phát triển trước khi triển khai ứng dụng. Bandit là một ví dụ về biện pháp này. SAST có thể được tự động hóa và chạy trong quá trình build để đảm bảo các biện pháp bảo mật đã được áp dụng. Các công cụ SAST tốt nhất sẽ phân tích mã nguồn của ứng dụng và xác định các lỗ hổng tiềm ẩn mà không cần ứng dụng phải chạy. Chúng tìm kiếm các lỗ hổng như SQL injection, cross-site scripting (XSS), và cross-site request forgery (CSRF).

2. Dynamic Application Security Testing (DAST) is a tool that simulates real-world attacks on an application and identifies potential vulnerabilities. They are used during the testing phase of SDLC to detect security flaws. 
Common DAST tools include OWASP ZAP and Legitify by Legit Labs. These tools can identify vulnerabilities in application configuration that are absent in the source code. They can also detect runtime issues like misconfigured servers.
![image](https://github.com/user-attachments/assets/98f891ec-dbe2-454e-b282-0196f09c2589)

> Kiểm thử bảo mật ứng dụng động (DAST) là một công cụ mô phỏng các cuộc tấn công thực tế vào ứng dụng và xác định các lỗ hổng tiềm ẩn. Chúng được sử dụng trong giai đoạn kiểm thử của vòng đời phát triển phần mềm (SDLC) để phát hiện các lỗi bảo mật. Các công cụ DAST phổ biến bao gồm OWASP ZAP và Legitify của Legit Labs. Những công cụ này có thể xác định các lỗ hổng trong cấu hình ứng dụng mà không có trong mã nguồn. Chúng cũng có thể phát hiện các vấn đề thời gian chạy như máy chủ cấu hình sai.

3. Runtime Application Self-Protection (RASP) constantly monitors the runtime environment of a web application to identify and prevent security threats. RASP has the ability to identify vulnerabilities that are not present in the source code. These vulnerabilities may only appear when the application is configured and running. RASP is the last line of defense that helps ensure the security of your web application.

> Bảo vệ ứng dụng tự động trong thời gian chạy (RASP) liên tục giám sát môi trường chạy của ứng dụng web để xác định và ngăn chặn các mối đe dọa bảo mật. RASP có khả năng nhận diện các lỗ hổng không có trong mã nguồn, những lỗ hổng này có thể chỉ xuất hiện khi ứng dụng được cấu hình và chạy. RASP là lớp phòng thủ cuối cùng giúp đảm bảo an ninh cho ứng dụng web.

4. A penetration test (pen test) is an authorized simulated attack performed on a computer system to evaluate its security. Penetration testers use the same tools, techniques, and processes as attackers to find and demonstrate the business impacts of weaknesses in a system. Penetration tests usually simulate a variety of attacks that could threaten a business. They can examine whether a system is robust enough to withstand attacks from authenticated and unauthenticated positions, as well as a range of system roles. With the right scope, a pen test can dive into any aspect of a system.

> Kiểm thử xâm nhập (pen test) là một cuộc tấn công giả lập được ủy quyền, thực hiện trên một hệ thống máy tính để đánh giá mức độ bảo mật của nó. Các chuyên gia kiểm thử xâm nhập sử dụng các công cụ, kỹ thuật và quy trình tương tự như kẻ tấn công để tìm và minh chứng các tác động kinh doanh của những điểm yếu trong hệ thống. Kiểm thử xâm nhập thường mô phỏng nhiều kiểu tấn công khác nhau có thể đe dọa đến doanh nghiệp. Họ có thể kiểm tra liệu hệ thống có đủ mạnh để chịu đựng các cuộc tấn công từ cả các vị trí đã được xác thực và chưa được xác thực, cũng như từ nhiều vai trò khác nhau trong hệ thống. Với phạm vi phù hợp, một cuộc kiểm thử xâm nhập có thể đi sâu vào bất kỳ khía cạnh nào của hệ thống.

$${\color{green}Check \space list \space OWSAP \space Website}$$	
1. Information Gathering
2. Configuration and Deployment Management Testing
3. Identity Management Testing
4. Authentication Testing
5. Authorization Testing
6. Session Management Testing
7. Input Validation Testing
8. Testing for Error Handling
9. Testing for Weak Cryptography
10. Business Logic Testing
11. Client-side Testing

