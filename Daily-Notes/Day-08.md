# Day 08 - Threat Hunting with Sentinel Bookmarks

## Objective:
- Use Sentinel bokmakrs to capture investigation evidence
- Convert notable hunting finding into a manual incident

## Platform / Tools:
- Microsoft Sentinel
- KQL
- OfficeActivity_CL
- Hunting

## Actions Performed
- Queried Office 365 audit activity using the OfficeActivity_CL table
- Reviewed Operations found in OfficeActivity_CL (*Figure 1*)
- Reviewed the "FileAccessed" operation to locate any suspicious IPs which we did find. A SharePoint file access event was observed originating from an
unseen external IP address, differing from the user’s normal access pattern. This activity was bookmarked for further investigation (*Figure 2 - 3*)
- Navigated to "Hunting" on Sentinel to create a Manuel Incident from our Bookmark created (*Figure 4 - 5*)


## SOC Relevance
- Bookmarks allow analysts to preserve investigation evidence during threat hunting
- Converting Bookmarks into incidents enables structured triage and escalation

## Screenshots

<p align="center">
  <img width="546" height="833" alt="image" src="https://github.com/user-attachments/assets/559fa37a-882b-46d0-9fc5-eb0beebcf17f" />
</p>
<p align="center"><b>Figure 1: Review of the different Operations availble to us in the OfficeActivity_CL table </b></p>


<p align="center">
  <img width="1226" height="279" alt="image" src="https://github.com/user-attachments/assets/5406b780-6359-43df-ac44-cbe4c0401aa0" />
</p>
<p align="center"><b>Figure 2: Utilising the Bookmark feature for suspicious logs observed.</b></p

<p align="center">
  <img width="567" height="643" alt="image" src="https://github.com/user-attachments/assets/510c7cc9-e9b2-4355-b825-b5443ea9135e" />
</p>
<p align="center"><b>Figure 3: Utilising the Bookmark feature for suspicious logs observed.</b></p


<p align="center">
  <img width="871" height="548" alt="image" src="https://github.com/user-attachments/assets/3420ce3f-d847-49c3-9a75-595056a7f76e" />
</p>
<p align="center"><b>Figure 4: Manuel Incident creation from our generated Bookmark</b></p

<p align="center">
  <img width="819" height="352" alt="image" src="https://github.com/user-attachments/assets/ab13b3a1-db88-4951-b72d-1f310c6cefaf" />
</p>
<p align="center"><b>Figure 5: Manuel Incident creation from our generated Bookmark</b></p
