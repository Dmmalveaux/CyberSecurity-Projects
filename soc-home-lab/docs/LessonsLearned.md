# Lessons Learned

# SOC Home Lab Project

## Overview

Building this SOC Home Lab provided practical experience with designing, deploying, and operating a small-scale Security Operations Center (SOC). Throughout the project, I encountered challenges similar to those faced in enterprise environments, including infrastructure deployment, log collection, SIEM configuration, detection engineering, and incident response.

Each phase expanded my understanding of cybersecurity operations and reinforced the importance of documentation, troubleshooting, and continuous improvement.

---

# Phase 1 – Infrastructure Deployment

## What I Learned

The first phase focused on designing and building the lab environment from the ground up. This provided valuable experience with virtualization, Windows Server administration, Active Directory, networking, and Linux system management.

### Skills Gained

* Deploying virtual machines using VMware
* Installing Windows Server 2022
* Configuring Active Directory Domain Services
* Managing DNS services
* Joining Windows clients to an Active Directory domain
* Configuring static IP addresses
* Basic Linux administration with Debian
* Understanding enterprise network architecture

### Challenges Encountered

* Domain join failures caused by DNS configuration issues
* Networking problems between virtual machines
* Incorrect IP addressing and subnet configuration
* Time synchronization issues affecting Active Directory authentication
* VMware networking configuration

### How I Solved Them

* Verified DNS settings on all domain-joined systems
* Corrected virtual network adapter configurations
* Reviewed Windows Event Viewer logs for authentication errors
* Tested network connectivity using ping and nslookup
* Validated Active Directory and DNS functionality before adding clients

### Key Takeaway

A properly configured infrastructure is essential for security monitoring. Small configuration errors in networking or Active Directory can prevent an entire security monitoring environment from functioning correctly.

---

# Phase 2 – SIEM Deployment and Log Collection

## What I Learned

The second phase focused on deploying Splunk Enterprise, configuring Universal Forwarders, and centralizing logs from multiple systems. This phase demonstrated how enterprise environments collect and analyze endpoint telemetry.

### Skills Gained

* Installing Splunk Enterprise
* Configuring Splunk Universal Forwarders
* Creating data inputs
* Collecting Windows Event Logs
* Configuring Sysmon
* Understanding log forwarding architecture
* Searching events using SPL
* Troubleshooting log ingestion issues

### Challenges Encountered

* Universal Forwarders not communicating with the Splunk server
* Incorrect outputs.conf and inputs.conf configuration
* Missing Sysmon logs
* Sysmon configuration file errors
* Confusion between indexes and log sources
* Event searches returning no results

### How I Solved Them

* Verified network connectivity between forwarders and Splunk
* Reviewed Splunk internal logs for ingestion errors
* Corrected Universal Forwarder configuration files
* Installed and verified Sysmon correctly
* Used source-based searches to validate incoming data
* Confirmed Windows Event Log collection before creating detections

### Key Takeaway

Collecting logs is only the first step. Understanding how data is ingested, indexed, and searched is critical for effective security monitoring.

---

# Phase 3 – Detection Engineering, Threat Hunting, and Incident Response

## What I Learned

The final phase shifted from building infrastructure to actively monitoring, detecting, and investigating suspicious activity. This phase closely reflected the daily responsibilities of a SOC Analyst.

### Skills Gained

* Writing custom SPL queries
* Building Splunk dashboards
* Creating detection rules
* Threat hunting using endpoint telemetry
* Investigating Windows security events
* Mapping detections to the MITRE ATT&CK Framework
* Documenting security incidents
* Developing reusable investigation procedures

### Challenges Encountered

* Searches returning unexpected results due to field differences
* Understanding Sysmon event IDs and Windows Event Codes
* Reducing false positives
* Correlating events across multiple hosts
* Organizing documentation for repeatable investigations

### How I Solved Them

* Verified field names before creating SPL queries
* Used targeted searches to validate event data
* Tested detections using simulated attack scenarios
* Improved detection logic through iterative tuning
* Organized documentation into structured folders for future reference

### Key Takeaway

Effective detection engineering requires continuous testing and refinement. Successful monitoring depends on understanding both the data source and the attacker behaviors being detected.

---

# Overall Project Reflection

This project demonstrated that building a functional SOC involves much more than installing software. Every component—from infrastructure and networking to log collection and incident response—must work together to provide meaningful security visibility.

Working through real configuration issues strengthened my troubleshooting skills and improved my understanding of how enterprise security technologies interact. Rather than relying solely on theoretical knowledge, I gained practical experience by identifying problems, researching solutions, testing changes, and validating results.

The project also reinforced the importance of thorough documentation. Maintaining detailed notes, detection logic, investigation procedures, and incident reports makes security operations more consistent, repeatable, and easier to improve over time.

---

# Technical Skills Strengthened

* Splunk Enterprise
* Splunk Search Processing Language (SPL)
* Windows Event Logging
* Sysmon
* Active Directory
* Windows Server Administration
* Linux Administration
* VMware Virtualization
* DNS and Networking
* Detection Engineering
* Threat Hunting
* Incident Response
* Digital Forensics Fundamentals
* Log Analysis
* MITRE ATT&CK Framework
* Security Documentation

---

# Future Improvements

Future phases of this project will focus on expanding the lab to simulate more advanced enterprise security operations.

Planned improvements include:

* Implementing Splunk Enterprise Security (ES)
* Developing additional correlation searches
* Building Risk-Based Alerting (RBA) detections
* Integrating Sigma detection rules
* Simulating ransomware attack scenarios
* Deploying endpoint detection and response (EDR) tools
* Automating investigations with SOAR workflows
* Integrating threat intelligence feeds
* Expanding Active Directory attack simulations
* Developing purple team exercises
* Creating executive and operational SOC dashboards
* Implementing cloud security monitoring for Microsoft Azure and AWS

---

# Final Thoughts

Completing this SOC Home Lab significantly improved my understanding of modern security operations and defensive cybersecurity practices. The project provided practical experience with enterprise technologies, reinforced structured troubleshooting methodologies, and strengthened my ability to analyze security events, investigate incidents, and communicate technical findings.

This repository represents my continued commitment to developing real-world cybersecurity skills through hands-on learning, continuous improvement, and practical application.
