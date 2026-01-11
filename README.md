🚨 SOC Automation Project 2.0 – MyDFIR

AI-Driven SOC Alert Enrichment & Automated Incident Reporting

📌 Overview

This project implements a real-world SOC Automation workflow that detects security events, enriches them with threat intelligence, applies AI-based analysis, and automatically notifies analysts via Slack.

The project demonstrates how modern SOC teams reduce alert fatigue and MTTR by transforming raw SIEM alerts into context-rich, actionable incident reports.

🎯 Project Goals

Detect brute-force authentication attempts

Enrich Indicators of Compromise (IOCs) automatically

Generate AI-based incident summaries

Map alerts to MITRE ATT&CK

Deliver enriched alerts to SOC analysts via Slack

🏗️ Architecture
Endpoint Logs
   │
   ▼
Splunk SIEM
   │
(Alert Trigger)
   ▼
Webhook (SOAR)
   │
   ▼
AI Analysis Engine
   │
   ▼
Threat Intelligence (AbuseIPDB)
   │
   ▼
Slack SOC Alerts (#alerts)

🖥️ Lab Environment
Virtualization

VMware Workstation

Machines
System	Role
Windows 10	Endpoint (Security Logs)
Ubuntu	Splunk Enterprise (SIEM)
Ubuntu	SOAR / Automation Engine
Ubuntu	Incident Response Node
Kali Linux	Attack Simulation
🛠️ Tools & Technologies

Splunk Enterprise

Splunk Universal Forwarder

Slack API

AbuseIPDB Threat Intelligence API

AI / LLM for alert summarization

Webhook-based SOAR workflow

MITRE ATT&CK Framework

🚨 Detection Use Case
Brute Force Authentication Detection

Windows failed login attempts are detected using:

index="beast005" EventCode=4625

Correlation & Context
index="beast005" EventCode=4625
| stats count by _time, ComputerName, user, src_ip


This identifies:

Source IP

Targeted user

Frequency of attempts

Host involved

🔄 SOC Automation Workflow

Splunk Alert triggers on suspicious authentication activity

Webhook sends alert data to SOAR workflow

AI Engine generates incident summary and severity

AbuseIPDB enriches source IP with reputation data

Slack receives a fully enriched SOC alert

📣 Automated Slack Alert Example

Source IP: 134.209.201.69

Abuse Confidence: 100/100

ISP: DigitalOcean, LLC

Country: Netherlands

Attack Type: SSH Brute Force

Severity: High

MITRE ATT&CK Mapping

T1110 – Brute Force

T1078 – Valid Accounts

🧠 Intelligent Severity Handling

Public IPs → Enriched + High severity

Private/Internal IPs → Identified correctly, lower severity

Reduces false positives and analyst fatigue

📊 Key Outcomes

✅ End-to-end SOC automation

✅ AI-generated analyst-ready alerts

✅ Reduced manual investigation time

✅ Real-world SOC workflow simulation

✅ Blue-team practical experience
