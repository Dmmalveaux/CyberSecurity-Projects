# Active Directory Attack & Defense Lab

## Overview

The Active Directory Attack & Defense Lab is a comprehensive cybersecurity project designed to simulate a modern enterprise Windows environment. This lab demonstrates both offensive and defensive security operations by deploying an Active Directory domain, performing common attack techniques against the environment, and detecting malicious activity using Splunk and Sysmon.

The project is divided into three phases that cover infrastructure deployment, attack simulation, and blue team detection and incident response. Each phase includes detailed documentation, screenshots, detection logic, MITRE ATT&CK mappings, and lessons learned.

---

## Objectives

- Deploy a realistic enterprise Active Directory environment
- Configure Windows Server and domain-joined Windows clients
- Centralize Windows event logs using Splunk
- Deploy Sysmon for enhanced endpoint visibility
- Simulate real-world Active Directory attacks
- Detect malicious activity using SIEM detection rules
- Perform threat hunting using Splunk
- Develop incident response documentation
- Map attacks and detections to the MITRE ATT&CK Framework
- Build a professional cybersecurity portfolio project

---

## Lab Architecture

### Infrastructure

- VMware Workstation
- Windows Server 2022
- Windows 11 Enterprise Clients
- Kali Linux
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Active Directory Domain Services
- DNS Server

---

## Technologies Used

### Operating Systems

- Windows Server 2022
- Windows 11
- Kali Linux

### Security Tools

- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- BloodHound
- Impacket
- CrackMapExec / NetExec
- Kerbrute
- Mimikatz
- Atomic Red Team
- Wireshark

### Windows Services

- Active Directory Domain Services
- DNS
- Group Policy
- Windows Event Logging
- Windows Defender

---

# Project Structure

```
Active-Directory-Attack-Defense-Lab
│
├── Phase1-Infrastructure
├── Phase2-Attacks
├── Phase3-Detection-and-Response
│
├── README.md
```

---

# Phase 1 – Enterprise Infrastructure

During Phase 1, a secure enterprise Windows environment is designed and deployed.

### Activities

- Design lab architecture
- Configure VMware networking
- Deploy virtual machines
- Install Active Directory Domain Services
- Configure DNS
- Create Organizational Units
- Create users and security groups
- Configure Group Policy Objects
- Join Windows clients to the domain
- Install Sysmon
- Deploy Splunk Universal Forwarders
- Configure Splunk log ingestion
- Establish a baseline of normal activity

### Deliverables

- Architecture diagrams
- Network diagrams
- Infrastructure documentation
- Group Policy configuration
- Screenshots
- Baseline dashboards

---

# Phase 2 – Attack Simulation

Phase 2 focuses on simulating common Active Directory attacks within the isolated lab environment.

### Attack Scenarios

- Network Reconnaissance
- Password Spraying
- Kerberoasting
- AS-REP Roasting
- BloodHound Enumeration
- Lateral Movement
- Credential Dumping
- PowerShell Abuse
- Living-off-the-Land Binaries (LOLBins)
- Persistence Techniques
- Scheduled Tasks
- Service Creation
- Registry Persistence
- Simulated Data Exfiltration

### Deliverables

- Attack walkthroughs
- MITRE ATT&CK mappings
- Screenshots
- Timeline documentation
- Attack summaries

---

# Phase 3 – Detection & Defense

The final phase focuses on blue team operations by detecting, investigating, and responding to the attacks performed in Phase 2.

### Detection Engineering

- Splunk SPL Queries
- Detection Rules
- Sigma Rules
- Alert Development
- Detection Tuning

### Threat Hunting

- Authentication Hunting
- PowerShell Hunting
- Persistence Hunting
- Lateral Movement Hunting
- Credential Theft Hunting

### Incident Response

Each simulated attack includes:

- Executive Summary
- Timeline
- Indicators of Compromise
- Evidence Collection
- MITRE ATT&CK Mapping
- Containment
- Eradication
- Recovery
- Lessons Learned

---

## Skills Demonstrated

### Blue Team

- Security Monitoring
- SIEM Administration
- Detection Engineering
- Threat Hunting
- Incident Response
- Log Analysis
- Windows Security
- Endpoint Monitoring

### Windows Administration

- Active Directory
- DNS
- Group Policy
- User Management
- Domain Administration
- Windows Event Logging

### Offensive Security

- Active Directory Enumeration
- Credential Attacks
- Privilege Escalation
- Lateral Movement
- Persistence
- Adversary Simulation

---

## MITRE ATT&CK

This project maps attack techniques and defensive detections to the MITRE ATT&CK Enterprise Framework, demonstrating detection coverage and defensive capabilities against common adversary tactics.

---

## Repository Contents

```
Phase1-Infrastructure/
├── Architecture
├── Network-Diagrams
├── Server-Configuration
├── Group-Policy
├── Users-and-Groups
├── Sysmon
├── Splunk
├── Screenshots

Phase2-Attacks/
├── Reconnaissance
├── Password-Attacks
├── Kerberoasting
├── ASREP-Roasting
├── BloodHound
├── Lateral-Movement
├── Credential-Dumping
├── PowerShell
├── Persistence
├── LOLBins
├── MITRE-Mapping
├── Screenshots

Phase3-Detection-and-Response/
├── Detection-Rules
├── SPL-Queries
├── Sigma-Rules
├── Dashboards
├── Threat-Hunting
├── Incident-Reports
├── MITRE-Matrix
├── Screenshots
```

---

## Key Learning Outcomes

Through this project I developed practical experience in:

- Building and administering an enterprise Active Directory environment
- Deploying centralized log collection using Splunk
- Configuring endpoint telemetry with Sysmon
- Simulating common Active Directory attack techniques
- Developing SIEM detections and threat hunting queries
- Performing incident response investigations
- Mapping attacks to the MITRE ATT&CK Framework
- Documenting findings using professional cybersecurity reporting standards

---

## Disclaimer

This project was created for educational purposes within an isolated virtual lab environment. All attacks were performed against systems owned and controlled by the author. No unauthorized testing was conducted against production or third-party systems.

---

## Author

**Davionte Malveaux**

Cybersecurity | Blue Team | SOC Analyst | Detection Engineering | Threat Hunting | Incident Response

*GitHub Portfolio:* **(Add your GitHub URL here)**

*LinkedIn:* **(Add your LinkedIn URL here)**
