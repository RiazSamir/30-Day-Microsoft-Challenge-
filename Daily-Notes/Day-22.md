# Day 22 – Executing a Threat Hunt Using PowerShell Network Activity

## Objective
- Apply a real-world threat Hunting hypothesis
- Use Advanced Hunting to identify suspicious PowerShell behaviour
- Analyse endpoint and network Telemetry to validate or disprove the hypothesis

## Platform / Tools
- Microsoft Defender for Endpoint
- Microsoft Defender XDR
- Advanced Hunting (KQL)

## Hypothesis

`PowerShell is rarely used by normal users to download files. PowerShell reaching out to external IPs or URLs may indicate malicious download or command-and-control activity`

## Actions Performed 
- Identified relevant data sources for the hypothesis:
  - `DeviceNetworkEvents` 
  - `DeviceProcessEvents`
- Queried **DeviceNetworkEvents** to identify PowerShell connections to external IP addresses (*Figure 1*)
  - Observed PowerShell initiating outbound connections to an external IP Address (*Figure 2*)
    - This was observed from a user who's not in the Tech department, which is unexpected behaviour
    - Furthermore, it is only seen once in our environment.
      
- Pivoted to **DeviceProcessEvents** to determine how PowerShell was executed
- Queried for PowerShell executions (*Figure 3*)
  - Identified PowerShell being spawned by another process (e.g. `cmd.exe`)
    - Noted that adversaries usually spawn PowerShell via a process such as (winword.exe, cmd.exe, excel.exe, rundll32.exe, etc).
      - Upon further investigation, the command that was used was to onboard our Virtual Machine onto Microsoft Defender for Endpoint for monitoring (*Figure 4*)
 
## SOC Relevance

- Demonstrates end-to-end threat hunting using hypothesis-driven investigation
- Shows how to pivot between network and process telemetry to build an attack narrative
- Highlights common attacker techniques such as living-off-the-land and fileless execution
- Reinforces the importance of understanding normal user behaviour to identify anomalies

## Screenshots

<p align="center">
  <img width="1048" height="611" alt="image" src="https://github.com/user-attachments/assets/7a5f1682-16ae-4336-a3e2-d23f4daee6e3" />
</p>
<p align="center"><b>Figure 1: Advanced Hunting Query identifying PowerShell outbound network Connections</b></p>


<p align="center">
  <img width="324" height="597" alt="image" src="https://github.com/user-attachments/assets/54e7c9ac-b7be-47d8-8444-f36509e99dad" />
</p>
<p align="center"><b>Figure 2: IP Address enrichment details viewed from Microsoft Defender for Endpoint</b></p>



<p align="center">
  <img width="1031" height="237" alt="image" src="https://github.com/user-attachments/assets/596781c3-da22-460e-8790-abefd9f6bd30" />
</p>
<p align="center"><b>Figure 3: Advanced Hunting query showing Powershell spawned by parent process (cmd.exe)</b></p>



<p align="center">
  <img width="391" height="218" alt="image" src="https://github.com/user-attachments/assets/f0fd08b7-166f-4376-adb7-00cd85d38fd6" />
</p>
<p align="center"><b>Figure 4: PowerShell execution with execution policy bypass spawned by cmd.exe</b></p>
