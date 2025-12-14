# Day 05 – Dashboard Dashboards

## Objective:
- Create a dashboard to support investigations and triage of authentication Activity


## Platofrm / Tools:
- Microsoft Sentinel
- Sentinel Workbooks
- Kusto Query Language


## Actions Performed:
- Navigated to Workbooks in Sentinel to gain an understanding of its layout (*Figure 1*)
- Built KQL queries to summarise failed logon attempts (Event ID 4625) by user account (*Figure 2*)
- Created a Sentinel workbook to visualise failed authentication activity (*Figure 3*)

## SOC Importance
- Visualising failed logon attemps help identify brute force or credential misuse attemps
- Workbooks supports faster triage without repeatedly running manual queries. 


## Screenshots


<p align="center">
  <img width="1580" height="788" alt="image" src="https://github.com/user-attachments/assets/49b7d5b1-5eb1-4409-9da9-472f05f54ed9" />
</p>
<p align="center"><b>Figure 1: Overview of Workbooks within Sentinel</b></p>

<p align="center">
  <img width="403" height="769" alt="image" src="https://github.com/user-attachments/assets/12b00e34-2375-4f7e-8c76-e41b72b56a26" />
</p>
<p align="center"><b>Figure 2: KQL Query to summarize failed logon attempts in a decending order. </b></p>

<p align="center">
  <img width="1518" height="836" alt="image" src="https://github.com/user-attachments/assets/aaae55b1-1f42-4271-8dbc-7812df6118fe" />
</p>
<p align="center"><b>Figure 3: Newly created Dashboard which summarizes the top failed logon attemps ina decending order </b></p
