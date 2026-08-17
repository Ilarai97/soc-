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

  

