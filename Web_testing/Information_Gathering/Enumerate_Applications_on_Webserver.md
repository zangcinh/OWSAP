# OVERALL #

$${\color{green}Summary}$$

An essential step in testing for web application vulnerabilities is identifying which specific applications are hosted on a web server

1. Vulnerabilities and Attacks: Many web applications have vulnerabilities that attackers can exploit. Knowing exactly which applications are running on a server can help identify potential weaknesses.
2. Misconfiguration and Updates: Web applications can be misconfigured or not updated, especially when they are used only internally and thus receive less attention.
3. IP Address and Symbolic Names: In virtual server environments, multiple websites or applications might share the same IP address but have different symbolic names. This can make it challenging to identify all applications.
4. Incomplete Information: When provided with a list of IP addresses and symbolic names, there might be missing information, reducing the effectiveness of the security assessment.
5. Obscure URLs: Some applications might be located at hard-to-find or non-publicly advertised URLs, making detection and testing more difficult.

>1.Lỗ Hổng và Tấn Công: Nhiều ứng dụng web có lỗ hổng mà kẻ tấn công có thể khai thác. Việc biết chính xác các ứng dụng nào đang chạy trên máy chủ có thể giúp nhận diện các điểm yếu tiềm ẩn.
>
>2.Cấu Hình Sai và Cập Nhật: Các ứng dụng web có thể bị cấu hình sai hoặc không được cập nhật, đặc biệt là khi chúng được sử dụng chỉ trong nội bộ và không được chú ý nhiều.
>
>3.Địa Chỉ IP và Tên Biểu Tượng: Trong môi trường máy chủ ảo, nhiều trang web hoặc ứng dụng có thể sử dụng cùng một địa chỉ IP nhưng có các tên biểu tượng khác nhau. Điều này làm cho việc xác định tất cả các ứng dụng có thể gặp khó khăn.
>
>4.Thông Tin Không Đầy Đủ: Khi được giao một danh sách địa chỉ IP và tên biểu tượng, có thể có thông tin bị thiếu, làm giảm hiệu quả của việc kiểm tra bảo mật.
>
>5.URL Không Rõ Ràng: Một số ứng dụng có thể được đặt ở các URL không dễ phát hiện hoặc không được quảng cáo công khai, làm cho việc phát hiện và kiểm tra trở nên khó khăn hơn.

# HOW TO TEST #

**Web Application Discovery** is the process of identifying web applications hosted on a specific infrastructure, usually defined by a set of IP addresses or DNS names. This information is provided before conducting security assessments such as penetration testing or application assessments. The goal is to identify all accessible applications through the given targets.

>Quá trình khám phá ứng dụng web nhằm xác định các ứng dụng web trên một cơ sở hạ tầng cụ thể. Thông tin này thường là một tập hợp địa chỉ IP hoặc tên DNS, và được cung cấp trước khi thực hiện đánh giá bảo mật, như kiểm tra xâm nhập (penetration test) hoặc đánh giá ứng dụng. Mục tiêu là xác định tất cả các ứng dụng có thể truy cập được qua các mục tiêu đã cho.


$${\color{green}Factors \space Affecting \space Web \space Application \space Discovery}$$

**1.Different Base URLs**

- Typically, web applications are accessed at URLs like `http://www.example.com.` However, applications don't necessarily have to start at the root `/`. A single domain name can host multiple applications, such as:
  - http://www.example.com/url1
  - http://www.example.com/url2
  - http://www.example.com/url3
 
- These applications might not be visible on the main page, and without explicit knowledge of these specific URLs, they remain hidden. This method is often used when the owner wants to keep the application's address discreet without advertising it publicly.

**2.Non-Standard Ports:**

- While web applications commonly run on ports 80 (HTTP) and 443 (HTTPS), there's no strict rule for this. Applications can be hosted on any port, like `http://www.example.com:20000/`. Using non-standard ports can make applications less easily discoverable.

**3.Virtual Hosts:**

