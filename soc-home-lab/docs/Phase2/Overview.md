## 🛡️ Phase 2 – Detection, Alerting, and Validation

### 📌 Overview

Phase 2 focuses on transforming the SOC home lab from a basic log collection environment into an active **detection and monitoring platform**. After successfully configuring log ingestion in Phase 1, this phase emphasizes identifying suspicious activity, generating alerts, and validating the effectiveness of the logging pipeline.

The objective is to simulate real-world SOC operations by creating detection logic, triggering alerts, and confirming that security events are properly captured and analyzed.

---

### 🎯 Key Objectives

* Develop detection queries using Windows Event Logs
* Create and configure alerts for suspicious activity
* Simulate attacks to generate real security events
* Validate end-to-end log flow from endpoint to SIEM
* Analyze and interpret security data

---

### 🔍 Detection Implementation

Custom Splunk queries were created to monitor critical Windows security events, including:

* **Failed login attempts (Event ID 4625)** – Brute force detection
* **Successful logins (Event ID 4624)** – Authentication tracking
* **Process creation (Event ID 4688)** – Execution monitoring
* **Account lockouts (Event ID 4740)** – Suspicious access attempts

These queries were enhanced using statistical functions to identify patterns such as repeated login failures or unusual activity from specific users or IP addresses.

---

### 🚨 Alerting Configuration

Detection queries were converted into scheduled alerts within Splunk to automate monitoring. Alerts were configured with:

* Defined thresholds (e.g., multiple failed logins within a short time frame)
* Scheduled execution intervals
* Trigger conditions based on event frequency

This enables near real-time identification of potential threats, mimicking a real SOC alerting workflow.

---

### 🧪 Attack Simulation & Validation

To validate detection capabilities, controlled attack simulations were performed, including:

* Multiple failed login attempts to simulate brute force activity
* Execution of system processes to generate event logs
* Basic network scanning to produce detectable traffic patterns

Each simulation followed the full pipeline:
**Attack → Log Generation → Forwarding → Indexing → Detection → Alert Trigger**

---

### ✅ Results

* Successfully detected and analyzed simulated attack activity
* Verified alerts triggered under defined conditions
* Confirmed reliable log ingestion and processing
* Demonstrated practical SOC analyst workflows

---

### 🧠 Skills Demonstrated

* SIEM query development (Splunk SPL)
* Security event analysis (Windows Event Logs)
* Alert creation and tuning
* Threat detection fundamentals
* Troubleshooting and validation of log pipelines

---

### 📈 Summary

Phase 2 establishes the core functionality of a SOC by enabling active monitoring and threat detection. This phase demonstrates the ability to move beyond system setup and into real-world security operations, showcasing hands-on experience relevant to SOC Analyst roles.
