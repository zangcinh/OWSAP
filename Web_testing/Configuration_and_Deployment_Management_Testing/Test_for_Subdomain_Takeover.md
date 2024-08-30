
chưa xong

# OVERALL #

$${\color{green}Summary}$$

- Subdomain takeover occurs when an attacker gains control of a subdomain pointing to a non-existent or inactive resource due to DNS misconfiguration or improper verification by the service provider. This can lead to various attacks such as serving malicious content, phishing, or stealing sensitive information.

$${\color{green}Impact}$$

- Malicious Content: Serving harmful content.
- Phishing: Creating deceptive pages.
- Data Theft: Stealing session cookies or credentials.
- DNS Records Exploitation: Affecting A, CNAME, MX, NS, TXT records.

**Highest Risk:**
An NS (Name Server) subdomain takeover has the highest impact, potentially giving full control over the DNS zone and the victim's domain.

$${\color{green}GitHub}$$

- Scenario: Victim (victim.com) used GitHub for their development and had a DNS record (coderepo.victim.com) pointing to GitHub.
- Issue: After migrating their repository to another platform, the victim didn't remove the DNS record for coderepo.victim.com.
- Exploit: An attacker discovers that coderepo.victim.com is hosted on GitHub and claims it using GitHub Pages, gaining control of the subdomain.

$${\color{green}Expired \space Domain}$$

- Scenario: Victim (victim.com) used a CNAME record (www) pointing to another domain (www.victim.com → victimotherdomain.com).
- Issue: When victimotherdomain.com expires and becomes available for registration, the CNAME record is still present in victim.com’s DNS.
- Exploit: An attacker registers the expired domain (victimotherdomain.com) and gains control over the www subdomain of victim.com.

 
$${\color{green}Test \space Objectives}$$

- Enumerate Domains: Identify both old and current domains.
- Identify Misconfigurations: Find forgotten or misconfigured DNS records that could lead to subdomain takeover.

# HOW TO TEST #

$${\color{green}Black-Box \space Testing}$$

**1.Enumerate DNS Servers and Resource Records:**
- Use methods such as DNS enumeration with a list of common subdomains, DNS brute force, or search engines and other OSINT (Open Source Intelligence) sources.

**2. Using the `dig` Command to check for DNS Responses That Warrant Further Investigation:**

- NXDOMAIN: Indicates that the domain name does not exist.
- SERVFAIL: Indicates that the DNS server encountered an error processing the request.
- REFUSED: Indicates that the request was refused by the DNS server.
- no servers could be reached: Indicates that no connection could be made to the DNS server.

**3.Objectives:**
- Identify forgotten or misconfigured domains that could lead to subdomain takeover vulnerabilities.
