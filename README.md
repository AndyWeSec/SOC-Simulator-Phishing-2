# SOC-Simulator-Phishing-2
A secondary end-to-end incident response lab simulating an enterprise phishing attack vector. Documents email header triage, malicious payload hashing, and threat intelligence lookups using VirusTotal, alongside blue-team detection engineering, log ingestion, and alert generation within Elastic SIEM.

### Tools Used
* Training Platform: TryHackMe SOC Simulator
* SIEM Platform: SPLUNK Enterprise
* Threat Intelligence: VirusTotal

### SOC Phishing Simulator & Incident Response Lab
* Attack Simulation: Simulated an enterprise phishing attack vector within an isolated sandbox environment to generate realistic endpoint and network telemetry.
* Threat Intelligence: Analysed raw email headers and extracted malicious payload hashes, leveraging VirusTotal to validate indicators of compromise (IoCs).
* SIEM Detection Engineering: Developed custom queries and alert rules within SPLUNK SIEM to detect post-exploitation activity, suspicious process spawning, and unauthorized network connections.
* OC Analyst Workflow: Completed hands-on training via the TryHackMe SOC Simulator to master real-time queue management, alert prioritization, and threat triage.

### Gained Core Competencies: 
* Email Artifact Triage: Spotting advanced social engineering red flags, typosquatted domains, spoofed senders, and masked malicious hyperlinks.
* Log Analysis & Correlation: Cross-referencing endpoint events and network proxy logs to track user click-through behavior on link lures.
* Incident Classification: Differentiating between True Positives and False Positives to draft comprehensive, structured blue team incident reports.

## Inside a Live Phishing Attack: Real-Time Breach Analysis and Documentation
This project showcases my ability to detect, analyse, and document a live phishing campaign unfolding within a corporate network. Operating under high-pressure conditions, I mapped out each phase of the attack lifecycle to stop the breach and strengthen network defences.

### Scenario Background
<img width="1470" height="778" alt="Screenshot 2026-06-24 at 19 33 54" src="https://github.com/user-attachments/assets/c69d0afc-db2e-4560-9d93-8f3fde655873" />

<img width="1470" height="778" alt="Screenshot 2026-06-24 at 19 34 05" src="https://github.com/user-attachments/assets/3c841ad3-87a4-46c0-88d2-ce41490a47f4" />

<img width="1470" height="778" alt="Screenshot 2026-06-24 at 19 34 17" src="https://github.com/user-attachments/assets/0e134c50-4245-419e-a003-f92e540f6bb0" />

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 36 52" src="https://github.com/user-attachments/assets/727bc848-9a75-4bb0-adc1-14a7051632ba" />

## Alert 1: Inbound Phishing Triage

### Initial Alert: Alert triggers in the queue for a "Suspicious email from external domain". The log captures an inbound message from eileen@trendymillionaires.me targeting support@trythatme.me with a clear social engineering lure regarding a fake "billionaire Relative" inheritance.

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 39 15" src="https://github.com/user-attachments/assets/7d990be6-d314-420e-acb3-6d01188d2b33" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 41 05" src="https://github.com/user-attachments/assets/0a469a23-0ad9-4ffc-bb6d-5b35cfb93be2" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 41 42" src="https://github.com/user-attachments/assets/1d9eb4ad-a6eb-4b95-bddd-58deaa22f85c" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 42 05" src="https://github.com/user-attachments/assets/ce2281d7-f8f9-400a-b780-49655e0127db" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 42 58" src="https://github.com/user-attachments/assets/8ed9a5e1-e61f-463b-92cb-9ac8a9c60acd" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 43 07" src="https://github.com/user-attachments/assets/49031760-76ba-45f2-9259-945c12b7d673" />

### Log Lanalysis: A deep-dive query inside SPLUNK Enterprise reveals broader campaign activity hitting the mail servers. Splunk catches a second concurrent phishing email variation from lucie@trendymillionaire.me pushing a fake "certified hat designer" job offer to a different employee.

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 46 08" src="https://github.com/user-attachments/assets/d0f1c5f2-fd82-427c-a09f-a4f11ba81c8f" />

### Threat Intelligence: The senders root domain (trendymillionaires.me) is pivoted to VirusTotal. While it returns a 0/91 clean vendor reputation score due to the domain being newly registered, the suspicious top level domain and explicit financial/credentials lure validate malicious intent.

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 51 40" src="https://github.com/user-attachments/assets/77cb8707-2c57-4960-b3a5-f8c843e30c3e" />

### Disposition and Resolution: Classified as a True Positive. The ticket is reso,lved by escalating the incident the initiate tenant-wide blocking of the sender domain cluster and recommending a block on the external sender address.


## Alert 2: Remore Desktop Clipboard Monitor
### Initial Alert: Alert triggers a high priority warning on host win-3450 flagging a "Suspicious Parent-Child Relationship". The monitoring system logs a core system hierachy anomally involving the process execution of rdpclip.exe.
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 55 56" src="https://github.com/user-attachments/assets/ce9f2b47-729b-4d6f-856e-cd58f1f3fd87" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 56 40" src="https://github.com/user-attachments/assets/8160bdfd-924f-437e-8d71-46f7bbcc4ac6" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 56 14" src="https://github.com/user-attachments/assets/466f55ba-86c5-4295-a8bd-a772ba16cb48" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 57 40" src="https://github.com/user-attachments/assets/12b9dddf-78b2-4537-b672-96f475c3a986" />

