# TỔNG QUAN #
$${\color{green}Tổng \space quan}$$
     
 **1. Cách công cụ tìm kiếm hoạt động**
- Thu thập dữ liệu (Crawling):
     - Trình thu tập dữ liệu là chương trình tự động thu thập dữ liệu từ các trang web trên Internet. 
     - Chúng duyệt qua các liên kết từ trang này sang trang khác để tìm và thu thập thông tin từ các trang web khác nhau. 
    - Sơ đồ trang web (Sitemap) cũng giúp robot tìm kiếm các trang quan trọng trên trang web.
- Chỉ mục (Indexing):
     - Sau khi thu thập dữ liệu, các robot sẽ lập chỉ mục nội dung trang để các trang web có thể xuất hiện trong kết quả của công cụ tìm .
       
**2. robots.txt**
- Tệp `robots.txt`giúp quản lý lưu lượng thu thập dữ liệu của các công cụ tìm kiếm.
- File này dùng để
   -  Ngăn các trình thu thập thông tin truy cập vào các phần trong trang web mà bạn không muốn chúng thu thập thông tin
   - Yêu cầu các trình thu thập thông tin thu thập ít thông tin từ trang web của bạn hơn
   - Sắp xếp thứ tự thu thập thông 
  
**3. Thực hành**
- Trực tiếp: Sử dụng các công cụ tìm kiếm để tìm kiếm thông tin ( ví dụ: Google ).
- Gián tiếp: Tìm thông tin từ các nhóm, diễn đàn,... 

$${\color{green}Bổ \space sung \space về \space file \space robots.txt}$$

**1. Hướng dẫn Robot Tìm Kiếm**
- Tệp `robots.txt` chứa các chỉ thị để hướng dẫn các trình thu thập về việc thu thập dữ liệu. Các chỉ thị này có dạng:
    - `User-agent`: Chỉ định loại trình thu thập mà chỉ thị này áp dụng.
    - `Disallow`: Xác định các đường dẫn không được phép thu thập
    - `Allow`: Xác định các đường dẫn được phép thu thập
    - Siemap ( sơ đồ website ): URL sitemap của trang web

$${\color{green}Mục \space tiêu \space kiểm \space tra}$$

- Xác định bất kỳ thông tin nhạy cảm nào liên quan đến ứng dụng, hệ thống có thể bị lộ

**1.Trực tiếp**: Thông qua trang web của tổ chức 

**2.Gián tiếp**: Thông qua các dịch vụ của bên thứ ba 

# CÁCH KIỂM TRA #

Sử dụng công cụ tìm kiếm để tìm kiếm các thông tin có thể nhạy cảm bao gồm:
- Sơ đồ mạng và cấu hình
- Các bài đăng và email lưu trữ của quản trị viên hoặc các nhân viên quan trọng khác
- Quy trình đăng nhập và định dạng tên người dùng
- Tên người dùng, mật khẩu và khóa riêng tư
- Tệp cấu hình dịch vụ của bên thứ ba hoặc dịch vụ đám mây
- Nội dung của thông báo lỗi

# CÔNG CỤ TÌM  #

