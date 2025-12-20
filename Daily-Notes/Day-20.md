# Day 20 - Simulating Adversary Behaviour Using Atomic Red Team 



## Objective
- Simulate suspicious adversary activity on a Windows virtual machine
- Trigger alerts and telemetry in Microsoft Defender for Endpoint
- Observe how Defender detects, correlates, and surfaces attacker behaviour


## Platform / Tools
- Windows 11 Virtual Machine
- Atomic Red Team
- Invoke-AtomicRedTeam PowerShell module
- Microsoft Defender for Endpoint
- Microsoft Defender XDR Portal

## Actions performed

- Installed Atomic Red Team and required PowerShell modules (*Figure 1*)
- Created a Defender exclusion for the **entire C:\ drive** to prevent Atomic Red Team activity from being blocked during testing
- Executed the following Atomic test:
  - `Invoke-AtomicTest T1547.001` (*Figure 3*)
    - This Simulated persistence behaviour is associated with Registry Run Keys and Startup Folder execution
      - Generated realistic endpoint telemetry without deploying real malware
- Reviewed the Incidents created in Defender XDR Portal, one of which was automatically created (*Figure 4*)
- Analysed the alerts for the registry run keys being created with the set value data being calc.exe (*Figure 5*)
- AS a way to pivot from this alert, navigated to `See in device timeline` to see the event that had occurred prior to the alert generating (*Figure 6*)

## SOC Relevance
- Atomic Red Team allows SOC analysts to safely test detection coverage using real MITRE ATT&CK techniques
- Helps validate whether Defender for Endpoint is correctly detecting persistence, execution, and post-compromise behaviour
- Understanding Device Timeline is critical for reconstructing attack chains during investigations
- Practising alert analysis improves triage skills and prioritisation decisions


## Screenshots

<p align="center">
  <img width="508" height="216" alt="image" src="https://github.com/user-attachments/assets/65b7146e-ae0a-4c63-a57d-05d4b42e9c8a" />
</p>
<p align="center"><b>Figure 1: Installed Atomic Red Team components on the C:\ drive</b></p>

<p align="center">
  <img width="348" height="313" alt="image" src="https://github.com/user-attachments/assets/06dedfa4-d275-4e1d-acb0-8146446b0872" />
</p>
<p align="center"><b>Figure 2: Exclusion created in Defender</b></p>

<p align="center">
  <img width="1142" height="851" alt="image" src="https://github.com/user-attachments/assets/beca9984-6611-455d-b097-286151d14e6e" />

</p>
<p align="center"><b>Figure 3: Execution of AtomicTest T1547.001</b></p>


<p align="center">
  <img width="1410" height="215" alt="image" src="https://github.com/user-attachments/assets/2d9aca35-2ca4-48d3-9b31-b251b13b6f04" />

</p>
<p align="center"><b>Figure 4: Incident Creation after Atomic Test had been conducted</b></p>


<p align="center">
  <img width="1275" height="230" alt="image" src="https://github.com/user-attachments/assets/d0d4e4f2-3722-4c59-9c71-28af3ae4f09d" />
</p>
<p align="center"><b>Figure 4: Microsoft Defender for Endpoint alert detecting registry-based persistence activity</b></p>


<p align="center">
  <img width="1275" height="230" alt="image" src="https://github.com/user-attachments/assets/d0d4e4f2-3722-4c59-9c71-28af3ae4f09d" />
</p>
<p align="center"><b>Figure 5: Microsoft Defender for Endpoint alert detecting registry-based persistence activity</b></p>


<p align="center">
  <img width="1623" height="437" alt="image" src="https://github.com/user-attachments/assets/eff5b666-b4de-4855-9078-5f1c60b85737" />
</p>
<p align="center"><b>Figure 5: Microsoft Defender for Endpoint alert detecting registry-based persistence activity</b></p>
