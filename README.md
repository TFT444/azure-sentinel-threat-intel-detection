# Azure Sentinel Threat Detection Lab (SOC Simulation)

## 📌 Overview

This project demonstrates a real-world Security Operations Center (SOC) workflow using Microsoft Sentinel.

The goal was to simulate detection and investigation of suspicious Azure Storage access using Threat Intelligence indicators and custom KQL queries.

---

## 🎯 Objectives

* Ingest threat intelligence indicators (malicious IPs)
* Detect suspicious Azure Storage activity
* Create custom analytics rules
* Generate alerts and incidents
* Perform basic incident investigation
* Automate response using playbooks

---

## 🛠️ Technologies Used

* Microsoft Sentinel
* Azure Log Analytics
* KQL (Kusto Query Language)
* Azure Logic Apps (Playbooks)
* Threat Intelligence (Indicators)

---

## 🔍 Detection Logic

### KQL Query

```kql
AzureActivity
| where OperationNameValue contains "MICROSOFT.STORAGE"
| where CallerIpAddress == "2a09:bac5:3804:2696::3d8:3c"
```

### What it does:

* Monitors Azure Storage operations
* Matches activity from a known malicious IP
* Triggers alert if activity is detected

---

## 🧠 MITRE ATT&CK Mapping

* T1078 – Valid Accounts
* Tactic: Initial Access

---

## ⚙️ Analytics Rule Configuration

* Rule Type: Scheduled
* Severity: High
* Trigger: Results > 0
* Frequency: Every 5 minutes
* Data Range: Last 1 day

---

## 🚨 Alerts & Incidents

When the rule is triggered:

* Alerts are generated in Microsoft Sentinel
* Incidents are automatically created
* Multiple alerts detected from the same malicious IP

---

## 🔎 Investigation

The incident investigation includes:

* IP address identification
* User (caller) information
* Activity details
* Alert classification
* Detection source validation

---

## 🤖 Automation (Playbook)

* Logic App triggers on incident creation
* Sends alert notification (email)
* Demonstrates automated SOC response workflow

---

## 📸 Screenshots

screenshots/threat-intelligence.png
screenshots/detection-logs.png
screenshots/analytics-rule.png
screenshots/alerts.png
screenshots/incident-investigation.png
screenshots/email-alert.png

---

## 📂 Project Structure

```
.
├── screenshots/
├── kql/
│   └── detection-query.kql
└── README.md
```

---

## 💡 Key Skills Demonstrated

* SIEM configuration (Microsoft Sentinel)
* KQL query development
* Threat intelligence integration
* Alert tuning and rule creation
* Incident investigation
* Security automation (SOAR)

---

## 🚀 Outcome

Successfully built an end-to-end SOC detection and response workflow:

* Detected malicious IP activity
* Generated alerts and incidents
* Investigated security events
* Automated response using playbooks

---

## 📌 Author

Tanvir Farhad
