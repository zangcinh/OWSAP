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
- Các phiên bản phát triển, kiểm thử, kiểm thử chấp nhận người dùng (UAT), và phiên bản staging của các trang web

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

- `inurl`: when followed by a particular string, returns results with that sequence of characters in the URL.
- `allinurl`: is used to search for webpages that contain multiple specific words in the URL.
- `intext`: when followed by the searcher's chosen word or phrase returns files with the string anywhere in the text.
- `allintext`: searches for webpages that contain multiple specific words in the pages.
- `related`: looks for websites that are related to a particular domain, such as techtarget.com.
- `intitle`: looks for webpages that contain a specific word in the page title.
- `allintitle`: searches for webpages that contain multiple specified words in the title.

$${\color{green}Search \space operator \space examples}$$

- **site:**: Get results from certain sites or domains.
Examples: `olympics site:nbc.com` and `olympics site:.gov`
- **link:**: Find pages that link to a certain page.
Example: `link:youtube.com`
- **related**: Find sites that are similar to a web address you already know.
Example: `related:time.com`
- **-** : When you use a dash before a word or site, it excludes sites with that info from your results. This is useful for words with multiple meanings, like Jaguar the car brand and jaguar the animal.
Examples: `jaguar speed -car` or `pandas -site:wikipedia.org`
- **"** : When you put a word or phrase in quotes, the results will only include pages with the same words in the same order as the ones inside the quotes. Only use this if you’re looking for an exact word or phrase, otherwise you’ll exclude many helpful results by mistake.
Example: `"imagine all the people"`
- **OR** : 	Find pages that might use one of several words.
Example: `marathon OR race`

$${\color{green}Viewing Cached Content}$$

The Google cache search tool will let you easily view cached pages and websites in Google's search index. You'll be able to view the content of the page as it was last cached using `cache`+`URL`

**1. What is Cache?**
- Search engine cache is a snapshot of a webpage that is stored by the search engine at the time it was crawled. Even if the webpage has been updated or removed, this cached version can still be accessed.

**2.Benefits of Viewing Cached Content**
- Access old content: You can view previous versions of a webpage, even if the content has changed or is no longer available on the official site.
- Recover information: If a webpage has been taken down or altered, using the cache can help you retrieve the original information.

**3.Using the `cache`: Operator in Search**
- The `cache`: operator allows you to search for and view the cached version of a specific webpage.
- How to use it: In Google’s search bar, type `cache`: followed by the URL of the page you want to view. For example: cache:www.example.com.

**4.Limitations**
- Not all search engines provide the ability to view cached content. This feature is most useful with Google.
- Limited version: The cache only stores the version of the page at the time it was crawled, so if the page has been updated, the cache won’t reflect the new content.

> **1. Bộ Nhớ Cache là Gì?**
> - Bộ nhớ cache của công cụ tìm kiếm là một bản sao của trang web được lưu trữ bởi công cụ tìm kiếm tại thời điểm nó thu thập dữ liệu. Khi một trang web được cập nhật hoặc bị xóa, bản sao này vẫn có thể được truy cập thông qua bộ nhớ cache.
>
> **2.Lợi Ích của Việc Xem Nội Dung Đã Lưu Trong Bộ Nhớ Cache**
> - Truy cập nội dung cũ: Bạn có thể xem các phiên bản trước đó của trang web, ngay cả khi nội dung đã thay đổi hoặc không còn tồn tại trên trang web chính thức.
> - Khôi phục thông tin: Nếu một trang web bị gỡ bỏ hoặc thay đổi, việc sử dụng bộ nhớ cache có thể giúp bạn khôi phục thông tin ban đầu.
>
> **3. Sử Dụng Toán Tử `cache`: trong Tìm Kiếm**
> - Toán tử `cache`: cho phép bạn tìm kiếm và xem phiên bản lưu trong bộ nhớ cache của một trang web cụ thể.
> - Cách sử dụng: Trong ô tìm kiếm của Google, bạn gõ `cache`: theo sau là URL của trang bạn muốn xem. Ví dụ: cache:www.example.com.

# GOOGLE HACKING OR DOCKING #

Google Hacking, also known as Dorking, involves using search operators creatively to uncover sensitive files and information. By chaining multiple search operators together, a tester can effectively find specific types of data that may not be easily accessible through regular searches. Although this technique is commonly associated with Google, it can also be used with other search engines, provided they support similar search operators.

**1.Search Operators**: These can be combined in various ways to locate sensitive information, such as configuration files, user credentials, or exposed directories.

**2.Google Hacking Database (GHDB)**: This is a valuable resource that provides pre-made search queries, known as "dorks," which are designed to uncover specific types of sensitive data. Categories in GHDB include:
- Footholds: Methods to gain initial access to a system.
- Files containing usernames: Documents that reveal usernames.
- Sensitive Directories: Directories that should not be publicly accessible.
- Web Server Detection: Identifying web server software and versions.
- Vulnerable Files: Files that may be exploited by attackers.
- Vulnerable Servers: Servers with known vulnerabilities.
- Error Messages: Pages displaying detailed error messages that may reveal sensitive information.
- Files containing juicy info: Documents with valuable information for attackers.
- Files containing passwords: Text files or logs containing password data.
Sensitive Online Shopping Info: Information related to online transactions that should remain confidential.

>**1.Toán tử tìm kiếm**: Có thể kết hợp theo nhiều cách khác nhau để xác định các thông tin nhạy cảm như tệp cấu hình, thông tin đăng nhập người dùng hoặc các thư mục bị lộ.
>
>**2.Google Hacking Database (GHDB)**:Đây là một nguồn tài nguyên quan trọng cung cấp các truy vấn tìm kiếm được chuẩn bị sẵn, được gọi là "dorks," được thiết kế để tìm ra các loại dữ liệu nhạy cảm cụ thể. Các danh mục trong GHDB bao gồm:
>- Footholds: Phương pháp để có được quyền truy cập ban đầu vào hệ thống.
>- Files containing usernames: Các tệp chứa tên người dùng.
>- Sensitive Directories: Các thư mục không nên được công khai.
>- Web Server Detection: Xác định phần mềm và phiên bản của máy chủ web.
>- Vulnerable Files: Các tệp có thể bị khai thác bởi kẻ tấn công.
>- Vulnerable Servers: Các máy chủ có lỗ hổng bảo mật đã biết.
>- Error Messages: Các trang hiển thị thông báo lỗi chi tiết có thể tiết lộ thông tin nhạy cảm.
>- Files containing juicy info: Các tài liệu chứa thông tin có giá trị đối với kẻ tấn công.
>- Files containing passwords: Các tệp văn bản hoặc nhật ký chứa dữ liệu mật khẩu.
>- Sensitive Online Shopping Info: Thông tin liên quan đến giao dịch trực tuyến cần được bảo mật.
