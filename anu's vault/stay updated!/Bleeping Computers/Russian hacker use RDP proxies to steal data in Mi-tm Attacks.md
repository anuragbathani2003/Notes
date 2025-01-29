
### Summary of APT29 Campaign:

1. **Hacking Group**:
    
    - APT29, also known as "Midnight Blizzard," is conducting attacks.
2. **Attack Strategy**:
    
    - Using a network of **193 remote desktop protocol (RDP) proxy servers** for man-in-the-middle (MiTM) attacks.
3. **Tools Used**:
    
    - The group employs **PyRDP** (a red team proxy tool) to:
        - Scan victims' filesystems.
        - Steal data in the background.
        - Remotely execute malicious applications.
4. **Targets**:
    
    - **Sectors**: Government, military, diplomatic entities, IT and cloud services, telecommunications, and cybersecurity.
    - **Geographic Focus**: U.S., France, Australia, Ukraine, Portugal, Germany, Israel, Greece, Turkey, and the Netherlands.
5. **Key Findings**:
    
    - Trend Micro identifies the group as 'Earth Koshchei.'
    - Malicious campaigns include data theft, credential compromise, and payload deployment.

![[intercept.webp]]
**RDP session interception**

![[aws.webp]]
**Deceptive connection request**

![[infrastructure.webp]]
**Overview of infrastructure obfuscation**

## Working of the Attack(Attack chain)

### Summary of APT29's Use of PyRDP for MitM Attacks

1. **Overview of RDP**:
    
    - Remote Desktop Protocol (RDP) is a Microsoft protocol enabling remote access to another computer, commonly used for administration and technical support.
2. **Attack Initiation**:
    
    - Victims are tricked into connecting to **rogue RDP servers** by running files attached to **phishing emails**.
3. **Shared Resources**:
    
    - Once connected, local resources like disks, networks, printers, clipboard, audio devices, and COM ports are shared with the attacker’s RDP server, providing full access to sensitive information.
4. **Infrastructure**:
    
    - **193 RDP proxy servers** redirect connections to **34 attacker-controlled backend servers**, allowing attackers to intercept and monitor sessions.
5. **MitM Tool**:
    
    - Attackers use **PyRDP**, a Python-based tool for man-in-the-middle (MitM) attacks.
    - The tool enables:
        - Logging of plaintext credentials or **NTLM hashes**.
        - Stealing clipboard data and transferred files.
        - Accessing shared drives to steal or modify files.
        - Running **console** or **PowerShell commands**.
6. **Malicious Activities**:
    
    - The rogue server mimics legitimate RDP behavior and executes malicious actions such as:
        - Deploying scripts or modifying system settings.
        - Browsing and altering the victim’s file system.
        - Injecting malicious payloads.
    - A specific example includes a misleading **AWS Secure Storage Connection Stability Test** request.
7. **Evasion Techniques**:
    
    - APT29 obscures IP addresses of rogue servers using:
        - **Commercial VPNs** accepting cryptocurrency payments.
        - **TOR exit nodes**.
        - **Residential proxy services**.
8. **Defense Measures**:
    
    - Avoid connecting to RDP servers linked in email attachments.
    - Use RDP connections only with known and trusted servers.
    - Be cautious with emails, even if sent from legitimate but **compromised addresses**.
9. **Historical Context**:
    
    - The technique was inspired by **Mike Felch’s 2022 research** on PyRDP.


## read more

https://www.bleepingcomputer.com/news/security/russian-hackers-use-rdp-proxies-to-steal-data-in-mitm-attacks/