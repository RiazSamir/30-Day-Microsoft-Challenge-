# Day 19 – Integrating Intune & Configuring Attack Surface Reduction (ASR) Rules


## Objective
- Integrate Microsoft Intune to manage endpoints at scale
- Configure Attack Surface Reduction Rules
- Enforce Microsoft Defender for Endpoint Security settings via Intune
- Understand how Intune acts as the policy deployment engine for Defender

## Platform / Tools
- Microsoft Intune
- Microsoft Defender for Endpoint
- Windows 11 Virtual Machine

## Actions Performed 

- Enabled **Automatic Enrollment** in Microsoft Intune to allow devices joining Entra ID to be automatically managed (*Figure 1*)
- Joined the Windows 11 virtual machine to **Microsoft Entra ID** using a test user account (John Doe) via access work or school (*Figure 2*)
- Verified the device appeared as a managed endpoint within Intune (*Figure 3*)
- Enabled Intune integration with Microsoft Defender for Endpoint to allow Intune to enforce Defender security configurations
- Created an **Attack Surface Reduction (ASR) policy** within Intune (*Figure 5*)
- Configured selected ASR rules in Block/Warn mode based (*Figure 6*)
- Assigned the ASR policy to the custom device group


## SOC Relevance
- ASR rules help prevent common attacker techniques such as macro abuse, credential theft, and ransomware execution
- Intune acts as a central policy enforcement engine, ensuring consistent endpoint security enforcement the organisation. 



## Screenshots

<p align="center">
  <img width="1488" height="681" alt="image" src="https://github.com/user-attachments/assets/dea2253c-f130-437b-98a6-1f1cd0db277d" />
</p>
<p align="center"><b>Figure 1:Intune device Enrollment Options</b></p>


<p align="center">
  <img width="1007" height="788" alt="image" src="https://github.com/user-attachments/assets/42e28dda-927e-4751-8c6a-717f9757d218" />
</p>
<p align="center"><b>Figure 2: Joining a Windows 11 device to Microsoft Entra ID via “Access work or school”</b></p>

<p align="center">
  <img width="1007" height="788" alt="image" src="https://github.com/user-attachments/assets/42e28dda-927e-4751-8c6a-717f9757d218" />
</p>
<p align="center"><b>Figure 3: Device showing successful enrollment to Intune</b></p>


<p align="center">
  <img width="1653" height="612" alt="image" src="https://github.com/user-attachments/assets/0b8fa270-f654-4812-b545-536c17d43765" />
</p>
<p align="center"><b>Figure 4: Creating a new ASR policy</b></p>

<p align="center">
  <img width="940" height="629" alt="image" src="https://github.com/user-attachments/assets/43b6c21f-3293-498c-80da-1129f930256d" />
</p>
<p align="center"><b>Figure 5: Example ASR rules configured via Intune</b></p>
