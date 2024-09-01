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

**1. DNS Enumeration:**
- Purpose: To find DNS servers and resource records (like subdomains) of the target domain (e.g., victim.com).
- Methods: Use tools and techniques like:
 - Using a dictionary of common subdomains to find existing ones.
 - Brute force to discover subdomains.
 - Gathering information from OSINT sources (publicly available information).

**2. Important DNS Responses to Watch For:**
- When using the dig command, pay attention to the following responses:
 - NXDOMAIN: The domain or subdomain doesn’t exist.
 - SERVFAIL: The server failed to process the request.
 - REFUSED: The request was refused by the server.
 - No servers could be reached: Unable to connect to the server.

**3. Checking for Subdomain Takeover with A and CNAME Records:**
- Step 1: Use dnsrecon to perform DNS enumeration:
  >./dnsrecon.py -d victim.com
-> This will show subdomains and their corresponding IP addresses or CNAME records.
- Step 2: Check CNAME records to see if they point to an inactive domain:
  >dig CNAME fictioussubdomain.victim.com
-> If the response is NXDOMAIN, it means the subdomain is inactive and potentially vulnerable to takeover.
- Step 3: Check the A record (IP address) using `whois` to identify the service provider:
  > whois 192.30.252.153 | grep "OrgName"
->For example, if it shows GitHub and visiting the subdomain returns a `404 - File not found` error, this indicates a potential vulnerability, as you could claim the subdomain through GitHub Pages.

**  4. Checking Nameserver (NS Record) Takeover:**
- Step 1: Identify all nameservers for the domain:
  >dig ns victim.com +short
- Step 2: If a nameserver points to an expired or inactive domain that can be purchased, the subdomain could be taken over.

$${\color{green}-Box \space Testing}$$
In Gray-Box Testing, the tester already has access to the DNS zone file, so initial enumeration isn’t needed, but the testing steps are the same as above.