- DNS allows a single IP address to be associated with multiple domain names. For example:
  - IP `192.168.1.100` could be linked to `www.example.com`, `helpdesk.example.com`, and `webmail.example.com.`
- Each domain name can serve different content using virtual hosts, identified by the `Host` header in HTTP requests. If additional domain names are unknown, other web applications may go undetected.

>**1.URL Khác Nhau**
>- Mặc định, ứng dụng web thường truy cập tại URL như `http://www.example.com.` Tuy nhiên, không có quy định bắt buộc ứng dụng phải bắt đầu từ đường dẫn `/`. Một tên miền có thể chứa nhiều ứng dụng khác nhau, ví dụ:
>  - http://www.example.com/url1
> - http://www.example.com/url2
>  - http://www.example.com/url3
>- Các ứng dụng này có thể không hiển thị trên trang chủ, và nếu người kiểm tra không biết đến các URL cụ thể này, thì họ sẽ không tìm thấy chúng. Cách này thường được dùng nếu chủ sở hữu muốn giữ kín địa chỉ ứng dụng mà không cần quảng cáo công khai.
>  
>**2.Cổng Không Chuẩn (Non-standard Ports)**
>- Ứng dụng web thường hoạt động trên cổng 80 (HTTP) và 443 (HTTPS), nhưng không có gì bắt buộc điều này. Ứng dụng có thể sử dụng cổng bất kỳ, ví dụ như `http://www.example.com:20000`. Việc sử dụng cổng không chuẩn giúp ứng dụng không bị phát hiện dễ dàng.
>
>**3.Máy Chủ Ảo (Virtual Hosts)**
>- DNS cho phép một địa chỉ IP có thể liên kết với nhiều tên biểu tượng khác nhau, ví dụ:
>    - IP `192.168.1.100` có thể liên kết với `www.example.com`, `helpdesk.example.com`, và `webmail.example.com.`
>- Mỗi tên miền có thể phục vụ nội dung khác nhau thông qua máy chủ ảo (virtual host), sử dụng thông tin trong tiêu đề `Host` của HTTP. Nếu không biết đến các tên miền khác, thì rất khó để phát hiện thêm các ứng dụng web khác ngoài trang chính.

# APPROACHES TO ADDRESS ISUE #

$${\color{green}Non-standard \space URLs}$$

Identifying non-standard web applications (those with non-obvious URLs) can be challenging because there are no set rules or naming conventions that govern their existence. However, testers can use several strategies to gain insight into these hidden applications:

**1.Directory Browsing and Misconfiguration:**
- If the web server is improperly configured to allow directory browsing, it can expose directories and files, making hidden applications easier to spot. Vulnerability scanners can also assist by detecting such misconfigurations.

**2.Search Engine Indexing:**
- Hidden applications might be referenced on other web pages, and there’s a possibility they have been crawled and indexed by search engines. Testers can use search engine queries, such as `site:www.example.com`, to uncover URLs that point to these non-standard applications.

**3.Probing Likely URLs:**
- Testers can guess URLs that could be likely candidates for hidden or non-published applications. For instance, URLs like `https://www.example.com/webmail`, `https://webmail.example.com/`, or `https://mail.example.com/` might reveal webmail interfaces. Similarly, administrative interfaces, like a Tomcat admin panel, might be accessible at obscure URLs not linked elsewhere. A combination of dictionary-based searching or “intelligent guessing” and vulnerability scanners can help in discovering these hidden applications.

