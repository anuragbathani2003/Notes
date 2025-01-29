
- **Vulnerability Overview**:
    
    - A critical security flaw, CVE-2024-52875, impacts GFI KerioControl firewalls (versions 9.2.5 to 9.4.5).
    - It allows for remote code execution (RCE) via a carriage return line feed (CRLF) injection, leading to HTTP response splitting and potential cross-site scripting (XSS) attacks.
    
- **Technical Details**:
    
    - Exploitation involves injecting malicious inputs using carriage return (\r) and line feed (\n) characters into HTTP response headers.
    
    - Affected URI paths include:
        - `/nonauth/addCertException.cs`
        - `/nonauth/guestConfirm.cs`
        - `/nonauth/expiration.cs`
    - The flaw arises due to improper sanitization of user input passed via the "dest" GET parameter.
    
- **Patch Availability**:
    
    - GFI released a fix (version 9.4.5 Patch 1) on December 19, 2024.
- **Exploitation**:
    
    - Threat actors use malicious URLs to upload .img files, granting root access to firewalls.
    - Exploitation attempts started on December 28, 2024, from seven unique IPs in Singapore and Hong Kong.
- **Exposure**:
    
    - Over 23,800 internet-exposed KerioControl instances exist, with most located in Iran, Uzbekistan, and Italy.
- **Advisory**:
    
    - Users are urged to update KerioControl to secure their systems and prevent exploitation.


## Read More

Link:- https://thehackernews.com/2025/01/critical-rce-flaw-in-gfi-keriocontrol.html