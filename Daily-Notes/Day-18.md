# Day 18 - Endpoint Investigation & Advanced Threat Hunting 

## Objective 
- Learn how to navigate the Microsoft Defender for Endpoint (MDE) device dashboard
- Investigate Endpoint Activity  using device timeline


## Platform / Tools 
- Microsoft Defender for Endpoint
- Microsoft Defender XDR Portal
- Advanced Threat Hunting 
- Device Timeline


## Actions Performed 
- Navigated to Assets > Devices within Defender XDR Portal and selected an Onboarded endpoint to review its details (*Figure 1*)
- Reviewed Incidents and Alerts associated with the onboarded device (*Figure 2*)
  - Investigated the incident and found it to be Benign, as this PowerShell usage was for the onboarding script to MDE (*Figure 3*)
- Analysed Device Timeline to Observe endpoint activity (*Figure 4*)
- Reviewed the process tree to understand parent-child process relationships (*Figure 5*)
- Examined file prevalence data to assess file rarity and potential threat scope of the incident that was reported (*Figure 6*)
- Reviewed the different tables available in Defender XDR for Endpoint Threat hunting (*Figure 7*)

## SOC Relevance

- MDE enables real-time detection and investigation of endpoint threats
- Automatic alerting reduces reliance on custom detection rules
- Device timelines support rapid root cause analysis during incidents
- Advanced Threat Hunting complements Sentinel by enabling deep endpoint-focused investigations

## Screenshot 

<p align="center">
  <img width="1625" height="476" alt="image" src="https://github.com/user-attachments/assets/01ff379b-29ff-4020-b4f6-948628961b5d" />
</p>
<p align="center"><b>Figure 1: Defender for Endpoint - Device Overview and Risk Assessment</b></p>



<p align="center">
  <img width="1299" height="304" alt="image" src="https://github.com/user-attachments/assets/2ec9e47b-6d7c-4725-b38d-ae6ebf324b07" />
</p>
<p align="center"><b>Figure 2: Endpoint Execution Incident in Microsoft Defender for Endpoint <b></p>



<p align="center">
  <img width="657" height="658" alt="image" src="https://github.com/user-attachments/assets/d323f34a-bbe1-49df-b0c7-1ba3189aeab7" />
</p>
<p align="center"><b>Figure 3: Endpoint Execution Incident for suspicious PowerShell usage, which was found to be benign<b></p>


<p align="center">
  <img width="1360" height="525" alt="image" src="https://github.com/user-attachments/assets/64ccc16f-7681-4186-a508-92bb95745c3a" />
</p>
<p align="center"><b>Figure 4: Endpoint Timeline View in Microsoft Defender for Endpoint<b></p>


<p align="center">
  <img width="433" height="400" alt="image" src="https://github.com/user-attachments/assets/5359a1af-4f0f-430c-9e9f-6ba839988889" />
</p>
<p align="center"><b>Figure 5: Parent-Child Process relationships via Entities <b></p>

<p align="center">
  <img width="377" height="415" alt="image" src="https://github.com/user-attachments/assets/a3d04d17-806a-49fc-a1bf-286f45675462" />
</p>
<p align="center"><b>Figure 6: File Prevalence Analysis in Microsoft Defender for Endpoint <b></p>


<p align="center">
  <img width="971" height="407" alt="image" src="https://github.com/user-attachments/assets/5ddd4f17-d900-4679-9cbe-4af00d008574" />
</p>
<p align="center"><b>Figure 7: Overview of different tables available for endpoint threat hunting<b></p>
