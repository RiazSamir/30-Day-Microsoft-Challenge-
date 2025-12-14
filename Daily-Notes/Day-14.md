# Day 14 - Threat Explorer & Quarantined Messages (Defender XDR) 

## Objectives
- Understand how Threat Explorer is used to investigate email-based threats
- Review how quarantined messages are handled and analysed
- Validate email security detection and user-reported phishing

## Platforms / Tools
- Microsoft Defender XDR
- Threat Explorer
- Quarantine (Review)
- Submissions

## Actions Performed
- Navigated to Threat Explorer within Defender XDR portal (*Figure 1*)
- Viewed the Dashboard within Threat Explorer (*Figure 2*)
  - Here we have a view of emails being sent and received
  - We can also filter by sender address and much more, which essentially allows us to narrow down results and supports email threat hunting
  - Clicking on an Email allows us to analyse the email header, where we can find artefacts such as authentication results and sender server IP addresses.
  - We can also use Email Entity to analyse the timeline of a particular email. Here we found when the email was delivered and when the user clicked on the email, and how many times they may have done this (*Figure 3 - 4*)
- Reviewed the Quarantined Section (called Review in Defender XDR); however, as expected, we won't have anything here (*Figure 5*)
- Accessed Outlook as the test user and reported a test email as Phishing (*Figure 6*)
  - This will then be sent for further investigation and can be found under Investigation & Response > Actions & Submissions > Submissions in Defender XDR (*Figure 7*)
 
## SOC Relevance
- Threat Explorer is the primary investigation tool for phishing and malicious emails
- Enables analysts to determine whether emails were delivered, blocked, or clicked
- Quarantine allows analysts to review and manage emails removed from user inboxes







## Screenshots 


<p align="center">
  <img width="1500" height="700" alt="image" src="https://github.com/user-attachments/assets/e91c3ec4-51ef-4093-918d-32c4ae19ad0d" />
</p>
<p align="center"><b>Figure 1: Navigation to Threat Explorer within Defender XDR </b></p>

<p align="center">
  <img width="1371" height="421" alt="image" src="https://github.com/user-attachments/assets/e03af803-4475-4c50-836d-20aa5df0ba57" />
</p>
<p align="center"><b>Figure 2: Threat Explorer Dashboard </b></p>

<p align="center">
  <img width="382" height="359" alt="image" src="https://github.com/user-attachments/assets/3286c65b-d972-42f9-a95a-00e10be2a255" />
</p>
<p align="center"><b>Figure 3: Navigation to Email Entity </b></p>


<p align="center">
  <img width="1403" height="454" alt="image" src="https://github.com/user-attachments/assets/4278876e-43aa-49fa-b957-274ecf0d1d9f" />
</p>
<p align="center"><b>Figure 4: Defender XDR Email Entity Timeline (Delivery and URL Click)</b></p>


<p align="center">
  <img width="1649" height="200" alt="image" src="https://github.com/user-attachments/assets/199ea5a3-35eb-4827-b12d-9cf2f1e5fc7e" />
</p>
<p align="center"><b>Figure 5: Defender XDR Quarantine Queue for Email Messages</b></p>


<p align="center">
  <img width="1233" height="223" alt="image" src="https://github.com/user-attachments/assets/c314e50c-ce26-4d63-83b3-42d590fcf5ea" />
</p>
<p align="center"><b>Figure 7: User-Reported Phishing Submission in Microsoft Defender XDR </b></p>

