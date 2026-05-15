# Cybersecurity Investigation Portfolio – Gabriel Chakos

This repository contains documented cybersecurity investigations conducted while monitoring live network telemetry within a SIEM environment through the PISCES cybersecurity program, as well as architectural breakdowns of self-engineered threat simulation modules developed for the **0Day Labs** platform.

---

## Table of Contents

* [About This Portfolio](#about-this-portfolio)
* [Tools and Technologies](#tools-and-technologies)
* [Skills Demonstrated](#skills-demonstrated)
* [Threat Simulation Modules (0Day Labs)](#threat-simulation-modules-0day-labs)
* [Investigations](#investigations)
* [Example Detection Logic](#example-detection-logic)

## About This Portfolio

These investigations were conducted while monitoring real network telemetry through the PISCES International cybersecurity monitoring program.

During this monitoring period, suspicious network activity was investigated using intrusion detection alerts, SIEM dashboards, and external threat intelligence resources. Each investigation documents the methodology used to analyze alerts, validate indicators of compromise, and determine whether activity warranted escalation.

Additionally, this portfolio highlights my work on **0Day Labs**, a gamified, narrative-driven cybersecurity training platform. Operatives receive synthetic log data, query it using a custom query language called SIEQL, and progress by finding exact values buried in noise with zero multiple-choice guardrails.

This repository demonstrates practical SOC analyst skills including event investigation, threat intelligence correlation, security engineering, and incident reporting.

---

## Tools and Technologies

The following platforms and tools were used during monitoring, investigation, and platform development:

![Elastic Stack](https://img.shields.io/badge/Elastic-Stack-005571?logo=elastic&logoColor=white)
![Kibana](https://img.shields.io/badge/Kibana-Data%20Visualization-E8478B?logo=kibana&logoColor=white)
![Suricata](https://img.shields.io/badge/Suricata-IDS-EF3B2D?logo=suricata&logoColor=white)
![VirusTotal](https://img.shields.io/badge/VirusTotal-Threat%20Intelligence-394EFF?logo=virustotal&logoColor=white)
![GreyNoise](https://img.shields.io/badge/GreyNoise-Internet%20Scanning%20Intel-4B0082?logo=greynoise&logoColor=white)
![AbuseIPDB](https://img.shields.io/badge/AbuseIPDB-IP%20Reputation-2C7BE5?logo=abuseipd&logoColor=white)
![NIST](https://img.shields.io/badge/NIST-CVE%20Database-FFF005?logo=nist&logoColor=white)
![React](https://img.shields.io/badge/React-UI%20Framework-61DAFB?logo=react&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend%20API-009688?logo=fastapi&logoColor=white)

---

## Skills Demonstrated

![SIEM Monitoring](https://img.shields.io/badge/SIEM-Monitoring-blue)
![Threat Detection](https://img.shields.io/badge/Threat-Detection-red)
![Intrusion Detection](https://img.shields.io/badge/Intrusion-Detection-orange)
![Threat Intelligence](https://img.shields.io/badge/Threat-Intelligence-purple)
![Incident Analysis](https://img.shields.io/badge/Incident-Analysis-green)
![Network Traffic Analysis](https://img.shields.io/badge/Network-Traffic%20Analysis-blueviolet)
![Security Monitoring](https://img.shields.io/badge/Security-Monitoring-darkgreen)
![Incident Documentation](https://img.shields.io/badge/Incident-Documentation-lightgrey)

---

## Threat Simulation Modules (0Day Labs)

Design case studies for modules built for the 0Day Labs training environment, featuring dynamic synthetic datasets and real-world intelligence integration.

### 🛸 Nexus-7: Alien Probe Infiltration
A multi-source correlation simulation forcing users to move beyond single-log streams to discover complex network anomalies using data join logic.
  
[View Design Case Study](0day-labs-showcase/nexus7.md)

### 🎣 Phish & Ships: Maritime Supply Chain Attack
A rookie-level investigation simulation requiring a hybrid workflow that bridges internal SIEM triage with live internet OSINT tooling (VirusTotal, AbuseIPDB, Shodan).

[View Design Case Study](0day-labs-showcase/phish-and-ships.md)

### 📡 Lost in Translation: Obfuscated C2 & Ransomware Triage
A specialized incident response simulation tracking active host-encryption events and obfuscated protocols.

[View Placeholder](0day-labs-showcase/lost-in-translation.md)

### 🏢 Inside Man: Insider Threat Detection
A behavioral analysis simulation mapping anomalous administrative sessions and privilege escalation.

[View Placeholder](0day-labs-showcase/inside-man.md)

---

## Investigations

### Mirai Botnet Scanning Activity

Investigation of intrusion detection alerts associated with Mirai-style botnet scanning activity targeting IoT devices such as DVR systems and routers.

Key investigation steps included:

* Identifying IDS signatures triggered by suspicious traffic
* Analyzing alert patterns within the SIEM dashboard
* Correlating source IP reputation using threat intelligence platforms
* Determining the activity was consistent with automated botnet reconnaissance
  
[View Investigation](mirai-botnet-investigation.md)

---

### TP-Link Router Exploit Attempt (CVE-2023-1389)

Investigation of alerts associated with exploitation attempts targeting a command injection vulnerability affecting TP-Link routers.

Key investigation steps included:

* Reviewing Suricata IDS alerts referencing CVE-2023-1389
* Researching vulnerability details using threat intelligence sources
* Analyzing traffic behavior and alert patterns within the SIEM
* Determining the activity was consistent with known exploitation attempts targeting vulnerable routers

[View Investigation](tplink-router-exploit-investigation.md)

---

### Internet-Wide Scanning Activity (ZMap / Stretchoid)

Investigation of large-scale reconnaissance scanning activity identified through intrusion detection alerts and threat intelligence research.

Key investigation steps included:

* Reviewing IDS alerts indicating potential reconnaissance activity
* Investigating source IP behavior using GreyNoise intelligence data
* Identifying scanning patterns consistent with internet-wide research scanning
* Determining the activity was likely related to large-scale scanning infrastructure such as ZMap or Stretchoid scanning projects

[View Investigation](internet-scanning-investigation.md)

---

## Example Detection Logic

Below are examples of detection logic concepts related to events investigated within this portfolio.

### Mirai Botnet Scanning Detection (Suricata IDS)

Example IDS signature associated with Mirai-style Telnet scanning:
