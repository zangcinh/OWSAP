# OVERVIEW #

$${\color{green}Summary}$$

- Even if primary authentication mechanisms are secure, vulnerabilities might exist in alternative channels for the same user accounts. These channels can be exploited to bypass the main authentication or expose information that aids attacks on the primary channel. Examples include:
  - Standard, mobile-optimized, or accessibility-optimized websites.
  - Alternative country or language versions.
  - Partner or parallel websites sharing user accounts.
  - Development, test, UAT, and staging versions of the main website.
  - Mobile apps, desktop applications, call centers, and IVR systems.
 
$${\color{green}Test \space Objectives}$$

- Identify alternative authentication channels.
- Assess the security measures used in these channels and check for any bypasses.

**Example:** The primary website uses HTTPS for authentication, but a separate mobile-optimized version uses HTTP and has a weaker password recovery mechanism.

# HOW TO TEST #

**1.Understand the Primary Mechanism:** Fully test the main website's authentication, including account creation, password recovery, and elevated privilege authentication measures.

**2.Identify Other Channels:** Find alternative channels using:
- Website content (home page, help pages, FAQs).
- HTTP proxy logs for keywords like “mobile,” “auth,” “SSO.”
- Search engines for similar sites or shared authentication mechanisms.

**3.Enumerate Authentication Functionality:** Identify authentication functions in each channel and compare with the primary channel. Check for extra or missing functions (e.g., mobile has "change password," but no "log out").

**4.Review and Test:** Note alternative channels in the report, even if out of scope. If permitted, perform authentication tests on alternative channels and compare results with the primary channel.
