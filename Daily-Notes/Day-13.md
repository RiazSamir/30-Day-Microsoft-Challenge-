# Day 13 - Anti-Phishing Policies in Microsoft Defender XDR

## Objective:
- Understand how Defender XDR detects phishing and impersonation attacks
- Configure a custom Anti-Phishing policy to protect users and domains

## Platform / Tools:
- Microsoft Defender XDR
- Email & Collaboration Security 
- Threat Policies

## Actions Performed: 
- Navigated to Email & Collaboration > Policies & Rules > Anti-Phishing
- Began creating an Anti-Phishing Rule (*Figure 1*)
- Configuring the Policy of our Anti-Phishing rule (*Figure 2*)
  - This includes:
    - Defining Users to protect from impersonation, which is especially important for individuals in financial roles or C-Suite executives.
    - Defining the Domains we want to protect, which is important when preventing attacks such as typosquatting (look-alike domains)
    - Enabling Mailbox Intelligence AI/ML feature in Microsoft Defender for Office 365 that learns how each user normally communicates. For example who emails you? Who do you usually Email? How Often?
- Configured the policy logic of when things like SPF and DMARC fail (*Figure 3*)
  - configured anti-phishing actions to quarantine impersonation attempts, enforce DMARC policies, and apply spoof intelligence while adding user-facing safety indicators for awareness.


## SOC Relevance

- Anti-Phishing Policies reduce the risk of credential theft and fraud
- Protecting VIP and finance users mitigates business email compromise (BEC)
- Domain and User Impersonation detection prevents spoofing attacks
- Mailbox Intelligence improves detection accuracy using behavioural baselines
- Safety tips increase user awareness and reduce successful phishing attempts



## Screenshots

<p align="center">
  <img width="1192" height="288" alt="image" src="https://github.com/user-attachments/assets/aaff7c09-35e5-4af3-8390-60103f60ec3a" />
</p>
<p align="center"><b>Figure 1: Anti-Phishing Policy Creation</b></p>

<p align="center">
  <img width="766" height="461" alt="image" src="https://github.com/user-attachments/assets/9ace11e4-0e5a-477e-a40a-f12815e58830" />
</p>
<p align="center"><b>Figure 2: Configruation of custom Anti-Phishing policy</b></p>

<p align="center">
  <img width="900" height="700" alt="image" src="https://github.com/user-attachments/assets/db8513a8-2bd9-4668-9176-a86915da8f4c" />
</p>
<p align="center"><b>Figure 2: Anti-Phishing Policy Response actions including DMARC Enforcement & Safety Tips and Indicators.</b></p>
