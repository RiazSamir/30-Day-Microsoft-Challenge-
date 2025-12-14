# Day 4 - Data Source Onboarding & Initial KQL Analysis

## Objective 

- To connect our First Data Source to Sentinel
- Begin Querying Logs using KQL

## Platform / Tools 
- Microsoft Sentinel
- Azure Activity Logs
- Log Analytics Workspace
- Kusto Query Language (KQL)
- Sentinel Content Hub

## Actions Performed 
- Exported Azure Actvity Logs to our Log Analytics Workspace so that Sentinel would be able to Query the Logs (*Figure 1*)
- Downloaded Azure Activity via Content Hub as Data Connectors are required to get data oboarded onto Sentinel (*Figure 2*)
- Downloaded Sentinel Training via Azure Portal so that we can start querying sample logs via KQL (*Figure 3*)

## SOC Relevance
- Azure Activity logs provide visibility into subscription-level administrative actions
-  Validating data ingestion ensures reliable telemetry before detection rule creation
- Practicing KQL enables effective investigation and threat hunting in Sentinel  


## Screenshots


<p align="center">
  <img width="1139" height="766" alt="image" src="https://github.com/user-attachments/assets/60ab76e2-6704-4695-84e4-6f6629884865" />
</p>
<p align="center"><b>Figure 1: Exporting Azure Activity Logs to Our LAW (SOC-PROJECT-SAMIR-LAW) </b></p>

<p align="center">
  <img width="1498" height="286" alt="image" src="https://github.com/user-attachments/assets/61d56a38-f4b8-41b9-994f-5f3657a7743d" />
</p>
<p align="center"><b>Figure 2: Downloading Azure Activity via Content Hub </b></p>

<p align="center">
  <img width="805" height="674" alt="image" src="https://github.com/user-attachments/assets/f4b1ff9f-309e-4f82-93e1-65f02e8989f1" />
</p>
<p align="center"><b>Figure 3: Sentinel Training Solution deployed for KQL practice</b></p>

