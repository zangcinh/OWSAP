 # OVERALL #

$${\color{green}Summary}$$

Checking certain files on a web server that might accidentally reveal sensitive information. These files can show details about how the website is structured or how it works.

$${\color{green}Problems}$$

- Security Risks: These files might expose secrets or important details that can be used by attackers to exploit vulnerabilities.
- Uncover Hidden Paths: They can reveal hidden parts of the website or application that are not immediately visible.

 # ROBOTS #

$${\color{green}Definition}$$

Web Spiders, Robots, or Crawlers are automated programs that visit web pages and follow links to gather more content. They are commonly used by search engines to index websites or by security tools to analyze web applications.

$${\color{green}How \space they \space work}$$

1.Start at a Web Page: The robot begins by accessing a specific web page.
2.Follow Links: It automatically follows hyperlinks on that page to other pages within the same website.
3.Retrieve Content: It collects content from these pages, potentially traversing many levels of links.

$${\color{green}Example}$$

`robots.txt` file form [Facebook](https://facebook.com/robots.txt)

>User-agent: Amazonbot
>Disallow: /
>
>User-agent: Applebot-Extended
>Disallow: /

This section of the robots.txt file provides specific directives for various bots or crawlers, instructing them not to access any part of the website.

For example, the `User-Agent: Amazonbot` refers to the spider from Google while `User-Agent: Applebot-Extended` refers to a crawler from Microsoft. User-Agent: * in the example above are not allowed to access any part of the website

>Disallow: /*/plugins/*
>Disallow: /?*next=
>Disallow: /a/bz?
>Disallow: /ajax/
>Disallow: /album.php

`/*/plugins/*` (blocks access to any URL that includes /plugins/ in any segment)

`/?*next=` (blocks URLs with the query parameter next=)

`/a/bz?` (blocks URLs that match this exact path)

`/ajax/` (blocks access to URLs starting with /ajax/)

`/album.php` (blocks this exact file)

The `robots.txt` file is retrieved from the web root directory of the web server. For example, to retrieve the `robots.txt` from www.google.com using `wget` or `curl`:

First, download the robots.txt file using 'curl'
>curl -O -Ss http://www.google.com/robots.txt

Use `cat` to display the entire content of the file:
>cat robots.txt

![image](https://github.com/user-attachments/assets/413c08fa-14bf-42ae-8971-bcfda320beb6)

# ANALYZED ROBOTS.TXT USING GOOGLE WEBMASTER TOOLS #
 
Web site owners can use the Google “Analyze robots.txt” function to analyze the website as part of its [Google Webmaster Tools](https://search.google.com/search-console/welcome?hl=en&utm_source=wmx&utm_medium=deprecation-pane&utm_content=home). This tool can assist with testing and the procedure is as follows:

1.Sign into Google Webmaster Tools with a Google account.

2.On the dashboard, enter the URL for the site to be analyzed.

3.Choose between the available methods and follow the on screen instruction.

# META TAGS #

$${\color{green}Definition}$$

META tags are typically placed within the `<head>` section of an HTML document. They provide essential information about the webpage to browsers, search engines, and other web crawlers. Consistency in META tags across a website helps ensure that search engines and other crawlers can correctly interpret and index the content, regardless of where they enter the site.

$${\color{green}Key \space points}$$

**1. Consistency Across the Site:**

- Ensure that META tags such as `description`, `keywords`, and `robots` are consistent across your site to avoid discrepancies in how pages are indexed and presented.
- This consistency is particularly important if a crawler starts from a deep link rather than the web root. Consistent META tags ensure that the same rules apply throughout the site.

**2. Robots META Tag:**

- The `robots` META tag provides directives to web crawlers on how to index and follow links on the page.

![image](https://github.com/user-attachments/assets/a3f5f747-c435-4359-8609-6e752ce02685)

- Common values for the `robots` tag include:
  - `index`, `follow`: Allow indexing and following links.
  - `noindex`, `follow`: Do not index the page but follow links.
  - `index`, `nofollow`: Index the page but do not follow links.
  - `noindex`, `nofollow`: Do not index the page and do not follow links.
    
**3. Robots.txt vs. META Tags:**

- Both `robots.txt` and META tags control crawling and indexing, but they serve different purposes:
  - robots.txt: Used to control access to parts of your site for all crawlers, generally applied at the site level.
  - META Tags: Provide page-specific directives and can be used to override robots.txt settings for individual pages.

**4.Miscellaneous META Information Tags:**

Organizations often embed informational META tags in web content to support various technologies such as screen readers, social networking previews, search engine indexing, etc. Such meta-information can be of value to testers in identifying technologies used, and additional paths/functionality to explore and test.

The following meta information was retrieved from [The New York Times](https://www.nytimes.com/2024/08/27/books/review/at-war-with-ourselves-hr-mcmaster.html) via View Page Source:

![image](https://github.com/user-attachments/assets/31125690-d782-4d8c-9a27-c40a04a593d1)


# SITEMAPS #

A sitemap is a file where a developer or organization can provide information about the pages, videos, and other files offered by the site or application, and the relationship between them. Search engines can use this file to more intelligently explore your site. Testers can use `sitemap.xml` files to learn more about the site or application to explore it more completely.

>Sitemap là một tệp tin mà nhà phát triển hoặc tổ chức có thể cung cấp thông tin về các trang, video và các tệp tin khác của trang web hoặc ứng dụng, cũng như mối quan hệ giữa chúng. Các công cụ tìm kiếm có thể sử dụng tệp tin này để khám phá trang web của bạn một cách thông minh hơn. Các kiểm thử viên cũng có thể sử dụng các tệp tin `sitemap.xml` để tìm hiểu thêm về trang web hoặc ứng dụng và khám phá nó một cách đầy đủ hơn.

For example, this is the `sitemap.xml` of Google

![image](https://github.com/user-attachments/assets/e1a14c09-1285-455b-a1d3-b2fc120496f0)

# SECURITY.TXT #

Security.txt is an accepted standard for website security information that allows security researchers to report security vulnerabilities easily. There are multiple reasons this might be of interest in testing scenarios, including but not limited to:
- Identifying further paths or resources to include in discovery/analysis.
- Open Source intelligence gathering.
- Finding information on Bug Bounties, etc.
- Social Engineering.

The file may be present either in the root of the webserver or in the `.well-known/` directory. Ex:

- `https://example.com/security.txt`
- `https://example.com/.well-known/security.txt`

Here is a real world example retrieved from [Facebook](https://www.facebook.com/security.txt)

![image](https://github.com/user-attachments/assets/5a5217ea-3d95-4576-b15f-d3f450e9778b)

# HUMANS.TXT #

`humans.txt` is an initiative for knowing the people behind a website. It takes the form of a text file that contains information about the different people who have contributed to building the website. See humanstxt for more info. This file often (though not always) contains information for career or job sites/paths.

Here is a real world example retrieved from [Google](https://www.google.com/humans.txt)

![image](https://github.com/user-attachments/assets/4da4c3bb-87c5-494a-8ca8-58bb4d57d4ec)

# OTHER .well-known INFORMATION SOURCES #

There are other RFCs and Internet drafts which suggest standardized uses of files within the `.well-known/` directory.

# TOOLS #

- Browser (View Source or Dev Tools functionality)
- curl
- wget
- Burp Suite
- ZAP