- [Baidu](https://www.baidu.com/) from China
- [Bing](https://www.bing.com/) by Microsoft. Support [advanced search keywords](https://support.microsoft.com/en-us/topic/advanced-search-keywords-ea595928-5d63-4a0b-9c6b-0b769865e78a)
- [binsearch.info](https://binsearch.info/) for binary Usenet newsgroups
- [Common Crawl(https://commoncrawl.org/),"an open repository of web crawl data that can be accessed and analyzed by anyone"
- [DuckDuckGo](https://duckduckgo.com/), a privacy-focused search engine that compiles results from many different sources. Supports [search syntax](https://duckduckgo.com/duckduckgo-help-pages/results/syntax/)
- [Google](https://www.google.com/)
- [Internet Archive Wayback Machine](https://web.archive.org/), “building a digital library of Internet sites and other cultural artifacts in digital form.”
- [Startpage](https://www.startpage.com/),a search engine that uses Google’s results without collecting personal information through trackers and logs
- [Shodan](https://www.shodan.io/),a service for searching Internet-connected devices and services. Usage options include a limited free plan as well as paid subscription plans.

# TOÁN TỬ TÌM KIẾM #

Là từ khóa, cú pháp đặc biệt giúp mở rộng khả năng của các truy vấn thông tin và có được kết quả cụ thể hơn 

$${\color{green}Một \space vài \space ví \space dụ \space về \space toán \space tử \space tìm \space kiếm}$$

- `site`: tìm kiếm thông tin, trang web nằm trên 1 tên miền cụ thể ( ví dụ: `https://www.facebook.com/ ` )
- `filetype`: tìm kiếm các file cụ thể như DOC, PDF, XLS, INI. Ví dụ tìm file excel (XLS) liên quan đến "climate change" sẽ sử dụng truy vấn `site:un.org filetype:xls "climate change"`

  ![image](https://github.com/user-attachments/assets/275d8c65-a246-41c5-b085-aed2dd455db1)

- `inurl`: trả về kết quả URL có chứa từ mà bạn cần tìm. Ví dụ: tìm các bài viết về bảo mật mà URL có chứa từ "security" trên trang `techcrunch.com`

![image](https://github.com/user-attachments/assets/9ad70d59-65cc-4b33-b1f2-17a6a7aa4b70)

- `allinurl`: tương tự như `inurl` hưng có thể kết hợp nhiều từ khóa hơn. Ví dụ

![image](https://github.com/user-attachments/assets/336eabdc-8eeb-4374-adba-7578dc6c8ee8)

- `intext`: tìm các bài viết trong trang có nội dung chứa từ cần tìm. Ví dụ:

  ![image](https://github.com/user-attachments/assets/c7ec8b9c-79d2-4baa-85d2-5c66b62745b1)

- `allintext`: tương tự như `intext` nhưng kết hợp được nhiều từ khóa. Ví dụ:

![image](https://github.com/user-attachments/assets/0195b46d-954c-452c-bc29-5a30431a250e)

- `related`: tìm các trang web có nội dung tương tự với 1 trang web cụ 
- `intitle`: tìm các bài viết trong tang có chưa từ cụ thể nào đó trong tiêu đề. Ví dụ:

![image](https://github.com/user-attachments/assets/c2d2ab69-0986-48a4-b759-ec70e9b25fd5)

- `allintitle`: tương tự như `intitle` nhưng kết hợp được nhiều từ khóa

$${\color{green}Xem \space nội \space dung \space bộ \space nhớ \space đệm}$$

Công cụ tìm kiếm bộ nhớ đệm của Google sẽ cho bạn xem các trang web đã được lưu trữ trong chỉ mục tìm kiếm của Google bằng cú pháp `cache` + `URL`

**1. Cache là gì**

-  Cache là vùng lưu trữ tạm thời để lưu trữ các dữ liệu như trang web, hình ảnh, video,... Mỗi lần truy cập vào một dữ liệu nào đó, trình duyệt sẽ tải chúng xuống từ máy chủ. KHi bạn truy cập lại cùng ` trang web ở lần tiếp theo, trình duyệt sẽ sử dụng bộ nhớ cache để lấy dự liệu nhanh hơn mà không phải tải lại lần nữa

# GOOGLE HACKING OR DOCKING #

Google Hacking, also known as Dorking, involves using search operators creatively to uncover sensitive files and information. By chaining multiple search operators together, a tester can effectively find specific types of data that may not be easily accessible through regular searches. Although this technique is commonly associated with Google, it can also be used with other search engines, provided they support similar search operators.

**1.Toán tử tìm kiếm**: Có thể kết hợp theo nhiều cách khác nhau để xác định các thông tin nhạy cảm như tệp cấu hình, thông tin đăng nhập người dùng hoặc các thư mục bị lộ.

**2.Google Hacking Database (GHDB)** : nguồn tài nguyên quan trọng trong việc tìm kiếm thông tin cụ thể:
- Footholds: truy vấn xác định điểm xâm nhập vào hệ thống
- Files containing usernames: Các tệp chứa tên người dùng.
- Sensitive Directories: Các thư mục nhạy cảm
- Web Server Detection: Xác định máy chủ web và cấu hình của nó
- Vulnerable Files: Các tệp tin dễ bị khai thác
- Vulnerable Servers: Các máy chủ có lỗ hổng bảo mật đã biết.
- Error Messages: Các trang hiển thị thông báo lỗi có thể tiết lộ thông tin nhạy cảm.
- Files containing juicy info: tệp chứa thông tin quan trọng
- Files containing passwords: các tệp có thể chứa mật khẩu
- Sensitive Online Shopping Info: Thông tin mua sắm trực tuyến có thể chứa các thông tin nhue thẻ tín dụng, địa chỉ giao hàng, thông tin khách 
