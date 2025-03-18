# Vulnerability Management Program Implementation

In this project, we simulate the implementation of a comprehensive vulnerability management program, from inception to completion.

_**Inception State:**_ the organization has no existing policy or vulnerability management practices in place.

_**Completion State:**_ a formal policy is enacted, stakeholder buy-in is secured, and a full cycle of organization-wide vulnerability remediation is successfully completed.

---

<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cfc5dbcf-3fcb-4a71-9c13-2a49f8bab3e6">

# Technology Utilized
- Tenable (enterprise vulnerability management platform)
- Azure Virtual Machines (Nessus scan engine + scan targets)
- PowerShell & BASH (remediation scripts)

---


# Table of Contents

- [Vulnerability Management Policy Draft Creation](#vulnerability-management-policy-draft-creation)
- [Mock Meeting: Policy Buy-In (Stakeholders)](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [Policy Finalization and Senior Leadership Sign-Off](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [Mock Meeting: Initial Scan Permission (Server Team)](#step-4-mock-meeting-initial-scan-permission-server-team)
- [Initial Scan of Server Team Assets](#step-5-initial-scan-of-server-team-assets)
- [Vulnerability Assessment and Prioritization](#step-6-vulnerability-assessment-and-prioritization)
- [Distributing Remediations to Remediation Teams](#step-7-distributing-remediations-to-remediation-teams)
- [Mock Meeting: Post-Initial Discovery Scan (Server Team)](#step-8-mock-meeting-post-initial-discovery-scan-server-team)
- [Mock CAB Meeting: Implementing Remediations](#step-9-mock-cab-meeting-implementing-remediations)
- [Remediation Round 1: Outdated Wireshark Removal](#remediation-round-1-outdated-wireshark-removal)
- [Remediation Round 2: Insecure Protocols & Ciphers](#remediation-round-2-insecure-protocols--ciphers)
- [Remediation Round 3: Guest Account Group Membership](#remediation-round-3-guest-account-group-membership)
- [Remediation Round 4: Windows OS Updates](#remediation-round-4-windows-os-updates)
- [First Cycle Remediation Effort Summary](#first-cycle-remediation-effort-summary)

---

### Vulnerability Management Policy Draft Creation

This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.  
[Draft Policy](https://docs.google.com/document/d/1CLSWm1_9JL1oUqgyNNwtPXW6FzXJ7ddVnSAUQTyqC8I/edit?usp=drive_link)

---

### Step 2) Mock Meeting: Policy Buy-In (Stakeholders)

In this phase, a meeting with the server team introduces the draft Vulnerability Management Policy and assesses their capability to meet remediation timelines. Feedback leads to adjustments, like extending the critical remediation window from 48 hours to one week, ensuring collaborative implementation.

# Policy Discussion

**Fred:** Good morning, James. How has everything been? I know everyone’s been busy these last few weeks.  

**James:** Good morning, Fred. Yeah, it’s been a bit hectic, but we’re hanging in there. Thanks for asking. I had a chance to read through the policy draft, and overall, it makes sense. However, with our current staffing, we can’t meet the aggressive remediation timelines, especially the 48-hour window for critical vulnerabilities.  

**Fred:** Yeah, I totally understand. It is a bit aggressive, especially to start. Perhaps we can extend the critical close to one week for now as a compromise, and reserve the 48-hour window for really severe, zero-day vulnerabilities.  

**James:** That sounds reasonable. We appreciate the flexibility. Could we have a bit of leeway in the beginning as we get used to the remediation and patching process? Maybe for the first few months?  

**Fred:** Absolutely. Once the policy is finalized, we’ll officially start the program. But we’re planning to give all departments about six months to adjust and get familiar with the process. Does that sound fair?  

**James:** Thanks, Fred. We’ll do our best. I appreciate you including us in the decision-making process. It really makes us feel like we’re part of the solution.  

**Fred:** Of course! We’re all in this together. Thanks for working with us.  

**James:** No problem. Thanks for keeping the meeting short.  

**Fred:** Yeah, those are my favorite types. Bye for now.  

**James:** See you later!  


---

### Step 3) Policy Finalization and Senior Leadership Sign-Off

After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.  
[Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link)
<div style="text-align: center;">
    <img src="https://github.com/user-attachments/assets/9afcdbc1-0493-4af2-9287-1cb9b8f59b40" alt="image" width="400">
</div>

---

### Step 4) Mock Meeting: Initial Scan Permission (Server Team)

The team collaborates with the server team to initiate scheduled credential scans. A compromise is reached to scan a single server first, monitoring resource impact, and using just-in-time Active Directory credentials for secure, controlled access.  

# Vulnerability Scan Discussion  

**Fred:** Morning!  

**Alex:** Good morning. I heard you're ready to conduct some scans.  

**Fred:** Yep! Now that our vulnerability management policy is in place, I wanted to start scheduling credentialed scans of your environment.  

**Alex:** Sounds good. What’s involved, and how can we help?  

**Fred:** We're planning to run weekly scans on the server infrastructure. We estimate it will take about 4 to 6 hours to scan all 2,200 assets. We'll need administrative credentials to allow the scan engine to remotely log into the targets for a more thorough assessment.  

**Alex:** Whoa, hold on. What exactly does the scanning process entail? I'm concerned about resource utilization. Also, you need admin credentials for all 200 machines? That doesn’t sound very secure.  

**Fred:** Those are valid concerns. The scan engine sends specific traffic to the servers to check for vulnerabilities. It looks into registry settings, outdated software, and insecure protocols or cipher suites. That’s why we require credentials—to perform a deeper, more accurate assessment.  

**Alex:** I see. As long as it doesn’t impact server availability, we should be okay.  

**Fred:** Absolutely. Let’s start by scanning a single server and monitor resource utilization before expanding the scope.  

**Alex:** Not a bad idea. Regarding credentials, can you use Active Directory? Maybe set up dedicated credentials that remain disabled until the scan begins, then re-enable them just for the scan. Once it's finished, we can deprovision or disable them again—kind of a just-in-time access approach.  

**Fred:** That sounds perfect. I'll ask Susan to automate the account provisioning process.  

**Alex:** Great. Let me know when the credentials are set up.  

**Fred:** Will do. Talk soon!  

**Alex:** See you later.  



[YouTube Video: Initial Discovery Scan](https://youtu.be/lg068WA4SKM)

---

### Step 5) Initial Scan of Server Team Assets

In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.  

![image](https://github.com/user-attachments/assets/c7ad0fa4-470a-4725-be8f-feb459ae139f)


[Scan 1 - Initial Scan](https://drive.google.com/file/d/1RBPVj_azKJMwmRZ8QILlb4hxIjQU3wQ7/view?usp=drive_link)




---

### Step 6) Vulnerability Assessment and Prioritization

We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Wireshark)
2. Windows OS Secure Configuration (Protocols & Ciphers)
3. Windows OS Secure Configuration (Guest Account Group Membership)
4. Windows OS Updates

---

### Step 7) Distributing Remediations to Remediation Teams

The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.  

<img width="635" alt="image" src="https://github.com/user-attachments/assets/bbf9478f-e1d1-4898-846e-b510ec8c6f72">

[Remediation Email](https://github.com/joshmadakor1/lognpacific-public/blob/main/misc/remediation-email.md)

---

### Step 8) Mock Meeting: Post-Initial Discovery Scan (Server Team)

The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB). 

# Vulnerability Scan Discussion  

**Fred:** Morning! How are you doing?  

**James:** Not bad for a Monday. And you?  

**Fred:** Still alive, so I can’t complain. Before we dive into the vulnerabilities, how did the scan go on your end? Any outages, overutilization, or other issues?  

**James:** The scan went well. We were monitoring it, and aside from all the open connections, we wouldn’t have even noticed it was happening.  

**Fred:** That’s good news. I expected as much. We’ll keep monitoring going forward, but I don’t anticipate any resource utilization issues. Do you mind if I jump into the vulnerability findings?  

**James:** Not at all, go ahead.  

**Fred:** Cool. I’ll share my screen real quick.  

The majority of these vulnerabilities stem from Wireshark being installed—it’s just super outdated. That’s the main issue.  

One interesting thing I found is that the local guest account on the servers belongs to a group—and that group is part of the local administrators group. I’m not sure why that is.  

Some vulnerabilities might resolve themselves through Windows updates, like this Microsoft Edge Chromium one. I’m also unsure about another one, but it could be fixed by updates as well.  

We don’t need to worry about the self-signed certificate since it’s just the computer’s own certificate. However, the medium-strength cipher suites and the use of TLS 1.0 and 1.1 are more concerning. These are deprecated and should be addressed.  

So, in summary, our focus should be on updating Wireshark, addressing insecure protocols and cipher suites, and removing the guest account from the admin group.  

**Fred:** That’s interesting. The good news is that most of our servers likely have the same vulnerabilities, so remediation should be more straightforward.  

**James:** Yeah, a uniform setup actually helps. Do you foresee any issues with fixing the cipher suites and insecure protocols?  

**Fred:** I highly doubt it. We’ll run it through the next Change Control Board. Uninstalling Wireshark and fixing the guest account shouldn’t be an issue either—those shouldn’t have been on the servers in the first place. I’ll check with our sysadmins about that.  

**James:** Sounds good. I’ll start building out some remediation packages to make the fixes easier on your end.  

**Fred:** That would be great. Oh, by the way, do you have something in place to handle the Windows update-related vulnerabilities? Do you already have patch management set up?  

**James:** Yep, I’m not too worried about that. Windows updates should take care of those automatically by next week. We have a patch management system in place.  

**Fred:** Excellent. I’ll research the best way to remediate these issues and update you before the next Change Control Board meeting.  

**James:** Sounds good. Talk to you soon.  

**Fred:** Cool, talk soon!  

---

### Step 9) Mock CAB Meeting: Implementing Remediations

The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.  

<a href="https://youtu.be/zOFPkTa9kY8" target="_"><img width="600" src="https://github.com/user-attachments/assets/07164e63-fbce-471a-b469-29a6d41b7bb8"/></a>

[Meeting Video](https://youtu.be/zOFPkTa9kY8)

---
### Step 10 ) Remediation Effort

#### Remediation Round 1: Outdated Wireshark Removal

The server team used a PowerShell script to remove outdated Wireshark. A follow-up scan confirmed successful remediation.  
[Wireshark Removal Script](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-wireshark-uninstall.ps1)  

![image](https://github.com/user-attachments/assets/2f81470a-40d5-4d5e-8b64-a01643d0d2f4)



[Scan 2 - Third Party Software Removal](https://drive.google.com/file/d/1UiwPPTtuSZKk02hiMyXf31pXUIeC5EWt/view?usp=drive_link)


#### Remediation Round 2: Insecure Protocols & Ciphers

The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.  
[PowerShell: Insecure Protocols Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-protocols.ps1)
[PowerShell: Insecure Ciphers Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-cipher-suites.ps1)

![image](https://github.com/user-attachments/assets/3b7cf460-998f-4efd-ac4d-68e559f1ad61)


[Scan 3 - Ciphersuites and Protocols](https://drive.google.com/file/d/1Qc6-ezQvwReCGUZNtnva0kCZo_-zW-Sm/view?usp=drive_link)


#### Remediation Round 3: Guest Account Group Membership

The server team removed the guest account from the administrator group. A new scan confirmed remediation, and the results were exported for comparison.  
[PowerShell: Guest Account Group Membership Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-guest-local-administrators.ps1)  

![image](https://github.com/user-attachments/assets/bf951178-785f-492b-9338-f8bca30db225)


[Scan 4 - Guest Account Group Removal](https://drive.google.com/file/d/1jVgikjfrV1YjOcL3QRT_oUB0Y82w22V7/view?usp=drive_link)


#### Remediation Round 4: Windows OS Updates

Windows updates were re-enabled and applied until the system was fully up to date. A final scan verified the changes  

![image](https://github.com/user-attachments/assets/9f5d3fa9-25c2-44c9-ad3b-678cdcb4d539)


[Scan 5 - Post Windows Updates](https://drive.google.com/file/d/1tmDjeHl5uiGitRwWy8kFRi33q-nGi1Zt/view?usp=drive_link)

---

### First Cycle Remediation Effort Summary

The remediation process reduced total vulnerabilities by 80%, from 30 to 6. Critical vulnerabilities were resolved by the second scan (100%), and high vulnerabilities dropped by 90%. Mediums were reduced by 76%. In an actual production environment, asset criticality would further guide future remediation efforts.  

![image](https://github.com/user-attachments/assets/4c2f2d9c-aaa9-4bea-a372-8420109e9601)


[Remediation Data](https://docs.google.com/spreadsheets/d/1FTtFfZYmFsNLU6pm8nTzsKyKE-d2ftXzX_DPwcnFNfA/edit?gid=0#gid=0)

---

### On-going Vulnerability Management (Maintenance Mode)

After completing the initial remediation cycle, the vulnerability management program transitions into **Maintenance Mode**. This phase ensures that vulnerabilities continue to be managed proactively, keeping systems secure over time. Regular scans, continuous monitoring, and timely remediation are crucial components of this phase. (See [Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link) for scanning and remediation cadence requirements.)

Key activities in Maintenance Mode include:
- **Scheduled Vulnerability Scans**: Perform regular scans (e.g., weekly or monthly) to detect new vulnerabilities as systems evolve.
- **Patch Management**: Continuously apply security patches and updates, ensuring no critical vulnerabilities remain unpatched.
- **Remediation Follow-ups**: Address newly identified vulnerabilities promptly, prioritizing based on risk and impact.
- **Policy Review and Updates**: Periodically review the Vulnerability Management Policy to ensure it aligns with the latest security best practices and organizational needs.
- **Audit and Compliance**: Conduct internal audits to ensure compliance with the vulnerability management policy and external regulations.
- **Ongoing Communication with Stakeholders**: Maintain open communication with teams responsible for remediation, ensuring efficient coordination.

By maintaining an active vulnerability management process, organizations can stay ahead of emerging threats and ensure long-term security resilience.
