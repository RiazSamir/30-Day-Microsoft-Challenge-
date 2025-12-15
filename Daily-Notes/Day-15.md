# Day 15 - Phishing Simulation & Email Security Validation 

## Objective
- Simulate a Phishing attack to test configured email security controls
- Observe how Microsoft Defender for Office 365 responds to Phishing activity

Platform / Tools 
- Microsoft Defender XDR
- Attack Simulation Training
- Threat Explorer
- KQL

## Actions Performed
- Crafted a basic phishing email targeting a test user (John Doe) (*Figure 1*)
  - Reviewed the Email within the test user's inbox to see how our security policy works (*Figure 2*).
    - We observed Safe Links and Safety Tips working.
- Another Phishing Attack was conducted, but this time, the Attack Simulation & Training in Defender XDR was utilised (*Figure 3*)
  - A credential Harvesting Attack was conducted (*Figure 4*), which will have the user log in to a fake portal.
    - The Email created is to scare the user into thinking they will lose access to their Tesco Account unless immediate action is taken (*Figure 5*)
      - Once the user clicks on the link, they are presented with the credential Harvester (*Figure 6*)
        - If the User provides their details, they are then forced to undergo security awareness Training (*Figure 7*)
- Reviewed a summary of the users who had fallen for the Simulated Phishing Attack or had Reported it (*Figure 8*)


## SOC Relevance 
- Phishing simulations safely validate safe links and Anti-Phishing policies
- URL rewriting and click tracking confirm Safe Links Effectiveness
- Training Assignment demonstrates user awareness training

## Screenshots

<p align="center">
  <img width="545" height="278" alt="image" src="https://github.com/user-attachments/assets/11ac6c5c-ec6f-4a35-b8cd-7b478b00a5d5" />
</p>
<p align="center"><b>Figure 1: Crafted Phishing Email sent to Joh Doe</b></p>


<p align="center">
  <img width="1373" height="396" alt="image" src="https://github.com/user-attachments/assets/3545cad0-58d9-4a79-bf69-19365cdda9a3" />
</p>
<p align="center"><b>Figure 2: Phishing Email from the User's perspective. </b></p>


<p align="center">
  <img width="1683" height="372" alt="image" src="https://github.com/user-attachments/assets/e6603dee-20c6-421d-9be4-51577c759a05" />
</p>
<p align="center"><b>Figure 3: Overview of Attack Simulation Training </b></p>


<p align="center">
  <img width="784" height="679" alt="image" src="https://github.com/user-attachments/assets/c622bb54-071d-4966-89ad-3f05592aaf8b" />
</p>
<p align="center"><b>Figure 4: Overview of the different types of Email Techniques associated with Phishing Attacks</b></p>


<p align="center">
  <img width="1247" height="567" alt="image" src="https://github.com/user-attachments/assets/9d876e14-4654-4f0f-9fb4-fe061e783de0" />
</p>
<p align="center"><b>Figure 5: Simulated Phishing Email to log into their account or they will lose access</b></p>


<p align="center">
  <img width="432" height="418" alt="image" src="https://github.com/user-attachments/assets/73457814-3ad4-4321-8b31-2d3e256852f8" />
</p>
<p align="center"><b>Figure 6: Simulated Credential Harvester</b></p>


<p align="center">
  <img width="1650" height="514" alt="image" src="https://github.com/user-attachments/assets/2afb5574-2640-4e17-a6b4-f12f642d3b67" />
</p>
<p align="center"><b>Figure 7: Security Awareness Training Page upon supplying Credential at the Credential Harvester Page</b></p>


<p align="center">
  <img width="1728" height="658" alt="image" src="https://github.com/user-attachments/assets/3faa3e70-07da-4f56-bbbf-b59d5335da4f" />
</p>
<p align="center"><b>Figure 8: Defender XDR Phishing Simulation Impact and User Interaction Summary</b></p>
