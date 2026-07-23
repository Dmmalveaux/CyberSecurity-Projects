## 🛡️ Phase 2 – Detection, Alerting, Attack Simulation, and Validation

### 📌 Overview

Phase 2 focused on transforming the SOC home lab from a centralized log collection environment into an active **security monitoring and detection platform**. After successfully deploying Splunk Enterprise and configuring Splunk Universal Forwarders during Phase 1, this phase focused on creating detection logic, generating security events, validating alerts, and performing SOC-style investigations.

The objective was to simulate real-world security operations by conducting controlled attacks from Kali Linux, analyzing Windows security events, creating Splunk detections, and documenting findings through incident response reports.

---

## 🎯 Key Objectives

* Develop Splunk SPL detection queries using Windows Security Event Logs
* Configure alerts for suspicious authentication activity
* Simulate real-world attacks against lab systems
* Validate end-to-end log collection and detection workflows
* Analyze security events from Windows endpoints and Active Directory
* Document incidents using a SOC analyst reporting format

---

# 🔍 Detection Implementation

Custom Splunk searches were created to monitor and analyze important Windows security events collected through Splunk Universal Forwarders.

Detection logic included:

### 🔐 Authentication Monitoring

**Failed Login Attempts (Event ID 4625)**
Used to detect:

* Brute-force attempts
* Password guessing activity
* Suspicious authentication failures

Example detection:

```spl
index=wineventlog EventCode=4625
| stats count by Account_Name, Source_Network_Address
| sort -count
```

---

**Successful Logins (Event ID 4624)**
Used to monitor:

* User authentication activity
* Potential unauthorized access

---

### ⚙️ Process Monitoring

**Process Creation (Event ID 4688)**

Used to track:

* New process execution
* Suspicious command execution
* Endpoint activity

---

### 🔒 Account Security Monitoring

**Account Lockouts (Event ID 4740)**

Used to identify:

* Repeated failed authentication attempts
* Potential credential attacks

---

# 🚨 Alerting Configuration

Splunk detection searches were converted into scheduled alerts to provide automated threat monitoring.

Alerts were configured with:

* Event frequency thresholds
* Scheduled search intervals
* Trigger conditions based on suspicious behavior
* Severity classification

Examples:

* Multiple failed logins from the same IP address
* Excessive authentication failures against an account
* Suspicious activity originating from Kali Linux

These alerts simulate a real SOC workflow where analysts monitor, investigate, and respond to security events.

---

# 🧪 Attack Simulation & Validation

Controlled attacks were performed using Kali Linux to validate the effectiveness of Splunk detections.

Each scenario followed the SOC detection lifecycle:

```
Attack Simulation
        ↓
Security Event Generation
        ↓
Splunk Universal Forwarder Collection
        ↓
Splunk Indexing
        ↓
Detection Query Execution
        ↓
Alert Generation
        ↓
Incident Investigation
```

---

# 🔴 Attack Scenario 1: RDP Brute Force Attack

## Description

A brute-force attack was simulated from Kali Linux against Windows 10 and Windows 11 virtual machines using Remote Desktop Protocol (RDP).

## Tools Used

* Kali Linux
* Hydra
* Splunk Enterprise

## Detection

Monitored Windows Security Events:

* Event ID 4625 – Failed Logon Attempts
* Event ID 4624 – Successful Logons

Investigation focused on:

* Source IP address
* Target username
* Number of failed attempts
* Authentication patterns

---

# 🔵 Attack Scenario 2: Network Reconnaissance (Nmap Scan)

## Description

Network scanning was performed from Kali Linux to identify available services and exposed ports within the SOC lab environment.

## Tools Used

* Kali Linux
* Nmap
* Splunk Enterprise

## Detection Goals

The objective was to identify:

* Suspicious network discovery activity
* Repeated connection attempts
* Reconnaissance behavior

---

# 🟣 Attack Scenario 3: LDAP Enumeration Against Active Directory

## Description

LDAP enumeration was performed against the Active Directory domain:

```
project.local
```

The activity simulated an attacker attempting to gather directory information including:

* Domain structure
* User accounts
* Groups
* LDAP information

## Tools Used

* Kali Linux
* Nmap
* ldapsearch
* Splunk Enterprise

## Findings

Anonymous LDAP enumeration was prevented by Active Directory security controls. A successful LDAP bind was required before directory queries could be performed.

The investigation focused on:

* Authentication activity
* LDAP-related behavior
* Windows Security Events

---

# 📂 Incident Documentation

Each attack scenario was documented using a SOC incident response format containing:

* Incident summary
* Attack methodology
* Tools used
* Detection methods
* Splunk queries
* Investigation findings
* Response recommendations
* Lessons learned

Completed incident reports include:

* RDP Brute Force Attack
* LDAP Enumeration Attempt
* Network Reconnaissance Scan

---

# ✅ Results

Phase 2 successfully demonstrated:

* Real-time security monitoring using Splunk Enterprise
* Successful log collection from Windows systems
* Detection of simulated attacks
* Alert validation and tuning
* Investigation of authentication events
* Documentation of SOC incidents

The lab successfully moved from passive log collection into an active detection and response environment.

---

# 🧠 Skills Demonstrated

* Splunk Enterprise administration
* Splunk SPL query development
* Security alert creation and tuning
* Windows Event Log analysis
* Active Directory security monitoring
* LDAP enumeration analysis
* Network reconnaissance detection
* Kali Linux attack simulation
* Incident response documentation

---

# 📈 Summary

Phase 2 established the core operational capabilities of the SOC home lab by introducing detection engineering, alerting, attack simulation, and investigation workflows.

This phase demonstrates practical SOC Analyst skills by showing the complete security monitoring lifecycle:

```
Threat Simulation
        ↓
Detection Engineering
        ↓
SIEM Monitoring
        ↓
Alert Investigation
        ↓
Incident Documentation
```

The completed work provides hands-on experience with the same processes used by security analysts to identify, investigate, and respond to cybersecurity threats.

