# Day 27 – Ingesting Entra ID Identity Logs into Microsoft Sentinel

## Objective 
- Send Entra ID **sign-in** and **audit logs** to Sentinel so identity events can be investigated with endpoint and email data in one place.

## Platform / Tools 
- Microsoft Sentinel
- Entra ID 


## Actions Performed 
- Installed Entra ID Data Connector in Sentinel (*Figure 1*)
- Configured the Data Connector to forward logs over to Sentinel. Logs include Sign-In, Audit, and Risky user logs. (*Figure 2*)
- Simulated standard user sign-in with our user John Doe and viewed the sign-in table within Sentinel (*Figure 3*)
- Generated Audit Log Telemetry by disabling security defaults within Entra ID (*Figure 4*)

## SOC Relevance
- By ingesting telemetry from Entra ID into Sentinel, we gain visibility into:
  - Risky Sign-In
  - Administrative changes
  - Risky user
- This is good for correlation between endpoint, Emails and identity. 






## Screenshots 

<p align="center">
  <img width="380" height="535" alt="image" src="https://github.com/user-attachments/assets/3f60f488-7132-4a19-acae-b180dddb45c8" />
</p>
<p align="center"><b>Figure 1: Entra ID Data connector Installation via Content Hub</b></p>


<p align="center">
  <img width="799" height="833" alt="image" src="https://github.com/user-attachments/assets/828e6d23-d80f-4167-aac7-8bf0590e3526" />
</p>
<p align="center"><b>Figure 2: Configuration of Entra ID data connector</b></p>

<p align="center">
  <img width="1267" height="226" alt="image" src="https://github.com/user-attachments/assets/8a005d9d-0cd4-47a2-b7fc-1fb5e6a5ee93" />
</p>
<p align="center"><b>Figure 3: Successful Entra ID sign-in event displayed in the Sentinel SigninLogs table</b></p>


<p align="center">
  <img width="649" height="701" alt="image" src="https://github.com/user-attachments/assets/61b5156f-7bfb-4b85-9e27-4dab8c3a409a" />
</p>
<p align="center"><b>Figure 4: Audit log entry showing “Update security defaults” operation with timestamp recorded in Entra ID</b></p>
