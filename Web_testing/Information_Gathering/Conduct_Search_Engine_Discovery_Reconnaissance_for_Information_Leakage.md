# OVERALL #
$${\color{green}Summary}$$

**1. How search engines work**
   - Crawling:
       - Search bots (also known as spiders or crawlers) are automated programs that gather data from websites on the Internet.
       - They navigate through links from one page to another to discover and collect information from various websites.
       - Sitemaps also assist search bots in finding important pages on a website.
   - Indexing
       - After collecting data, bots index the content of webpages based on tags and attributes, such as the <TITLE> tag and meta tags.
       - The index is a database containing information about the content of webpages. Search engines use this index to quickly return relevant results when users perform searches.
         
**2. Managing content with `robots.txt`**
   - `robots.txt` file: This is a text file located in the root directory of a website that provides instructions to search bots about which pages or sections of the site they are not allowed to crawl.
   - If the `robots.txt` file lists certain pages, search bots will ignore these pages and not collect data from them.
     
**3. Reconnaissance using search engines**
   - `Direct methods`: Involve using search engines to query and retrieve indexed content from the search engine's cache, such as performing direct searches on Google.
   - `Indirect methods`: Involve gathering information from other sources such as forums, newsgroups, or bidding sites to learn about the configuration and design of a website or web application.
     
**4. Managing unwanted content**
   - If the `robots.txt` file is not updated or meta tags are not used correctly, search engines might index content that the website owner does not wish to make public.
   - `Search engines`: Provide tools and options to manage and remove unwanted content from the index, such as Google Search Console, where you can request content removal or adjust how search engines index your site.
     
> **1. Quá trình hoạt động của công cụ tìm kiếm**
>- Thu thập dữ liệu (Crawling):
>     - Robot tìm kiếm là chương trình tự động thu thập dữ liệu từ các trang web trên Internet. 
>     - Chúng duyệt qua các liên kết từ trang này sang trang khác để tìm và thu thập thông tin từ các trang web khác nhau. 
>     - Sơ đồ trang web (Sitemap) cũng giúp robot tìm kiếm các trang quan trọng trên trang web.
>- Chỉ mục (Indexing):
>     - Sau khi thu thập dữ liệu, các robot sẽ lập chỉ mục nội dung trang web dựa trên các thẻ và thuộc tính của trang, chẳng hạn như thẻ `<TITLE>` và các thẻ meta.
>     - Chỉ mục là cơ sở dữ liệu chứa thông tin về nội dung của các trang web. Công cụ tìm kiếm sử dụng chỉ mục này để nhanh chóng trả về kết quả khi người dùng thực hiện tìm kiếm.
>**2. Quản lý nội dung với `robots.txt`**
>- Tệp `robots.txt`: Đây là một tệp văn bản đặt tại thư mục gốc của trang web, chứa hướng dẫn cho các robot tìm kiếm về các trang hoặc phần của trang web mà chúng không được phép thu thập.
>- Nếu tệp `robots.txt` liệt kê các trang, robot tìm kiếm sẽ bỏ qua các trang đó và không thu thập dữ liệu từ chúng.
>**3. Thực hành trinh sát với công cụ tìm kiếm**
>- Các phương pháp trực tiếp: Bao gồm việc sử dụng công cụ tìm kiếm để truy vấn và tìm kiếm các chỉ mục và nội dung từ bộ nhớ đệm của công cụ tìm kiếm, chẳng hạn như tìm kiếm trực tiếp trên Google.
>- Các phương pháp gián tiếp: Liên quan đến việc thu thập thông tin từ các nguồn khác như diễn đàn, nhóm tin tức, hoặc trang web đấu thầu để tìm hiểu thông tin về cấu hình và thiết kế của trang web hoặc ứng dụng web.
>**4. Quản lý nội dung không mong muốn**
>- Nếu tệp `robots.txt` không được cập nhật hoặc các thẻ meta không được sử dụng, có thể xảy ra trường hợp công cụ tìm kiếm lập chỉ mục nội dung mà chủ sở hữu trang web không muốn công khai.
>- Công cụ tìm kiếm: Cung cấp các công cụ và tùy chọn để quản lý và xóa nội dung không mong muốn khỏi chỉ mục, chẳng hạn như Google Search Console, nơi bạn có thể yêu cầu xóa nội dung hoặc thay đổi cách công cụ tìm kiếm lập chỉ mục trang của bạn.

