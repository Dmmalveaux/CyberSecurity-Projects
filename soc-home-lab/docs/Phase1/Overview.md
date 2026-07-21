# 🛡️ SOC Home Lab – Log Monitoring & Threat Detection

## 📌 Overview

This project demonstrates the design, deployment, and troubleshooting of a **Security Operations Center (SOC) home lab**. The lab simulates real-world log collection, monitoring, and detection workflows using industry-standard tools.

The goal was to build a functional environment capable of:

* Collecting endpoint logs
* Forwarding logs securely
* Indexing and searching logs
* Troubleshooting ingestion issues

---

## 🧱 Lab Architecture

* **SIEM Server:** Splunk Enterprise (Main log collector & analyzer)
* **Log Forwarder:** Splunk Universal Forwarder (Windows endpoint)
* **Endpoint:** Windows 10/11 VM
* **Hypervisor:** VMware Workstation Pro
* **Network Type:** NAT / Host-Only (depending on test scenario)

---

## ⚙️ Technologies Used

* Splunk Enterprise
* Splunk Universal Forwarder
* Windows 10/11
* VMware Workstation
* Command Prompt (CLI)
* Basic Networking (IP, ports, connectivity testing)

---

## 🚀 Deployment Steps

### 1. Install Splunk Enterprise (SIEM)

* Installed on primary VM
* Configured web interface (default port: 8000)
* Enabled receiving on port **9997**

### 2. Install Universal Forwarder (Endpoint)

* Installed on Windows machine
* Configured to forward logs to Splunk server

### 3. Configure Forwarding

**outputs.conf**

```
[tcpout]
defaultGroup = default-autolb-group

[tcpout:default-autolb-group]
server = <Splunk_Server_IP>:9997
```

**inputs.conf**

```
[WinEventLog://Security]
index = main

[WinEventLog://System]
index = main
```

---

## 🔍 Verification

* Confirmed forwarder connection:

```
splunk list forward-server
```

* Verified logs in Splunk:

  * Searched:

    ```
    index=main
    ```
  * Observed Windows event logs successfully ingested

---

## 🛠️ Troubleshooting Process

### ❌ Issue: Forwarder Not Sending Logs

**Symptoms:**

* No logs appearing in Splunk
* Forwarder connected but no data

---

### 🔎 Step 1: Verify Service Status

```
net start splunkforwarder
```

✔ Confirmed service was running

---

### 🔎 Step 2: Restart Forwarder

```
cd "C:\Program Files\SplunkUniversalForwarder\bin"
splunk restart
```

✔ Ensured configs were applied

---

### 🔎 Step 3: Validate Configuration Files

* Checked:

  * `inputs.conf`
  * `outputs.conf`
* Verified correct IP and port

---

### 🔎 Step 4: Check Network Connectivity

* Pinged Splunk server
* Verified port **9997** reachable

---

### 🔎 Step 5: Confirm Receiving Port on Splunk

* Enabled receiving on **9997**
* Verified via Splunk UI

---

### ✅ Resolution

After restarting the forwarder and correcting configuration paths, logs began successfully forwarding and indexing.

---

## 📊 Key Skills Demonstrated

* SIEM deployment (Splunk)
* Log forwarding and ingestion
* Windows log monitoring
* Troubleshooting log pipeline issues
* CLI-based system management
* Network connectivity validation

---

## 🧠 Lessons Learned

* Restarting services is critical after config changes
* Misconfigured file paths can silently break ingestion
* Always verify both **forwarder side** and **SIEM side**
* Layered troubleshooting (service → config → network) is most effective

---

## 📈 Future Improvements

* Add alerting (failed login detection)
* Integrate with Wazuh or Elastic Stack
* Simulate attacks (Brute force, Nmap scans)
* Create dashboards for visualization

---

## 🔗 Author

**Davionte Malveaux**
Cybersecurity & IT Professional

---

## ⭐ Summary

This lab demonstrates hands-on experience with building and troubleshooting a SOC environment, focusing on real-world log ingestion challenges and solutions—skills directly applicable to SOC Analyst and IT roles.
