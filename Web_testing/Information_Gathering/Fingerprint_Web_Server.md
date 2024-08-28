# OVERALL #

$${\color{green} Definition}$$	

Fingerprinting a Web Server is the process of identifying the specific software and version of a web server running on a target system. This information is crucial for attackers and security professionals alike because it helps them understand the potential vulnerabilities and configuration specifics of the server, which could be exploited or need to be secured.

>Fingerprint Web Server là quá trình xác định phần mềm và phiên bản cụ thể của máy chủ web đang chạy trên một hệ thống mục tiêu. Thông tin này rất quan trọng đối với cả kẻ tấn công và các chuyên gia bảo mật vì nó giúp họ hiểu rõ các lỗ hổng tiềm ẩn và cấu hình cụ thể của máy chủ, từ đó có thể bị khai thác hoặc cần được bảo vệ

$${\color{green}Test \space Objectives}$$

**1.Identify Vulnerabilities**:Knowing the exact version of a web server allows you to check for known vulnerabilities that can be exploited.

**2.Tailored Attacks or Security Measures**: Attackers can use this information to craft specific exploits, while defenders can use it to apply relevant security patches and configurations.

**3.Understand Server Configuration**: Fingerprinting can also provide insights into how the server is configured, including supported modules, technologies, and security mechanisms in place.

>**1.Xác định lỗ hổng bảo mật**: Biết được phiên bản chính xác của máy chủ web giúp bạn kiểm tra các lỗ hổng đã biết có thể bị khai thác.
>
>**2.Tấn công hoặc bảo mật tùy chỉnh**: Kẻ tấn công có thể sử dụng thông tin này để tạo ra các cuộc tấn công cụ thể, trong khi những người phòng thủ có thể sử dụng để áp dụng các bản vá bảo mật và cấu hình phù hợp.
>
>**3.Hiểu cấu hình máy chủ**:  Fingerprinting cũng có thể cung cấp thông tin chi tiết về cách máy chủ được cấu hình, bao gồm các mô-đun hỗ trợ, công nghệ và cơ chế bảo mật.

# BANNER GRABBING #

$${\color{green}Definition}$$

Banner grabbing is a technique used to gather information about the software running on a server, such as web servers, FTP servers, and SSH servers. This information, called "banners", often includes details like the software version, operating system, and the services running on the server.

This information is valuable because:
- **Defenders** (like security professionals) use it to understand what software and services are running on their systems, so they can secure them and reduce the chances of an attack.
- **Attackers** use it to find weaknesses in the software or services, making it easier to exploit vulnerabilities.
  
There are two ways to perform banner grabbing:
- **Active Banner Grabbing**: This involves directly connecting to a server and sending it a request. The server responds with its banner, which the attacker or defender can analyze.
- **Passive Banner Grabbing**: Instead of directly interacting with the server, this method involves using tools that observe and analyze data passing over the network. This allows the attacker or defender to gather information without alerting the server.

>Banner grabbing là một kỹ thuật được sử dụng để thu thập thông tin về phần mềm đang chạy trên máy chủ, chẳng hạn như máy chủ web, máy chủ FTP và máy chủ SSH. Thông tin này, được gọi là "banners," thường bao gồm chi tiết như phiên bản phần mềm, hệ điều hành, và các dịch vụ đang chạy trên máy chủ.
>Thông tin này rất quý giá vì:
>- **Người bảo vệ** (như các chuyên gia bảo mật) sử dụng nó để hiểu phần mềm và dịch vụ nào đang chạy trên hệ thống của họ, từ đó có thể bảo mật và giảm nguy cơ bị tấn công.
>- **Kẻ tấn công** sử dụng nó để tìm ra những điểm yếu trong phần mềm hoặc dịch vụ, làm cho việc khai thác lỗ hổng dễ dàng hơn.
>  
>Có hai cách thực hiện banner grabbing:
>- **Banner Grabbing Chủ Động**: Phương pháp này bao gồm việc kết nối trực tiếp với máy chủ và gửi một yêu cầu. Máy chủ phản hồi với banner mà người tấn công hoặc người bảo vệ có thể phân tích.
>- **Banner Grabbing Thụ Động**: Thay vì tương tác trực tiếp với máy chủ, phương pháp này sử dụng các công cụ để quan sát và phân tích dữ liệu truyền qua mạng. Điều này cho phép thu thập thông tin mà không làm máy chủ biết được.

$${\color{green}Active \space Banner \space Grabbing}$$

