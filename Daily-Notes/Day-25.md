# Day 25 - Conditional Access Based on Sign-in Risk


## Objective 
Create and test Conditional Access policies that react to risky sign-ins and observe how Entra ID blocks or interrupts suspicious logins.

## Platform / Tools
- Microsoft Entra ID
- Entra ID Protection 
- Conditional Access
- Outlook Web App
- VPN

## Actions Performed 
- Reviewed the difference between **user risk vs sign-in risk**
- Generated normal sign-in telemetry for our test user John Doe and reviewed the Sign-In logs under monitoring and health (*Figure 1*)
- Connected to Belgium via a VPN to simulate a risky sign-in
  - Upon logging in, we are prompted by Multi-Factor Authentication (MFA) (*Figure 2*)
    - Checked Risky Sign-Ins within Identity Protection to review the telemetry produced and saw the logon attempt (*Figure 3*)
      - This was done because of the Security Default Policy created by Microsoft (*Figure 4*)
- Disabled Security Defaults and created a Country-Based Conditional List based on Named Locations (*Figure 5*)
  - Applied this to a Policy and set this `block` (*Figure 6*)
    - Once applied, another sign-in was simulated using the IP Address from Belgium which we received the error message `You cannot access this right now` (*Figure 7*)


## SOC Relevance
- Demonstrates preventing account takeover using Conditional Access Policies
- Shows how Risky-Ins are detected and blocked
- Reinforces incident investigation using sign-in and risk logs. 


## Screenshots

<p align="center">
  <img width="1593" height="94" alt="image" src="https://github.com/user-attachments/assets/1dece98d-98f4-4c04-8942-6cdc640ed823" />
</p>
<p align="center"><b>Figure 1: Successful OWA sign-in for user John Doe with no conditional Access policy set up</b></p>


<p align="center">
  <img width="212" height="260" alt="image" src="https://github.com/user-attachments/assets/f8dac35e-21fe-4907-bbec-1859d9b3e2dc" />
</p>
<p align="center"><b>Figure 2: MFA prompt upon logging in via an IP Address from Belgium</b></p>


<p align="center">
  <img width="1238" height="92" alt="image" src="https://github.com/user-attachments/assets/96bd7256-428e-438d-956c-8d2a6f84ebe2" />
</p>
<p align="center"><b>Figure 3: Risky OWA sign-in attempt attempted from foreign IP address</b></p>


<p align="center">
  <img width="673" height="239" alt="image" src="https://github.com/user-attachments/assets/7d3f5d15-8741-408b-88d4-ce234e9fc386" />
</p>
<p align="center"><b>Figure 4: Sign-in interrupted by Security Defaults enforcing MFA, resulting in authentication failure</b></p>


<p align="center">
  <img width="456" height="402" alt="image" src="https://github.com/user-attachments/assets/81537b3f-1271-4349-980d-a26904c023b9" />

</p>
<p align="center"><b>Figure 5: Configuration of new conditional access, which lists countries to block. </b></p>



<p align="center">
  <img width="456" height="402" alt="image" src="https://github.com/user-attachments/assets/81537b3f-1271-4349-980d-a26904c023b9" />

</p>
<p align="center"><b>Figure 6: Creating a Conditional Access policy configured to block access based on Blocked countries </b></p>



<p align="center">
  <img width="370" height="316" alt="image" src="https://github.com/user-attachments/assets/375cd1e6-1e0d-4b14-a814-e60caf54c9cd" />
</p>
<p align="center"><b>Figure 7: Conditional Access policy blocking sign-in despite successful authentication</b></p>