### Log Analysis: A targeted investigation of sysmon event logs within SPLUNK Enterprise is conducted to trace the execution path and command -line parameters of rdpclip.exe on host win-3450. The behaviour shows standard, benign initialization sequences, indicating no signs of binary masqerading, malicious argument injection, or memory tampering.

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 58 44" src="https://github.com/user-attachments/assets/cc8adfff-8098-45bf-b2fe-b045240971c3" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 59 12" src="https://github.com/user-attachments/assets/f889d56b-1be3-4753-af0d-b8646aa4f75c" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 59 56" src="https://github.com/user-attachments/assets/a82f2302-89f3-4580-91ca-4fe9b9360a21" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 01 05" src="https://github.com/user-attachments/assets/68eb68a2-9422-41a1-8c86-241b941545cd" />

### Threat Intelligence: Documentation from official Microsoft resources verifies that rdpclip.exe (remote Desktop Clipboard Monitor) is legitimate native Windows binary located in C:\windows\system32. It is tasked with managing clipboard translation and format synchrinization during active REmote Deskyop (RDP) sessions.

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 01 22" src="https://github.com/user-attachments/assets/8c07b035-f966-48bd-a313-9c473d2e07a4" />

### Disposition and Resolution: Classified as a False Positive. The alert was tripped by standard administration access over RDP. The ticket is documented and resolved with no further operational risk actions required.

### an update on alerts and their severity
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 06 56" src="https://github.com/user-attachments/assets/e0f25cda-95bf-4d4a-a002-b190d289fc6f" />


## Alert 3 True Positive after intense investogations following phishing emails and signs of exfiltration porcedures
### Inital Alert: This alert triggered a high severity warning in the queue for a "Suspicious Parent-Child Relationship" on host win-3450. The system flags an anomalous execution pattern where powershell.exe spawns nslookup.exe.
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 16 13" src="https://github.com/user-attachments/assets/9c348f0d-d299-4617-98f4-0fa296d27ad2" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 16 28" src="https://github.com/user-attachments/assets/870a1553-d984-4f1b-8ded-da1e6debf8fe" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 16 32" src="https://github.com/user-attachments/assets/86022be0-c2e2-4efc-97ac-ebfe91c76e44" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 16 45" src="https://github.com/user-attachments/assets/550c2452-8ad6-43e8-a55f-631c96eabbf0" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 17 21" src="https://github.com/user-attachments/assets/605530c3-c95f-400d-9508-7694f90e7af3" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 17 51" src="https://github.com/user-attachments/assets/5ee166bb-6816-468d-879f-b01cadbdcec4" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 18 24" src="https://github.com/user-attachments/assets/e934741d-dcc8-45a6-8878-53f3e5438d4d" />
<img width="924" height="502" alt="Screenshot 2026-06-24 at 20 20 07" src="https://github.com/user-attachments/assets/00bbfbd4-86f1-42dc-b09e-807941a3860c" />

### Log Analysis: A deep-dive query in SPLUNK Enterprise details a highly suspicious execution chain. The adversary is running obfuscated PowerShell scripts directly out of a localized folder (C:\Users\michael.ascot\downloads/exfiltration). SPLUNK log analysis shows nslookup.exe being abused to query an external domain (haz4rdw4re.io) confirming that the attacker is levergaing the utility as a Living-off-the-Land Binary (LoBin) to tunnel data out via DNS requests.

<img width="1462" height="709" alt="Screenshot 2026-06-24 at 20 27 32" src="https://github.com/user-attachments/assets/b8ddaa22-0b3b-4546-ab68-63e51d71b8b9" />
<img width="1462" height="709" alt="Screenshot 2026-06-25 at 09 04 16" src="https://github.com/user-attachments/assets/3f24c63f-39df-496e-a715-e9e27aefc265" />
<img width="1462" height="709" alt="Screenshot 2026-06-25 at 09 04 54" src="https://github.com/user-attachments/assets/fb345fe5-30b0-415f-804e-1381a6d7527e" />
<img width="1462" height="709" alt="Screenshot 2026-06-25 at 09 05 02" src="https://github.com/user-attachments/assets/3b2b5bb4-b5b1-4e13-a87f-32fb51bb7266" />
<img width="1462" height="709" alt="Screenshot 2026-06-25 at 09 05 11" src="https://github.com/user-attachments/assets/64f1d2c9-e08a-4f54-808d-3202bac2ff4a" />
<img width="1462" height="709" alt="Screenshot 2026-06-25 at 09 05 44" src="https://github.com/user-attachments/assets/b4a6abd2-790a-46b6-85f7-fee62ca25540" />
<img width="1462" height="709" alt="Screenshot 2026-06-25 at 09 06 57" src="https://github.com/user-attachments/assets/8762b169-e3b8-487e-a855-65dfef80f8d5" />

### Threat Intelligence: Public OSINT resources and technical documentation confirm that the domain infrastructure (h4rdw4re.io) is associated with active command and control (C2) frameworks designed explicity for bypassing firewalls through DNS-Based exfiltration.

<img width="743" height="471" alt="Screenshot 2026-06-25 at 11 48 06" src="https://github.com/user-attachments/assets/10450fe6-575f-447f-aafe-8ec797aa1b6d" />
<img width="743" height="433" alt="Screenshot 2026-06-25 at 11 48 18" src="https://github.com/user-attachments/assets/062221ec-4fd8-420d-905d-372e7220564e" />
<img width="743" height="433" alt="Screenshot 2026-06-25 at 11 48 24" src="https://github.com/user-attachments/assets/a8259c70-bbdc-478a-91f8-b7fc81523682" />

### Disposition and Resolution:Classified as a True Positive. The incident is immediately escalated to senior leadership with recommended containment procedures, including isolating host win-3450 from the network, serving the active C2 connection, and implementing tenant-wide firewall blocks on the malicious domain infrastructure.

### Result
<img width="1445" height="433" alt="Screenshot 2026-06-25 at 11 48 43" src="https://github.com/user-attachments/assets/77882312-4997-4959-b9be-f400f5d1e161" />












