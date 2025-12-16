# Day 17 - Endpoint Security with Microsoft Defender for Endpoint (MDE) 

## Objective
- Onboard a Windows 11 Virtual Machine into Microsoft Defender for Endpoint
- Validate Endpoint Telemetry Visibility within Defender XDR portal

## Platform / Tools
- Microsoft Defender for Endpoint
- Defender XDR Portal
- Windows 11 Virtual Machine
- KQL


## Actions Performed 
- Reviewed Endpoint settings via Defender XDR (*Figure 1*) and enabled the following settings:
  -  Enable EDR in Block Mode
  -  Custom Network Indicators
  -  Web Content Filtering
  -  Live Response
  -  Microsoft Intune Connections
 - Navigated to device onboarding on Defender XDR Settings to set up the onboarding of the Virtual Machine (*Figure 2*)
 - Downloaded the Onboarding package and transferred it to the Virtual Machine via a shared folder (*Figure 3 - 4*)
 - Once installed, "Run Detection Test" confirmed that the device was successfully onboarded onto MDE (*Figure 5*)
 - Reviewed the device under Asset > Device to  further confirm onboarding onto MDE (*Figure 6*)

## SOC Relevance
- Defender for Endpoint provides continuous endpoint telemetry, including:
  - Process Execution
  - File creation & Modification
  - Registry Changes for persistence detection
  - Network connections and potential C2 activity
-  Onboarding endpoints is critical for enabling endpoint-based threat detection and investigation
-  Establishes the foundation for future endpoint attack simulations and detections

## Screenshots

<p align="center">
  <img width="794" height="476" alt="image" src="https://github.com/user-attachments/assets/82fe4254-74bd-49b8-8152-87a153298fd2" />
</p>
<p align="center"><b>Figure 1: Endpoint Settings on Defender XDR</b></p>


<p align="center">
  <img width="1374" height="795" alt="image" src="https://github.com/user-attachments/assets/d40ada64-ea12-4da6-9d52-9e588efa1c09" />
</p>
<p align="center"><b>Figure 2: Device onaboarding configurations</b></p>


<p align="center">
  <img width="838" height="513" alt="image" src="https://github.com/user-attachments/assets/11f3f663-cffe-4b26-ac0d-b489aadbfacd" />
</p>
<p align="center"><b>Figure 3: Downloaded Microsoft Defender for Endpoint local onboarding package on the virtual machine</b></p


<p align="center">
  <img width="983" height="330" alt="image" src="https://github.com/user-attachments/assets/60148b0e-05d5-4dba-b483-46b4822ec095" />
</p>
<p align="center"><b>Figure 4: Microsoft Defender for Endpoint local onboarding script execution</b></p


<p align="center">
  <img width="1613" height="872" alt="image" src="https://github.com/user-attachments/assets/0a687748-5b10-4fa4-ba72-1bfc76606870" />
</p>
<p align="center"><b>Figure 5: Successful onboarding of the first device</b></p


<p align="center">
  <img width="1337" height="109" alt="image" src="https://github.com/user-attachments/assets/130caba8-26e7-47e3-8c02-723b3801bd19" />
</p>
<p align="center"><b>Figure 6: Defender for Endpoint Device Inventory Showing Successful Onboarding and Active Sensor </b></p
