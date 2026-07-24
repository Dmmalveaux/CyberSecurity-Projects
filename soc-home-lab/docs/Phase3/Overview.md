# Phase 3 – Detection Engineering, Threat Hunting & Incident Response

## Overview

Phase 3 focuses on the operational side of a Security Operations Center (SOC). Building on the infrastructure and log collection completed in Phases 1 and 2, this phase emphasizes detecting malicious activity, investigating security events, and documenting incidents using industry-standard methodologies.

The objective is to simulate the daily responsibilities of a Tier 1/Tier 2 SOC Analyst by developing detection rules, performing threat hunting, creating dashboards, and responding to simulated attacks within a controlled lab environment.

---

# Objectives

* Develop custom Splunk detection rules using Search Processing Language (SPL).
* Monitor Windows Security and Sysmon logs for suspicious activity.
* Simulate common cyber attacks against a Windows Active Directory environment.
* Perform threat hunting using log analysis and endpoint telemetry.
* Investigate alerts and document findings through formal incident reports.
* Map detections to the MITRE ATT&CK Framework.
* Build reusable documentation and playbooks for future investigations.

---

# Lab Environment

## Infrastructure

* Windows Server 2022 Domain Controller
* Active Directory Domain Services (AD DS)
* DNS Server
* Windows 10 Client
* Windows 11 Client
* Debian Linux Server
* Kali Linux Attack Machine
* Splunk Enterprise SIEM
* Splunk Universal Forwarders
* Sysmon Endpoint Monitoring

---

# Technologies Used

## SIEM & Monitoring

* Splunk Enterprise
* Splunk Search Processing Language (SPL)
* Splunk Universal Forwarder
* Windows Event Logs
* Sysmon

## Operating Systems

* Windows Server 2022
* Windows 10
* Windows 11
* Debian Linux
* Kali Linux

## Security Tools

* Wireshark
* Nmap
* Metasploit Framework
* Event Viewer
* PowerShell

---

# Phase 3 Components

## Detection Rules

Custom detection logic was developed to identify suspicious activity using Windows Security and Sysmon telemetry. Each rule includes:

* Detection objective
* SPL query
* Alert logic
* Investigation guidance
* False positive considerations
* MITRE ATT&CK mapping

Example detections include:

* Brute-force authentication attempts
* New local administrator creation
* PowerShell execution
* Suspicious process creation
* Network reconnaissance
* Service installation
* Account lockouts
* Remote Desktop logins

---

## Threat Hunting

Threat hunts were conducted using Splunk to proactively identify indicators of compromise (IOCs) and abnormal behavior.

Hunting scenarios include:

* Failed authentication analysis
* PowerShell activity
* Process creation monitoring
* Network connection analysis
* Privilege escalation
* Persistence mechanisms
* Lateral movement

---

## Incident Response

Each simulated attack was documented using a structured incident response workflow.

Every incident report contains:

* Executive Summary
* Timeline of Events
* Detection Details
* Indicators of Compromise (IOCs)
* Evidence Collected
* MITRE ATT&CK Mapping
* Containment Actions
* Recovery Actions
* Lessons Learned

---

## Dashboards

Custom Splunk dashboards were created to provide visibility into the environment.

Dashboard categories include:

* SOC Overview
* Authentication Monitoring
* Endpoint Monitoring
* Threat Hunting
* Incident Response
* Detection Metrics

---

## SPL Query Library

A library of reusable SPL queries was created for:

* Windows Authentication
* Sysmon Events
* PowerShell Activity
* Active Directory Monitoring
* Threat Hunting
* Detection Engineering

Each query includes a description, expected output, and investigation guidance.

---

## MITRE ATT&CK Mapping

Detection rules and threat hunts are mapped to the MITRE ATT&CK Framework to demonstrate adversary behaviors and defensive coverage.

Examples include:

| Tactic               | Technique                               |
| -------------------- | --------------------------------------- |
| Initial Access       | T1078 – Valid Accounts                  |
| Execution            | T1059.001 – PowerShell                  |
| Persistence          | T1543 – Create or Modify System Process |
| Privilege Escalation | T1134 – Access Token Manipulation       |
| Defense Evasion      | T1562 – Impair Defenses                 |
| Credential Access    | T1110 – Brute Force                     |
| Discovery            | T1046 – Network Service Discovery       |
| Lateral Movement     | T1021.001 – Remote Desktop Protocol     |

---

# Skills Demonstrated

This phase demonstrates practical experience with:

* Security Operations Center (SOC) workflows
* Detection Engineering
* Threat Hunting
* Log Analysis
* Security Monitoring
* Incident Response
* Active Directory Security
* Windows Event Analysis
* Sysmon Monitoring
* SIEM Administration
* MITRE ATT&CK Framework
* Security Documentation
* Technical Reporting

---

# Learning Outcomes

Through Phase 3, I gained hands-on experience building and operating a SIEM-driven security monitoring environment. By creating custom detections, investigating simulated attacks, and documenting incidents, I strengthened my understanding of endpoint visibility, authentication monitoring, and incident response workflows.

This phase provided practical experience with defensive security operations and reinforced the importance of continuous monitoring, detection tuning, and structured investigation processes within an enterprise environment.

---

# Future Improvements

Planned enhancements for future phases include:

* Sysmon configuration tuning
* Custom correlation searches
* Risk-Based Alerting (RBA)
* Automated response workflows
* Security Orchestration, Automation, and Response (SOAR)
* Sigma rule integration
* YARA rule testing
* Endpoint Detection and Response (EDR) simulations
* Malware analysis
* Threat intelligence integration
* Additional attack simulations mapped to MITRE ATT&CK


## Conclusion

Phase 3 transforms the lab from a log collection environment into a functioning Security Operations Center simulation. By combining SIEM monitoring, endpoint telemetry, threat hunting, detection engineering, and incident response, this phase demonstrates practical blue team skills that align with the responsibilities of an entry-level SOC Analyst or Cybersecurity Analyst.