Active banner grabbing involves sending specially crafted packets to a target server and then analyzing the responses to gather information about the server's software and operating systems

**HOW ACTIVE BANNER GRABBING WORKS**

1. Sending Packets:
- You send specific types of data requests to the target server. These packets are designed to elicit a response from the server that includes information about the software and version it is running
2. Analyzing Responses:
- The server responds with information in the form of banners. These banners can include details about the software, version numbers, and sometimes even the operating system.
3. Gathering Critical Information:
- By analyzing these responses, you can determine what services are running on the server and their versions. This information is valuable because it can reveal potential vulnerabilities or weaknesses in the software.

**RISKS AND TOOLS**

1. Risks:
- If a server reveals information about insecure or outdated software through its banners, it can attract attention from attackers who may exploit these vulnerabilities.
2. Tools:
- [Wget](https://www.gnu.org/software/wget/): This tool is often used to download files from a server. It can also help in active banner grabbing by connecting to the server and retrieving banner information.
- [Dmitry](https://github.com/jaygreig86/dmitry/): This tool is used for port scanning and retrieving banners. It helps by scanning open ports on the target network and gathering information about the software and versions running on those ports.

$${\color{green}Passive \space Banner \space Grabbing}$$

Passive banner grabbing is a technique used to collect information about network services running on a system without performing any actions that could be detected by the target system. Instead of sending active requests to the server and analyzing responses (as in active techniques), this method often relies on analyzing existing network traffic to identify service and application details.

**HOW PASSIVE BANNER GRABBING WORKS**

1. Monitoring Network Traffic: Instead of sending requests to services, passive banner grabbing uses network traffic analysis tools (such as Wireshark) to monitor and analyze traffic that has already passed through the network.
2. Packet Analysis: These analysis tools collect information from packets traveling over the network. These packets may contain banner data or information about running services.
3. Service Identification: Based on this information, system administrators or security analysts can determine which services and applications are running on the target server.

**RISKS AND TOOLS**

1. Risks:
- Sensitive Information: Banner data may contain sensitive information such as software versions, operating systems, and service configurations, which can help potential attackers exploit known vulnerabilities.
- Lack of Security: If information about services and software versions is exposed, it can assist attackers in identifying weaknesses in the system.
3. Tools
- [Wireshark](https://www.wireshark.org/): A popular network traffic analysis tool that helps monitor and analyze packets.
- [tcpdump](https://www.tcpdump.org/): A powerful command-line tool for capturing network packets.
- [NetworkMiner](https://www.netresec.com/?page=NetworkMiner): A comprehensive network forensic analysis tool that can collect and analyze information from network traffic.

>Passive banner grabbing là kỹ thuật thu thập thông tin về các dịch vụ mạng đang chạy trên hệ thống mà không thực hiện bất kỳ hành động nào có thể bị phát hiện bởi hệ thống mục tiêu. Thay vì gửi các yêu cầu chủ động đến máy chủ và phân tích phản hồi (như trong kỹ thuật chủ động), phương pháp này thường dựa vào việc phân tích lưu lượng mạng hiện có để nhận diện các thông tin dịch vụ và ứng dụng.
>
>**Cách hoạt động**
>
>1.Theo dõi Lưu lượng Mạng: Thay vì gửi yêu cầu đến các dịch vụ, kỹ thuật passive banner grabbing sử dụng các công cụ phân tích lưu lượng mạng (như Wireshark) để theo dõi và phân tích lưu lượng mạng đã được truyền qua mạng.
>
2.Phân tích Gói Tin: Các công cụ phân tích này sẽ thu thập thông tin từ các gói tin đang truyền tải qua mạng. Những gói tin này có thể chứa các dữ liệu banner hoặc thông tin về các dịch vụ đang chạy.

>3.Nhận diện Dịch vụ: Dựa trên các thông tin này, người quản trị hệ thống hoặc nhà phân tích bảo mật có thể xác định các dịch vụ và ứng dụng đang hoạt động trên máy chủ mục tiêu.
>
>**Rủi ro**
>
>1.Thông tin Nhạy cảm: Dữ liệu banner có thể chứa thông tin nhạy cảm như phiên bản phần mềm, hệ điều hành, và cấu hình dịch vụ, giúp kẻ tấn công tiềm năng khai thác các lỗ hổng đã biết.
>
>2.Thiếu An toàn: Nếu thông tin về các dịch vụ và phiên bản phần mềm được công khai, có thể giúp kẻ tấn công xác định các điểm yếu trong hệ thống.
>
>**Công cụ**
>
>1.Wireshark: Công cụ phân tích lưu lượng mạng phổ biến, giúp theo dõi và phân tích gói tin.
>
>2.tcpdump: Công cụ dòng lệnh mạnh mẽ để bắt gói tin mạng.
>
>3.NetworkMiner: Công cụ phân tích mạng mạnh mẽ, có khả năng thu thập và phân tích thông tin từ lưu lượng mạng.

# SENDING MALFORMED REQUESTS #

$${\color{green}Definition \space and \space purpose}$$

- Sending Malformed Requests: This involves sending HTTP requests that do not conform to standard formats or contain errors to a web server. These requests may include invalid HTTP methods, incorrectly formatted URLs, or malformed headers.
- Purpose: The goal is to force the server to return default error messages, which can reveal information about the server, software version, and configuration. This helps in identifying the server and its details, which attackers might use to discover vulnerabilities.

>Gửi yêu cầu sai lệch (Malformed Requests): Là việc gửi các yêu cầu HTTP không tuân theo chuẩn hoặc có cấu trúc sai đến máy chủ web. Những yêu cầu này có thể chứa các phương thức không hợp lệ, URL sai định dạng, hoặc header không đúng.
>
>Mục đích: Nhằm ép buộc máy chủ trả về các thông báo lỗi mặc định, qua đó thu thập thông tin về máy chủ, phiên bản phần mềm, và cấu hình. Đây là một cách để xác định máy chủ và các chi tiết mà kẻ tấn công có thể sử dụng để tìm ra lỗ hổng.

$${\color{green}How \space it \space works}$$

- When sending malformed requests, the server responds with error messages. Standard error messages (such as 400, 403, 404, 500) can reveal:
  - Web Server Type: Apache, Nginx, IIS, etc.
  - Server Version: For example, Apache/2.4.41 (Ubuntu).
  - Operating System Details: The OS running the server, such as Ubuntu or Windows Server.
  - Security Configuration Details: Some error messages might reveal information about security configurations or directory structures.

$${\color{green}Common \space Errors}$$

- 400 Bad Request: Occurs when the request is improperly formatted or unrecognized by the server. This error can sometimes reveal the type of server.
- 404 Not Found: A page not found error might reveal directory structures and server details if not customized.
- 500 Internal Server Error: An internal server error due to improper request handling. It often contains information about the server software and environment.

$${\color{green}Tools}$$

- Burp Suite: Used to customize HTTP requests and analyze detailed server responses.
- [cURL](https://curl.se/): Allows sending HTTP requests from the command line to test server responses.
- Netcat (nc): Sends custom requests over TCP to HTTP ports.

# AUTOMATED SCANNING TOOLS #

$${\color{green}Definition}$$

Automated scanning is a type of vulnerability scanning in which systems or applications are scanned using automated tools. This process is usually performed by vulnerability management software or vulnerability management services. 
Automated Scanning tools have the forte of auditing, logging, threat modeling, reporting, and remediation

$${\color{green}Types \space of \space Automated \space Scanning \space Tools}$$

**1.Network Scanners:**

- [Nmap](https://nmap.org/): A powerful tool for network discovery and security auditing. It can identify open ports, services, and versions, and detect vulnerabilities.
- [Nessus](https://www.tenable.com/products/nessus): A comprehensive vulnerability scanner that detects known vulnerabilities and misconfigurations across a network.
- [OpenVAS](https://www.openvas.org/): An open-source vulnerability scanner and management tool.

**2.Web Application Scanners:**

- [OWASP ZAP](https://www.zaproxy.org/) (Zed Attack Proxy): A popular tool for finding vulnerabilities in web applications. It includes features like automated scanners and passive scanning.
- Burp Suite: Provides a suite of tools for web application security testing, including automated scanning, crawling, and manual testing.
- [Acunetix](https://www.acunetix.com/): A commercial tool that scans web applications for vulnerabilities like SQL injection, XSS, and more.

**3.Vulnerability Scanners:**

- [Qualys](https://www.qualys.com/): A cloud-based vulnerability management tool that scans for a wide range of vulnerabilities and provides detailed reports.
- Rapid7 Nexpose: Provides real-time vulnerability assessment and management.

**4.Configuration Scanners:**

- [Lynis](https://cisofy.com/lynis/): An open-source security auditing tool for Unix-based systems. It performs checks on system configuration and security settings.
- [CIS-CAT](https://www.cisecurity.org/cybersecurity-tools/cis-cat-pro): Scans for compliance with CIS Benchmarks and best practices.
