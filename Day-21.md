# Day 21 – Forming Threat Hunting Hypotheses

## Objective
- Understand what threat hunting is and why it is important
- Learn how to proactively search for malicious activity that has not triggered alerts
- Identify different types of threat hunting
- Learn how to form effective and actionable hunting hypotheses


## Platform / Tools
- Microsoft Defender for Endpoint
- Microsoft Defender XDR
- Advanced Hunting (KQL)


## Actions Performed
- Reviewed the concept of threat hunting as a **proactive** security practice
- Distinguished between:
  - Alert-driven (reactive) investigations
  - Threat hunting (proactive assumption of compromise)
- Learned that threat hunting begins with forming a **hypothesis**
- Studied the three main types of threat hunting:
  - `Structured hunting`
    - Based on known attacker behaviour
    - Uses frameworks such as MITRE ATT&CK
    - Example: Hypothesising credential dumping from LSASS
  - `Unstructured hunting`
    - Starts from an indicator of compromise
    - Expands investigation to related processes or hosts
  - `Situational hunting`
    - Focuses on high-risk assets, users, or applications
    - Prioritises hunts based on business impact
- Defined the characteristics of a good hunting hypothesis:
  - `Relevant` – applies to the specific environment and data sources
  - `Specific` – clearly defines attacker behaviour being investigated
  - `Answerable` – supported by available telemetry to confirm or disprove
 
## SOC Relevance
- Threat hunting allows SOC analysts to detect threats that bypass traditional alerts
- Developing strong hypotheses improves investigation efficiency and accuracy
- Understanding hunting types helps analysts choose the right approach based on context
