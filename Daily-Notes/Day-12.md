# Day 12 - Safe Links Protection with Microsoft Defender for Office 365

## Objective:
- Understand how Safe Links protect users from malicious URLS
- Create and Configure a Safe Links Policy
- Observe Safe Links behaviour through a practical proof of Concept.


## Platform / Tools
- Microsoft Defender for Office 365
- Microsoft Defender XDR Portal
- Email & Collaboration

## Actions Performed 
- Navigated to Email & Collaboration > Policies and Rules > Threat Policies > Safe Links
- Reviewed how Safe Links scans and rewrites URLs at the time of Click
- Began creating our own Safe Links Rule (*Figure 1*)
- Configured the Safe Links Settings (*Figure 2*)
- Before enabling our SafeLinks Rule, I had sent an email to a test user, which shows that the URLs aren't being rewritten (*Figure 3*)
- I had then enabled our Custom Safe Links Rule and sent another test email (*Figure 4*)
  - This is powerful, as now when the user clicks on the link, it goes through Defender's Safe Links Service. Which Defender will then perform:
    - URL Reputation
    - Known Phishing/malware indicators
    - Time of Click, which is useful for investigation.
   
## SOC Relevance

- Safe Links mitigates Phishing by inspecting URLs at click time rather than delivery time.
- URL rewriting allows Defender to block malicious links even after emails are delivered.
- Click Tracking provides visibility into user interaction with potentially malicious links
- This control directly reduces initial access via phishing, the most common attack vector. 



## Screenshots


<p align="center">
  <img width="1193" height="262" alt="image" src="https://github.com/user-attachments/assets/46fe4cdb-9346-4132-bf35-353f6dd7c2ea" />
</p>
<p align="center"><b>Figure 1: Safe Links Rule Creation </b></p>

<p align="center">
  <img width="423" height="681" alt="image" src="https://github.com/user-attachments/assets/3ee50017-8778-4a74-a6bc-656c036dcc06" />
</p>
<p align="center"><b>Figure 2: Configured our Safe Links setting on how it should work</b></p>



<p align="center">
  <img width="607" height="195" alt="image" src="https://github.com/user-attachments/assets/29234a85-4345-4b9d-a917-443404fbd942" />
</p>
<p align="center"><b>Figure 3: Email delivered before Safe Links policy enforcement, showing URL not rewritten</b></p>



<p align="center">
  <img width="877" height="189" alt="image" src="https://github.com/user-attachments/assets/cd9272a3-faab-4bcb-b32d-d404335044eb" />
</p>
<p align="center"><b>Figure 4: Email delivered after Custom Safe Links policy has been enabled, showing URL being rewritten.</b></p