$${\color{green}More  \space about \space robots.txt}$$

`The robots.txt file is designed to guide search bots on which pages or parts of a website they should not crawl. Here’s why search bots will ignore the pages listed in the robots.txt file`
**1. Guiding Search Bots**
   - The `robots.txt` file contains directives written in a specific format to instruct search bots on how to crawl data. These directives include:
       - `User-agent`: Specifies the particular bot to which the following directives apply
       - `Disallow`: Defines paths or directories that the bot is not permitted to crawl.
         
       **Example**
     
          >User-agent: *
          >Disallow: /private/
        
     
In this example, all search bots (indicated by `*`) are instructed not to crawl data from the `/private/` directory.

**2. Adhering to Rules**
   - Most search bots follow the rules in the robots.txt file. This ensures that:
       - Privacy and Security: Website owners can request bots not to collect data from sensitive or non-public parts of their site.
       - Server Load Management: By limiting crawling to unnecessary parts, website owners can reduce the load on their servers.
         
**3. Ethical and Cooperative Principles**
   - Ethical Principles: Search bots are designed to adhere to the instructions in the `robots.txt file`, reflecting a cooperative relationship between search engines and website administrators.
   - Cooperation: Search engines like Google, Bing, and Yahoo! generally follow the directives in the `robots.txt` file to maintain a positive relationship with website owners.
     
**4. Potential to Ignore `robots.txt`**
   - Some Bots May Ignore: Not all search bots follow the rules in the `robots.txt` file. Some search engines or bots might ignore this file and crawl data from listed pages if they do not adhere to the directives.
   - Malicious Bots: Malicious search engines or non-compliant bots might not follow the instructions in `robots.txt`.

> Tệp robots.txt được thiết kế để hướng dẫn các robot tìm kiếm về các trang hoặc phần của trang web mà chúng không nên thu thập dữ liệu.
> 
> **1. Hướng dẫn Robot Tìm Kiếm**
>- Tệp `robots.txt` chứa các chỉ thị được viết theo định dạng cụ thể để hướng dẫn các robot tìm kiếm về việc thu thập dữ liệu. Các chỉ thị này có dạng:
>    - `User-agent`: Chỉ định robot cụ thể mà các chỉ thị tiếp theo áp dụng.
>    - `Disallow`: Xác định các đường dẫn hoặc thư mục mà robot không được phép thu thập dữ liệu
>      
> **2. Tuân Thủ Quy Tắc**
> Hầu hết các robot tìm kiếm tuân theo các quy tắc trong tệp `robots.txt`. Điều này giúp đảm bảo rằng:
>- Tôn trọng quyền riêng tư và bảo mật: Chủ sở hữu trang web có thể yêu cầu các robot không thu thập dữ liệu từ các phần nhạy cảm hoặc không muốn công khai của trang web.
>- Quản lý tải trên máy chủ: Bằng cách giới hạn việc thu thập dữ liệu từ các phần không cần thiết, chủ sở hữu có thể giảm tải trên máy chủ của mình.
>  
> **3. Nguyên Tắc Đạo Đức và Hợp Tác**
>- Nguyên tắc đạo đức: Các robot tìm kiếm được thiết kế để tuân theo các hướng dẫn từ tệp `robots.txt`, thể hiện sự hợp tác giữa các công cụ tìm kiếm và các quản trị viên web.
>- Hợp tác: Các công cụ tìm kiếm như Google, Bing, và Yahoo! thường tuân theo các chỉ thị trong tệp `robots.txt` để duy trì mối quan hệ tích cực với các chủ sở hữu trang web.
>  
> **4.Khả Năng Bỏ Qua `robots.txt`**
>- Một số robot không tuân theo: Không phải tất cả các robot tìm kiếm đều tuân theo các quy tắc trong tệp `robots.txt`. Một số công cụ tìm kiếm hoặc robot có thể bỏ qua tệp này và thu thập dữ liệu từ các trang bị liệt kê nếu chúng không tuân thủ các chỉ thị.
>- Các công cụ tìm kiếm độc hại: Các công cụ tìm kiếm độc hại hoặc các robot không hợp lệ có thể không tuân theo các chỉ thị trong `robots.txt`.

$${\color{green}Test \space Objectives}$$

`The objective is to identify any sensitive design and configuration information related to the application, system, or organization that may be exposed either:`

