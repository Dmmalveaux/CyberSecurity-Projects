SOC Home Lab
Overview

This project documents the design, implementation, and operation of a Security Operations Center (SOC) home lab built to simulate a real-world enterprise environment. The lab provides a safe environment for practicing security monitoring, threat detection, incident response, log analysis, and attack simulation.

The objective of this project is to develop practical Blue Team skills by generating realistic attack scenarios, collecting security telemetry, creating detection rules, and investigating security events using industry-standard tools.

Objectives
Build a functional SOC environment from scratch
Simulate common cyber attacks in a controlled lab
Collect and centralize security logs
Detect malicious activity using SIEM technologies
Practice incident investigation and response
Develop threat hunting and detection engineering skills
Map detections to the MITRE ATT&CK framework
Lab Environment

The lab consists of multiple virtual machines representing an enterprise network, including Windows and Linux systems. Security monitoring and logging solutions are configured to collect endpoint, authentication, and network events for analysis.

Example components include:

Windows Workstation
Windows Server (Active Directory)
Linux Server
Attacker Machine (Kali Linux)
SIEM Platform
Sysmon
Windows Event Logs
Network Monitoring Tools
Skills Demonstrated
Security Operations (SOC)
Threat Detection
Threat Hunting
Incident Response
Log Analysis
Windows Event Investigation
Active Directory Security
Network Traffic Analysis
Detection Engineering
MITRE ATT&CK Mapping
SIEM Administration
Python Security Automation
Project Structure
SOC-Home-Lab/
│
├── architecture/
├── attack-scenarios/
├── detections/
├── dashboards/
├── incident-response/
├── logs/
├── playbooks/
├── scripts/
├── screenshots/
├── threat-hunting/
├── writeups/
└── README.md
Planned Scenarios
Brute Force Login Detection
PowerShell Abuse
Suspicious Process Execution
Credential Dumping Simulation
Lateral Movement
Persistence Techniques
Malware Simulation (Safe Samples)
DNS Tunneling Detection
Privilege Escalation
Data Exfiltration Simulation
Learning Goals

This project is intended to strengthen practical knowledge of enterprise security operations while building experience with detection engineering, incident response workflows, and threat hunting methodologies. Each scenario includes documentation describing the attack, evidence collected, detection logic, investigation process, and remediation steps.

Future Improvements
Integrate Microsoft Sentinel
Add Splunk dashboards
Expand Sigma and YARA rule coverage
Automate log collection with Python
Simulate ransomware attacks in a controlled environment
Build custom detection rules
Add cloud security monitoring
Create additional incident response playbooks
Disclaimer

This lab is intended solely for educational and defensive cybersecurity purposes. All attack simulations are performed in an isolated virtual environment that I own and control. No testing is conducted against systems without explicit authorization.
