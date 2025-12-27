# Day 27 – Full Attack Simulation Report 

## Overview

This investigation simulated a realistic attack chain commonly seen in enterprise environments.
A user received a phishing email containing a typosquatted DocuSign link, entered credentials, and the attacker used those stolen credentials to access Outlook Web Access and later an endpoint. On the endpoint, credential dumping activity was observed using Mimikatz, including the theft of Kerberos tickets. The goal of this exercise was to track end-to-end attacker behaviour, correlate identity and endpoint telemetry, and practice incident reporting and response recommendations.


---

# Report

## Findings

### Emails
- **2025-12-25 17:20 (UTC)** — Suspicious invoice email sent to John Doe from Gmail address: **abc@gmail.com**

### Files
- **2025-12-25 18:56 (UTC)** — `mimikatz.exe` executed  
  - **Location:** `C:\Users\JohnDoe\AppData\Local\Temp\mimikatz_extracted\x64\mimikatz.exe`

### IP Addresses
- **x[.]x[.]x[.]x** — Canada, Montreal Office Network, ASN: **AS212238**

### URL
- **D0cusign[.]com** (typosquatted DocuSign domain)

## Investigation Summary 

On 2025-12-25 17:30 PM (UTC), an Incident was created for an Anonymous IP involving one user. A successful sign-in had been made from the IP address x[.]x[.]x[.]x on 2025-12-25 17:33 PM (UTC), into the user's (John Doe) Outlook Web (Figure 1). On 2025-12-25 17:20 PM (UTC), a Suspicious Invoice Email was sent to John Doe from the Gmail Address **abc@gmail.com** claiming that their "invoice is ready for viewing". This Email did have a URL attached (D0cusign[.]com) which the user had clicked on 2025-12-25 17:23 PM (UTC). Using URL2PNG for this link showed a login page, which is likely a credential harvester (Figure 2). Due to the structure of the URL in the email, typosquatting is occurring, meaning this Gmail address is imitating the legit site docusign.com and getting people to click on the link to log in and possibly steal credentials. Based on the available evidence, a **30-day advanced hunting email search** showed that only John Doe received this email. (Figure 3). Furthermore, looking up this IP address on Abuse IPDB, this IP address was reported 12 times with an abuse confidence of 0%. This IP Address was last reported 2 months ago for port scanning as well as brute forcing (Figure 6)

On 2025-12-25 18:57 PM (UTC), an incident was generated on Defender XDR for Credential Access on one Endpoint. The affected asset (soc-project-samir-vm-01) had executed Mimikatz.exe via PowerShell. This was done by the user John Doe. Mimikatz is a malicious program which is known for credential dumping. On 2025-12-25 18:56 PM - 2025-12-25 19:00 PM (UTC), the following commands were executed: 

`sekurlsa::tickets`

`sekurlsa::minidump` 

which are both used to steal credentials as well as Kerberos tickets using mimikatz.exe. On  2025-12-25 18:43 PM (UTC), a successful login was made onto the endpoint soc-project-samir-vm-01 sourcing from the same IP x[.]x[.]x[.]x however, the logon type was either unknown or unlock. It is possible that this was done through RDP however further investigation is required. What is certain that the logon was made by the same IP Address associated with the OWA sign-in. (Figure 4). Based on the available evidence, no further sign-in activities or lateral movement activities have been observed (Figure 5). However, this is subject to change due to how recent this is. In this case, immediate action needs to be taken. 

## Who, What, When, Where, Why 

### Who 
- **Primary user:** John Doe  
- **External IP:** x[.]x[.]x[.]x  
- **Affected endpoint:** `soc-project-samir-vm-01`  
- **Phishing email sender:** `abc@gmail.com` (typosquatted DocuSign lure)



### What 
- John Doe received a phishing email
- The email contained a malicious DocuSign-lookalike link
- John Doe clicked the link and likely entered credentials
- The suspicious IP successfully logged into OWA
- The same IP later logged into the endpoint
- On the endpoint, **Mimikatz** was executed
- The following commands were run:
  - `sekurlsa::tickets`
  - `sekurlsa::minidump`
- These commands indicate:
  - credential dumping  
  - Kerberos ticket theft  
  - possible lateral movement attempt  



### When – Timeline (UTC)

| Event | Timestamp |
|------|-----------|
| Phishing email received | 2025-12-25 17:20 |
| User clicked phishing link | 2025-12-25 17:23 |
| Suspicious OWA login | 2025-12-25 17:33 |
| Endpoint login from same IP | 2025-12-25 18:43 |
| Mimikatz execution window | 2025-12-25 18:56 - 19:00 |



### Where 
- **Email platform:** Outlook Web Access (OWA)
- **Endpoint:** soc-project-samir-vm-01



### Why 
- User fell for phishing lure
- Credentials were harvested
- Attacker used stolen credentials
- Attacker executed credential-dumping tools
- Likely objectives:
  - privilege escalation
  - lateral movement
  - Kerberos ticket theft

## Recommendations

- Immediately **reset credentials** for John Doe
- Reset any accounts sharing the same password
- **Revoke all active sessions** associated with compromised accounts
- The IP Address (x[.]x[.]x[.]x) associated should also be blocked, given that we have no business occurring in Canada.
- Require re-authentication with **new credentials**
- **Enforce MFA** on affected accounts if not already enabled
- **Isolate endpoint `soc-project-samir-vm-01`** from the network
- Perform full malware containment via **Microsoft Defender for Endpoint**
- Review additional lateral movement indicators. This can be done by viewing Windows event logs 4624/4625 with the Logon type being 3 or 10.


## Screenshots

<p align="center">
  <img width="825" height="435" alt="image" src="https://github.com/user-attachments/assets/d69f40f4-767e-4e07-8517-f8d4df4a17eb" />
</p>
<p align="center"><b>Figure 1: Multiple failed OWA sign-in attempts followed by a successful login from the same external IP address</b></p>


<p align="center">
  <img width="520" height="597" alt="image" src="https://github.com/user-attachments/assets/f92b3965-4c8b-4341-9299-731c6c268362" />
</p>
<p align="center"><b>Figure 2: Typosquatted DocuSign-lookalike phishing webpage used to harvest user credentials </b></p>


<p align="center">
  <img width="673" height="434" alt="image" src="https://github.com/user-attachments/assets/97b59a5e-91cb-4d72-a04b-1f71b1931d1d" />
</p>
<p align="center"><b>Figure 3: Advanced Hunting query confirming only John Doe received the phishing email with the subject “Invoice is ready for viewing”</b></p>


<p align="center">
  <img width="1218" height="175" alt="image" src="https://github.com/user-attachments/assets/57043af9-c063-4fd9-afbd-9aed3c20e0e8" />
</p>
<p align="center"><b>Figure 4: Successful endpoint login to soc-project-samir-vm-01 from the same suspicious external IP address used in the earlier OWA compromise</b></p>


<p align="center">
  <img width="1158" height="321" alt="image" src="https://github.com/user-attachments/assets/46fc700e-d411-42cc-9dbc-232262980ef9" />
</p>
<p align="center"><b>Figure 5: No evidence of lateral movement detected — no RemoteInteractive or Network logon types observed on other devices during the investigation timeframe</b></p>


<p align="center">
  <img width="628" height="475" alt="image" src="https://github.com/user-attachments/assets/9ae007a6-8f0f-4e0b-8a34-c659dda808b1" />
</p>
<p align="center"><b>Figure 6: AbuseIPDB lookup showing IP reputation, ASN (AS212238), and geolocation (Montreal, Canada)</b></p>
