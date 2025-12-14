# Day 06 – Defender XDR intergration & First Detection Rule  

## Objective:
- Intergrate Microsoft Defener XDR with Microsoft Sentinel
- Create an initial detection rule for Brute Force Activity

## Platform / Tools 
- Microsoft Defender XDR
- Microsoft Sentinel
- Sentinel Content Hub
- Sentinel Analytics

## Actions Performed 
- Installed Defender XDR via Content Hub (*Figure 1*)
- Once installed, Data connectors for Defender XDR had to be configured. Essentially we had configured it So that Sentinel will begin ingesting alerts from Defender XDR which we can then view (*Figure 2*)
- Created our first detection rule via Analytic for Brute Force Attacks (*Figure 3*)
- Created the Logic of our rule using KQL (*Figure 4*)
- Automatic Incident Creation if our rule was triggered (*Figure 5*)
- Verified our Rule works by going to the incident Section of Sentinel (*Figure 6*)




## Screenshots

<p align="center">
  <img width="300" height="600" alt="image" src="https://github.com/user-attachments/assets/afb9f452-0133-41f9-a247-c0271ba1cdf1" />
</p>
<p align="center"><b>Figure 1: Installation of Defender XDR via Sentinel Content Hub</b></p>

<p align="center">
  <img width="1282" height="244" alt="image" src="https://github.com/user-attachments/assets/669765f4-b8b6-43be-925c-91e0ac9c01f3" />
</p>
<p align="center"><b>Figure 2: Configuring the Data Connector for Defender XDR so that Alerts would be ingested by Sentinel. This includes Endpoints, Email, and Identity</b></p>


<p align="center">
  <img width="1161" height="602" alt="image" src="https://github.com/user-attachments/assets/39ecdacd-7660-41a2-a512-9a09ecda9b9d" />
</p>
<p align="center"><b>Figure 3: Rule creation via Analytics to detect brute Force attakcs.</b></p>


<p align="center">
  <img width="990" height="251" alt="image" src="https://github.com/user-attachments/assets/f759e8b5-dc9b-4112-959b-5f1216e7f503" />
</p>
<p align="center"><b>Figure 4: Detection Logic for excessive failed logon Events (Event ID 4625).</b></p>


<p align="center">
  <img width="1479" height="679" alt="image" src="https://github.com/user-attachments/assets/1e2da3aa-1279-4fd4-b391-76802f87aaae" />
</p>
<p align="center"><b>Figure 5: Enabling Incident Creation for when our Brute Force Rule was triggered.</b></p>


<p align="center">
  <img width="1612" height="615" alt="image" src="https://github.com/user-attachments/assets/496d11a9-bed3-4b5c-8840-e862467c2daf" />
</p>
<p align="center"><b>Figure 6: Sentinel Incidents page presenting our rule in action.</b></p>
