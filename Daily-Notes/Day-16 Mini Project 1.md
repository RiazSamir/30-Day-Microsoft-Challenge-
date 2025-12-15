# Phishing Attack Simulation Report 

## Overview
- This project is a Phishing attack simulation designed to replicate a real-world incident response workflow, including investigation, analysis, and report creation from a SOC analyst's perspective. 


## Context 
- Our test User John Doe had received a Phishing Email Urging them that they required a change in financial information and then supplying a Link to a website (*Figure 1*).

# Report

### Findings

Email Delivered: 2025-12-14 22:04 UTC  
Closest Sending Server IP: x[.]x[.]x[.]x  
Reply-To Address: abc@gmail.com  
Return Address: abc@gmail.com  
Subject: Banking Details URGENT  
Message ID: xxx  

Authentication Results:
- SPF=pass
- DKIM=Pass
- DMARC=pass

URLs:
- hxxps://example.com/
  - IP Address of Website: 104.20.34.220
  - Location: New Jersey - Newark - Cloudflare Inc.
  - Created: 1992-01-01

---

### Investigation Summary

On 2025-12-15 14:36 UTC, the user John Doe had reported an email for Phishing which came from the sender address abc@gmail.com. This was delivered to the user on 2025-12-14 22:04 UTC with the Subject "Banking Details URGENT". The email in question informed the user that they had wanted to change their financial information and that it was a matter of Urgency. The Sender had then provided a link which goes to hxxps://example.com/. On 2025-12-15 04:59 UTC, the user John Doe had clicked on this link twice. Due to limited Telemetry Sign-in telemetry (Microsoft Entra ID SigninLogs table) was not available within the environment at the time of investigation. As a result, confirmation of post-click authentication activity or potential session token misuse could not be performed.

hxxps://example.com is a website reserved by IANA (Internet Assigned Numbers Authority). This is an organisation which oversees global IP Address Allocation, and this domain is usually reserved as a placeholder that doesn't usually host any services on this domain. The sender may have attached the wrong URL by chance; however, if someone wanted to change their financial information, why would they provide a link? The intent behind the inclusion of the placeholder domain could not be determined. A lookup on Virus Total for this domain (hxxps://example.com) presents only one flagged vendor (*Figure 2*) and the community tab confirming that "this is just an example domain" (Figure 3). Based on the available evidence, when performing a 31-day search for who else may have clicked on this link, it shows that only John Doe had clicked on this Email (Figure 4). Furthermore, when assessing who else may have received this email, the available evidence shows that only John Doe had received this Specific Email in the past 31 days (Figure 5).

Performing an IP Address lookup on AbuseIPDB shows that the IP Address x[.]x[.]x[.]x was reported 25 times with an Abuse confidence of 0% and the last time this IP was reported was 4 months ago for Phishing and Spam (Figure 6 - 7). The confidence of 0% means that there has been no confirmed malicious activity at the time of analysis.

---

### Who, What, When, Where, Why, How

#### Who - Who was involved?
- John Doe, who is the Affected User
- abc@gmail.com, who had sent the suspicious email

#### What - What happened?
- On 2025-12-15 14:36 UTC, the user John Doe had reported an email for Phishing which came from the sender abc@gmail.com. This email had landed in John Doe's inbox on 2025-12-14 22:04 UTC. The email in question informed the user that they had wanted to change their financial information and that it was a matter of Urgency and had then supplied a link going to hxxps://example.com.

#### When - When did this occur, and is it still happening? (Include timezone)
- Time of Email Delivery: 2025-12-14 22:04 UTC
- URL Clicked by John Doe: 2025-12-15 04:59 UTC

#### Where - Where in the environment did this happen?
- This had occurred in Outlook Web Access

#### Why - Why did this happen? (If known)
- This is unclear as SPF, DKIM and DMARC had passed, and there were no spoofing or Typosquatting attempts in place, based on the Sender Address, Reply-Address and the URL attached.

#### How - How did this happen?
- An Email was sent to John Doe with a sense of urgency to update their financial information, and then supplied a link.
- John Doe had then clicked on this link twice, taking them to hxxps://example.com, which at the time of investigation didn't exhibit malicious behaviours. Post Click Activity could not be confirmed.

---

### Recommendations

Based on the evidence presented, the email appears to be benign; however, monitoring for the sender address (abc@gmail.com) should be done, and if applicable, block the address (Not the Domain). Furthermore, John Doe's credentials should be reset as a precautionary measure, if cookies were stolen and invalidate active user sessions. Ensure the user John Doe has MFA enabled. Due to limited telemetry SigninLogs table could not be queried. Therefore, it was not possible to validate whether any successful authentication events occurred following the user's interaction with the URL. Again, it is strongly advisable to reset the user's credentials for Entra ID as well as other services the user may use. The Domain hxxps://example.com likely serves no purpose in a production environment, if applicable, please block this domain.


## Screenshots

<p align="center">
  <img width="850" height="420" alt="image" src="https://github.com/user-attachments/assets/a4bb9c33-9c32-46c8-9159-2025ea5935af" />
</p>
<p align="center"><b>Figure 1: Simulated Phishing Email sent to the user John Doe</b></p>



<p align="center">
  <img width="1414" height="577" alt="image" src="https://github.com/user-attachments/assets/55da3a8e-868f-452f-b67b-fb7469b230e5" />
</p>
<p align="center"><b>*Figure 2: VirusTotal results for hxxps://example.com indicating no confirmed malicious activity at the time of analysis.*</b></p>


<p align="center">
  <img width="698" height="287" alt="image" src="https://github.com/user-attachments/assets/fa239de4-2dcf-446a-a514-c669da472f1b" />
</p>
<p align="center"><b>*Figure 3: VirusTotal community feedback describing hxxps://example.com as a benign example domain.*</b></p>

<p align="center">
  <img width="1104" height="359" alt="image" src="https://github.com/user-attachments/assets/2450d8c1-5652-4f7b-a0fc-a9668eded31e" />
</p>
<p align="center"><b>*Figure 4: KQL Query for people who have clicked on the link hxxps://example.com*</b></p>

<p align="center">
  <img width="1515" height="305" alt="image" src="https://github.com/user-attachments/assets/51b76b2e-894c-48e7-b8cd-4f131e5927ed" />
</p>
<p align="center"><b>*Figure 5: KQL Query for people who else may have received the email with the Subject "Banking Details URGENT".*</b></p>


<p align="center">
  <img width="618" height="496" alt="image" src="https://github.com/user-attachments/assets/422c7d07-40e7-40a1-839e-382685377908" />
</p>
<p align="center"><b>*Figure 6: IPDBAbuse for the senders IP Address x[.]x[.]x[.]x*</b></p>


<p align="center">
  <img width="1243" height="124" alt="image" src="https://github.com/user-attachments/assets/3898f176-5b8b-49a0-9582-63995e62ab4b" />
</p>
<p align="center"><b>*Figure 7: Latest report on the Sender IP Address x[.]x[.]x[.]x flagging it for Phishing and Email Spam *</b></p>


