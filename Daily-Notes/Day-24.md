# Day 24 - Introduction to Entra ID & Entra ID protection 

## Objective
- Shift our focus from **Endpoint Secuirty** to **Idenity** and learn how:
  - Microsoft **Entra ID** manages Identities
  - How attackers abuse Identities
  - How **Entra ID Protection** detects risky users and Sign-ins
 
  ## Platform / Tools
  - Microsoft Entra Admin Centre
  - Microsoft Entra ID Protection
 
## Action Performed 
- Navigated to Entra ID Centre > Monitoring & Health to understand how logs are stored under `Sign-in logs` and `Audit Logs`
- Navigated to Entra ID Protection and reviewed each section (*Figure 1*):
  - Conditional Access
  - User Risk Policy
  - Sign-In Risk Policy
  - Multifactor Authentication Registration Policy
- Reviewed how Microsoft creates reports for:
  - Risky users
  - Risk workload identities
  - Risk Sign-ins
    - This will be essential for the coming days 


## SOC Relevance
- Identity is a primary intrusion vector in most modern breaches.
- Entra ID logs provide visibility into account takeover, MFA failures, impossible travel, Risky User behaviour, etc.
- Risky users help analysts identify compromised accounts over time.
- Risky Sign-ins help detect malicious single-session authentication attempts.
- Audit logs allow investigation of privilege escalation and tenant configuration. 




## Screenshots

<p align="center">
 <img width="1634" height="871" alt="image" src="https://github.com/user-attachments/assets/c8ff5535-5c95-4127-b2e1-78219066023d" />
</p>
<p align="center"><b>Figure 1: Overview of Identity Protection Dashboard</b></p>