**1.Directly** :Through the organization’s own website or online resources.

**2.Indirectly**: Via third-party services or external platforms that interact with or host aspects of the organization’s system.

>`Mục tiêu là xác định bất kỳ thông tin nhạy cảm nào về thiết kế và cấu hình liên quan đến ứng dụng, hệ thống, hoặc tổ chức có thể bị lộ`
>
>**1.Trực tiếp**: Thông qua trang web của tổ chức hoặc các nguồn tài nguyên trực tuyến của chính tổ chức
>
>**2.Gián tiếp**: Thông qua các dịch vụ của bên thứ ba hoặc các nền tảng bên ngoài có tương tác hoặc lưu trữ các khía cạnh của hệ thống của tổ chức.
>
>

# HOW TO TEST #

Use a search engine to search for potentially sensitive information. This may include:
- network diagrams and configurations
- archived posts and emails by administrators or other key staff
- logon procedures and username formats
- usernames, passwords, and private keys
- third-party, or cloud service configuration files
- revealing error message content
- development, test, User Acceptance Testing (UAT), and staging versions of sites

>Sử dụng công cụ tìm kiếm để tìm kiếm các thông tin có thể nhạy cảm. Điều này có thể bao gồm:
>- Sơ đồ mạng và cấu hình
>- Các bài đăng và email lưu trữ của quản trị viên hoặc các nhân viên chủ chốt khác
>- Quy trình đăng nhập và định dạng tên người dùng
>- Tên người dùng, mật khẩu và khóa riêng tư
>- Tệp cấu hình dịch vụ của bên thứ ba hoặc dịch vụ đám mây
>- Nội dung của thông báo lỗi tiết lộ thông tin
>- Các phiên bản phát triển, kiểm thử, kiểm thử chấp nhận người dùng (UAT), và phiên bản staging của các trang web

# SEARCH ENGINES #

- [Baidu](https://www.baidu.com/) from China
- [Bing](https://www.bing.com/) by Microsoft. Support [advanced search keywords](https://support.microsoft.com/en-us/topic/advanced-search-keywords-ea595928-5d63-4a0b-9c6b-0b769865e78a)
- [binsearch.info](https://binsearch.info/) for binary Usenet newsgroups
- [Common Crawl(https://commoncrawl.org/),"an open repository of web crawl data that can be accessed and analyzed by anyone"
- [DuckDuckGo](https://duckduckgo.com/), a privacy-focused search engine that compiles results from many different sources. Supports [search syntax](https://duckduckgo.com/duckduckgo-help-pages/results/syntax/)
- [Google](https://www.google.com/)
- [Internet Archive Wayback Machine](https://web.archive.org/), “building a digital library of Internet sites and other cultural artifacts in digital form.”
- [Startpage](https://www.startpage.com/),a search engine that uses Google’s results without collecting personal information through trackers and logs
- [Shodan](https://www.shodan.io/),a service for searching Internet-connected devices and services. Usage options include a limited free plan as well as paid subscription plans.

# Search Operators #

A search operator -- sometimes referred to as a search parameter -- is a character or string of characters used in a search engine query to narrow the focus of the search.

$${\color{green}What \space are \space some \space types \space of  \space search \space operators?}$$

The most common search operators are Boolean relationships, including AND, OR and NOT, as well as simple wildcard operators, like an asterisk, parentheses or quotation marks, which indicate the searcher is looking for an exact match. Search engines typically provide a variety of advanced search operators designed to provide powerful search capabilities.
>Các toán tử tìm kiếm phổ biến nhất là các mối quan hệ Boolean, bao gồm AND, OR và NOT, cũng như các toán tử ký tự đại diện đơn giản, như dấu hoa thị (*), dấu ngoặc đơn hoặc dấu ngoặc kép, để chỉ ra rằng người tìm kiếm đang tìm kiếm một kết quả chính xác. Các công cụ tìm kiếm thường cung cấp một loạt các toán tử tìm kiếm nâng cao được thiết kế để cung cấp khả năng tìm kiếm mạnh mẽ.

- `site`: is an operator that when followed by a website or domain, without a space, returns files located there.
- `filetype`: when followed by a file extension, such as DOC, PDF, XLS and INI, returns files of the specified type. Multiple file types can be searched for simultaneously by separating extensions with the vertical line symbol, as in the query filetype:DOC|PDF. The ext: operator, short for file extension, performs the same job.
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
