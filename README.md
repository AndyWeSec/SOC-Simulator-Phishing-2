# SOC-Simulator-Phishing-2
A seconadry end-to-end incident response lab simulating an enterprise phishing attack vector. Documents email header triage, malicious payload hashing, and threat intelligence lookups using VirusTotal, alongside blue-team detection engineering, log ingestion, and alert generation within Elastic SIEM.

### Tools Used
Training Platform: TryHackMe SOC Simulator
SIEM Platform: SPLUNK
Threat Intelligence: VirusTotal

### SOC Phishing Simulator & Incident Response Lab
* Attack Simulation: Simulated an enterprise phishing attack vector within an isolated sandbox environment to generate realistic endpoint and network telemetry.
* Threat Intelligence: Analysed raw email headers and extracted malicious payload hashes, leveraging VirusTotal to validate indicators of compromise (IoCs).
* SIEM Detection Engineering: Developed custom queries and alert rules within Elastic SIEM to detect post-exploitation activity, suspicious process spawning, and unauthorized network connections.
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

## Alert 1 True Posetive following SPLUNK (SEIM) and VirusTotal investigations

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 39 15" src="https://github.com/user-attachments/assets/7d990be6-d314-420e-acb3-6d01188d2b33" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 41 05" src="https://github.com/user-attachments/assets/0a469a23-0ad9-4ffc-bb6d-5b35cfb93be2" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 41 42" src="https://github.com/user-attachments/assets/1d9eb4ad-a6eb-4b95-bddd-58deaa22f85c" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 42 05" src="https://github.com/user-attachments/assets/ce2281d7-f8f9-400a-b780-49655e0127db" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 42 58" src="https://github.com/user-attachments/assets/8ed9a5e1-e61f-463b-92cb-9ac8a9c60acd" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 43 07" src="https://github.com/user-attachments/assets/49031760-76ba-45f2-9259-945c12b7d673" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 46 08" src="https://github.com/user-attachments/assets/d0f1c5f2-fd82-427c-a09f-a4f11ba81c8f" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 51 40" src="https://github.com/user-attachments/assets/77cb8707-2c57-4960-b3a5-f8c843e30c3e" />

## Alert 2 False Posetive following investigation into process name details 

<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 55 56" src="https://github.com/user-attachments/assets/ce9f2b47-729b-4d6f-856e-cd58f1f3fd87" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 56 02" src="https://github.com/user-attachments/assets/535cbab0-25f7-4d1e-a80e-5da1345e0239" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 56 14" src="https://github.com/user-attachments/assets/466f55ba-86c5-4295-a8bd-a772ba16cb48" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 56 40" src="https://github.com/user-attachments/assets/8160bdfd-924f-437e-8d71-46f7bbcc4ac6" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 57 40" src="https://github.com/user-attachments/assets/12b9dddf-78b2-4537-b672-96f475c3a986" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 58 44" src="https://github.com/user-attachments/assets/cc8adfff-8098-45bf-b2fe-b045240971c3" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 59 12" src="https://github.com/user-attachments/assets/f889d56b-1be3-4753-af0d-b8646aa4f75c" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 19 59 56" src="https://github.com/user-attachments/assets/a82f2302-89f3-4580-91ca-4fe9b9360a21" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 01 05" src="https://github.com/user-attachments/assets/68eb68a2-9422-41a1-8c86-241b941545cd" />
<img width="1470" height="707" alt="Screenshot 2026-06-24 at 20 01 22" src="https://github.com/user-attachments/assets/8c07b035-f966-48bd-a313-9c473d2e07a4" />

## Alert 3 True Posetive after intense investogations following phishing emails and signs of exfiltration porcedures















