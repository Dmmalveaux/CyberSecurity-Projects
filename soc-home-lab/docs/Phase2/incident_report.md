# Incident Report: LDAP Enumeration Attempt Against Active Directory Domain

## Incident ID

SOC-LAB-002

## Incident Type

Active Directory Reconnaissance / LDAP Enumeration Attempt

## Severity

Medium

## Status

Resolved / No Compromise Detected

## Date

07/22/2026

## Analyst

Davionte Malveaux

---

# 1. Executive Summary

A simulated LDAP enumeration attack was performed against the Active Directory environment `project.local` using a Kali Linux penetration testing workstation. The objective of the activity was to demonstrate how an attacker could attempt to gather information about users, groups, and directory structure through LDAP queries.

The attack was detected and analyzed using Splunk Enterprise after authentication activity was generated against the Domain Controller. The investigation confirmed that LDAP enumeration attempts occurred, but no unauthorized access or account compromise was identified.

---

# 2. Environment

## Security Monitoring Platform

**SIEM:**

* Splunk Enterprise

**Log Collection:**

* Splunk Universal Forwarder

---

## Lab Infrastructure

| System                           | Role                           |
| -------------------------------- | ------------------------------ |
| Kali Linux                       | Attack simulation workstation  |
| Windows Server Domain Controller | Active Directory / LDAP server |
| Windows 10 VM                    | Domain endpoint                |
| Windows 11 VM                    | Domain endpoint                |

---

## Active Directory Details

**Domain:**

```
project.local
```

**Site:**

```
Default-First-Site-Name
```

**LDAP Services:**

```
TCP 389 - LDAP
TCP 636 - LDAPS
```

---

# 3. Attack Overview

The simulated attack followed a common attacker workflow:

1. Discover Active Directory services
2. Identify domain information
3. Attempt LDAP enumeration
4. Authenticate to LDAP
5. Query directory objects
6. Analyze resulting security events in Splunk

---

# 4. Attack Discovery Phase

## Tool Used

Kali Linux

Tools:

* Nmap
* ldapsearch

---

## Active Directory Discovery

Command:

```bash
nmap -p 389,636 -sV <Domain_Controller_IP>
```

Results identified:

```
Domain: project.local
Site: Default-First-Site-Name
```

This confirmed the target system was an Active Directory Domain Controller.

---

# 5. LDAP Enumeration Attempt

## Initial Anonymous LDAP Query

The attacker attempted to enumerate LDAP without authentication:

```bash
ldapsearch -x \
-H ldap://<DC-IP> \
-b "DC=project,DC=local"
```

---

## Result

The Domain Controller rejected the request:

```
In order to perform this operation a successful bind must be completed on the connection
```

This indicated that anonymous LDAP enumeration was disabled.

---

# 6. Authenticated LDAP Enumeration

A successful LDAP bind was performed using a valid domain account.

Command:

```bash
ldapsearch -x \
-H ldap://<DC-IP> \
-D "Administrator@project.local" \
-W \
-b "DC=project,DC=local"
```

---

## Enumeration Queries Performed

### User Enumeration

```bash
ldapsearch -x \
-H ldap://<DC-IP> \
-D "Administrator@project.local" \
-W \
-b "DC=project,DC=local" \
"(objectClass=user)"
```

---

### Group Enumeration

```bash
ldapsearch -x \
-H ldap://<DC-IP> \
-D "Administrator@project.local" \
-W \
-b "DC=project,DC=local" \
"(objectClass=group)"
```

---

# 7. Detection and Analysis

## Detection Platform

Splunk Enterprise

---

## Data Source

Windows Security Event Logs collected from the Domain Controller using Splunk Universal Forwarder.

---

# 8. Splunk Searches Used

## Successful Authentication Events

```spl
index=wineventlog EventCode=4624
| stats count by Account_Name, Source_Network_Address
```

Purpose:

* Identify authentication attempts
* Identify source systems
* Correlate attacker activity

---

## Failed Authentication Attempts

```spl
index=wineventlog EventCode=4625
| stats count by Account_Name, Source_Network_Address
| sort -count
```

Purpose:

* Detect password guessing attempts
* Identify suspicious authentication failures

---

## Kerberos Authentication Activity

```spl
index=wineventlog EventCode=4768
| stats count by Account_Name, Source_Network_Address
```

Purpose:

* Monitor Active Directory authentication requests
* Identify abnormal authentication patterns

---

# 9. Investigation Findings

## Findings

The investigation identified:

* LDAP enumeration attempts originating from the Kali Linux workstation
* Active Directory authentication activity against `project.local`
* No unauthorized account creation
* No privilege escalation detected
* No evidence of successful compromise

---

## Indicators of Activity

| Indicator   | Description       |
| ----------- | ----------------- |
| Source      | Kali Linux VM     |
| Target      | Domain Controller |
| Protocol    | LDAP              |
| Port        | TCP 389           |
| Domain      | project.local     |
| Attack Type | LDAP Enumeration  |

---

# 10. Response Actions

The following actions were performed:

## Security Validation

✔ Verified anonymous LDAP enumeration was disabled
✔ Reviewed authentication events in Splunk
✔ Confirmed no unauthorized access occurred

---

## Recommended Hardening

Recommended actions:

* Require LDAP signing
* Disable insecure LDAP binds
* Monitor abnormal directory queries
* Implement account lockout policies
* Monitor privileged account usage
* Restrict administrative LDAP access

---

# 11. MITRE ATT&CK Mapping

| Technique                   | ID    | Description                    |
| --------------------------- | ----- | ------------------------------ |
| Network Service Scanning    | T1046 | Discovery of LDAP services     |
| Account Discovery           | T1087 | Enumeration of domain accounts |
| Permission Groups Discovery | T1069 | Enumeration of groups          |

---

# 12. Lessons Learned

This exercise demonstrated how attackers can use LDAP queries to gather information about an Active Directory environment. By collecting Windows authentication logs with Splunk, suspicious directory activity can be investigated and correlated with the originating system.

The lab improved skills in:

* Active Directory security monitoring
* LDAP enumeration analysis
* Windows Event Log investigation
* Splunk SIEM detection engineering
* Incident response documentation

---

# 13. Evidence Collected

Screenshots and evidence included:

* Nmap domain discovery results
* LDAP enumeration commands
* LDAP authentication results
* Splunk event searches
* Windows security event logs
* Detection timeline

---

# Final Outcome

**Incident closed.**

The LDAP enumeration activity was successfully identified and analyzed. The Active Directory environment remained secure, and no compromise was detected.
