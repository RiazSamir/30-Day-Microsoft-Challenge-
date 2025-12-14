# Day 07 – Brute Force Investigation Report

## Objective:
- Investigate a "multiple Failed Logons" alert created via day 06
- Determine affected accounts/hosts and indentify and successful logons
- Provide Recommendations as if this were a client Incident

## Platform / Tools:
- Microsoft Sentinel
- KQL (SecurityEvent_CL)

## Actions Performed:
- Queried failed logon events (Event ID 4625) and summarised by host and account (*Figures 1 - 2*)
- Queried successful logons (Event ID 4624) to identify potential account compromise (*Figure 3*)
- Documented findings and recommended response actions

## Report

### Findings:
- Hosts affected:
  - SHIR-HIVE
  - SOC-FW-RDP
- Accounts targeted:
  - \ADMINISTRATOR
  - \ADMIN
  - \admin
- High-volume failed logons observed within a short time window, consistent with brute force activity (*Figure 1–2*)
- Successful logons were observed during the same period, indicating possible compromise and requiring immediate validation (*Figure 3*)

### Investigation Summary:
- On 2025-12-06 around 20:47 UTC, multiple failed logons were recorded on SOC-FW-RDP and SHIR-HIVE.
- SOC-FW-RDP: \ADMINISTRATOR (~9997) and \ADMIN (~503) failed logons (*Figure 1*)
- SHIR-HIVE: \admin (~1988) and \administrator (~1740) failed logons (*Figure 2*)
- Successful logons were present in the dataset (*Figure 3*). Further validation is required to confirm legitimacy vs compromise.



### Recommendations:
- Treat impacted local admin accounts as potentially compromised until verified
- Reset passwords and review authentication activity for those accounts
- Implement account lockout / password policy controls where appropriate
- Restrict remote use of local accounts (prefer privileged domain accounts / PIM where applicable)
- If available, ingest richer telemetry (source IP, logon type) to improve triage accuracy

## SOC Relevance:
- Failed logon spikes can indicate password spraying/brute force and often precede account takeover
- Confirming successful logons after brute force is critical for determining incident severity
- Host + account scoping enables rapid containment decisions

## Screenshots

<p align="center">
  <img width="498" height="363" alt="image" src="https://github.com/user-attachments/assets/87606d4d-a8ab-4fcf-8a88-51a5802c4053" />
</p>
<p align="center"><b>*Figure 1: Failed logons by account on SOC-FW-RDP (Event ID 4625)* </b></p>

<p align="center">
  <img width="500" height="360" alt="image" src="https://github.com/user-attachments/assets/bce85c9e-7968-4f80-9139-3d7f799baef8" />
</p>
<p align="center"><b>*Figure 2: Failed logons by account on SHIR-HIVE (Event ID 4625)* </b></p>

<p align="center">
  <img width="536" height="693" alt="image" src="https://github.com/user-attachments/assets/042ee26e-fa70-49b0-9ca5-2259a1cac9f7" />
</p>
<p align="center"><b>*Figure 3: Successful Logons Summar (Event ID 4625)* </b></p>