>Việc phát hiện các ứng dụng web có URL không chuẩn (các URL không rõ ràng hoặc không được công khai) rất phức tạp vì không có tiêu chuẩn cố định nào quy định về cách đặt tên cho các ứng dụng này. Tuy nhiên, có một số phương pháp mà người kiểm thử có thể sử dụng để tìm ra các ứng dụng ẩn này:
>
>**1.Duyệt Thư Mục và Cấu Hình Sai:**
>- Nếu máy chủ web bị cấu hình sai và cho phép duyệt thư mục, người kiểm thử có thể nhìn thấy các ứng dụng hoặc tập tin không được bảo vệ. Việc này có thể giúp lộ ra các ứng dụng không được công khai. Sử dụng các công cụ quét lỗ hổng bảo mật (vulnerability scanners) cũng có thể phát hiện ra các cấu hình sai này, cho phép truy cập vào các ứng dụng ẩn.
>
>- **2.Chỉ Mục của Công Cụ Tìm Kiếm:**
>- Các ứng dụng ẩn có thể được tham chiếu trên các trang web khác, và có khả năng chúng đã bị các công cụ tìm kiếm quét và lập chỉ mục. Người kiểm thử có thể dùng các truy vấn đặc biệt, như `site:www.example.com`, để tìm các URL tiềm ẩn của ứng dụng trên một trang web cụ thể. Các URL trả về có thể bao gồm những ứng dụng không hiển thị rõ ràng.
>
>**3.URL Khả Dụng:**
>- Thử đoán các URL có thể dẫn tới các ứng dụng không được công khai. Ví dụ, một giao diện webmail có thể được truy cập từ các URL như `https://www.example.com/webmail`, `https://webmail.example.com/`, hoặc `https://mail.example.com/`. Các giao diện quản trị cũng có thể nằm ở các URL ẩn mà không được liên kết ở đâu khác. Việc thử tìm kiếm theo từ điển (dictionary-style searching) hoặc “đoán thông minh” (intelligent guessing) có thể mang lại kết quả. Các công cụ quét lỗ hổng cũng hữu ích trong việc dò tìm các ứng dụng này

$${\color{green}Non-standard \space Ports}$$

When testing web applications, it's important to check for services running on non-standard ports. Unlike the typical web ports (80 for HTTP and 443 for HTTPS), applications might be running on any of the 64,000 available TCP ports. Here’s a step-by-step explanation of how to discover these applications:

**1.Using Port Scanners**

nmap is a powerful tool for this purpose. It can scan all 64,000 TCP ports to identify which ones are open and what services are running on them. Here’s how you use it:

![image](https://github.com/user-attachments/assets/b1eda00e-fa2a-4033-90ac-a415cad8a70a)
  - `-Pn`: Skips host discovery (assumes the host is up).
  - `-sT`: Performs a TCP connect scan (checks which ports are open).
  - `-sV`: Attempts to determine the version of the service running on each open port.
  - `-p0-65535`: Scans all ports from 0 to 65535.

**Output Interpretation**: The output will list open ports and the services running on them. For example:

![image](https://github.com/user-attachments/assets/515d2543-f6ab-41df-9c8b-bd9ca367244f)

Key Findings:
- Port 80: An Apache HTTP server is running.
- Port 443: An HTTPS server is likely running (needs confirmation).
- Port 901: A Samba SWAT web interface is present.
- Port 1241: An SSL-wrapped Nessus daemon is present.
- Port 3690: An unspecified service (could be identified later).
- Port 8000: Likely an HTTP server (confirmed with a telnet test).
- Port 8080: An Apache Tomcat server is running.

**2.Confirming Services**

- For ports where the service is not immediately clear:
  - Telnet: You can use `telnet` to connect and manually send HTTP requests to see if the service responds as an HTTP server.

![image](https://github.com/user-attachments/assets/aff32215-fcdd-4921-b86d-7cdcd6ca1c52)

Then, send an HTTP GET request:
    
![image](https://github.com/user-attachments/assets/699e154e-3d94-4ee5-8d7b-fd2f7bc8a917)

Response Example:

![image](https://github.com/user-attachments/assets/bee5095a-4499-44d2-836b-472256d6d5e0)

This confirms that the service on port 8000 is an HTTP server.

**3.Using Vulnerability Scanners**

Vulnerability scanners like Nessus can also detect services running on non-standard ports. They can:
- Identify HTTP[S] Services: Scan all ports to find web services.
- Assess Vulnerabilities: Check for known vulnerabilities in these services.
- Detect Popular Applications: Spot common applications or administrative interfaces that might not be obvious.

Example: Nessus, when configured to scan all ports, will identify web servers and their vulnerabilities, including SSL/TLS configurations and common application interfaces.
