# 🛡️ AI-Powered SOC L1 Security Operations & Incident Response Automation

### `n8n` • `Splunk` • `Gemini` • `VirusTotal` • `Jira` • `Cloudflare Tunnel`

## 🎯 Overview

This project implements an automated **SOC L1 security investigation and incident response workflow** using n8n Cloud. Security alerts are received through a webhook, processed through AI-assisted investigation agents, enriched with Splunk and VirusTotal, documented through Jira, and followed by email notifications and L2 escalation for high-severity incidents.

---

## 🔄 n8n Workflow

### SOC L1 Alert Investigation & Escalation

```text
🚨 Security Alert
        │
        ▼
🔗 Webhook
        │
        ▼
📝 Edit Fields
        │
        ▼
🤖 SOC L1 Investigation AI Agent
        │
        ├──────────────► ✨ Google Gemini Chat Model
        │
        └──────────────► 📊 Splunk
        │
        ▼
🤖 AI Investigation & Enrichment Agent
        │
        ├──────────────► ✨ Google Gemini Chat Model
        │
        ├──────────────► 🛡️ VirusTotal Lookup
        │
        └──────────────► 🎫 Jira
        │
        ▼
📧 Gmail
   Investigation Completed
        │
        ▼
🔀 IF — Severity Check
        │
        ├── FALSE ──► End
        │
        └── TRUE
              │
              ▼
📧 Gmail
   🚨 High Severity Incident
   Escalated to L2
```

---

## 🤖 AI Agent Architecture

### 1️⃣ SOC L1 Investigation AI Agent

The first AI agent performs the initial security investigation using:

**Tools:**

* ✨ Google Gemini Chat Model
* 📊 Splunk

**Responsibilities:**

* Analyze the incoming security alert
* Perform initial SOC L1 triage
* Investigate relevant security events in Splunk
* Review alert context and supporting log data
* Identify indicators and investigation findings
* Prepare the investigation context for the next stage

---

### 2️⃣ AI Investigation & Enrichment Agent

The second AI agent continues the investigation and enrichment process.

**Tools:**

* ✨ Google Gemini Chat Model
* 🛡️ VirusTotal Lookup
* 🎫 Jira

**Responsibilities:**

* Analyze the investigation results from the first AI agent
* Perform threat-intelligence enrichment
* Validate relevant indicators using VirusTotal
* Determine the security severity/classification
* Create or update the Jira incident
* Prepare the final investigation result

---

## 📧 Notification & Escalation

After the AI-assisted investigation is completed:

```text
Investigation Completed
        │
        ▼
     📧 Gmail
        │
        ▼
   🔀 Severity Check
      /       \
   FALSE       TRUE
     │           │
     ▼           ▼
   End      📧 Gmail
            High Severity
            Escalated to L2
```

### Normal Investigation

A Gmail notification is sent when the investigation is completed.

### High-Severity Investigation

If the IF condition evaluates to **TRUE**, a separate Gmail notification is sent indicating that the **high-severity incident has been escalated to L2**.

---

## 🧰 Tools & Technologies

| Technology               | Purpose                                         |
| ------------------------ | ----------------------------------------------- |
| 🔗 **n8n Cloud**         | Workflow automation and orchestration           |
| ✨ **Google Gemini**      | AI-assisted security investigation and analysis |
| 📊 **Splunk**            | SIEM log analysis and security investigation    |
| 🛡️ **VirusTotal**       | Threat intelligence and IOC enrichment          |
| 🎫 **Jira**              | Incident creation and management                |
| 📧 **Gmail**             | Investigation and escalation notifications      |
| ☁️ **Cloudflare Tunnel** | Connectivity between cloud n8n and local Splunk |

---

## ⭐ Key Features

* 🚨 Automated security alert intake
* 🔗 Webhook-based alert processing
* 🤖 Multi-stage AI-assisted SOC investigation
* 📊 Splunk-based event investigation
* 🛡️ VirusTotal threat-intelligence enrichment
* 🎫 Automated Jira incident management
* 📧 Investigation completion notifications
* 🔀 Severity-based decision logic
* 🚨 High-severity L2 escalation notifications
* ☁️ Cloud-to-local connectivity using Cloudflare Tunnel

---

## 📂 Repository Structure

```text
AI-SOC-L1-Automation/
│
├── 📁 workflow/
│   └── SOC-L1-Investigation.json
│
├── 📁 screenshots/
│   ├── n8n-workflow.png
│   ├── splunk-investigation.png
│   ├── virustotal-enrichment.png
│   ├── ai-investigation.png
│   ├── jira-incident.png
│   ├── investigation-completed.png
│   └── l2-escalation.png
│
├── 📄 README.md
└── 📄 .gitignore
```

---

## 🔐 Security

> **No API keys, passwords, authentication tokens, or other sensitive credentials are included in this repository.** Credentials should be configured separately within n8n.

---

## 🎓 Skills Demonstrated

`SOC L1 Operations` • `Alert Triage` • `SIEM Investigation` • `Threat Intelligence` • `IOC Enrichment` • `Security Automation` • `AI-Assisted Investigation` • `Incident Management` • `L2 Escalation` • `Splunk` • `n8n` • `VirusTotal` • `Jira`

---

### 🔐 Automate • Investigate • Enrich • Escalate
