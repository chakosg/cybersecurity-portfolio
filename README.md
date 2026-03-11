# Cybersecurity Investigation Portfolio – Gabriel Chakos

This repository contains documented cybersecurity investigations conducted while monitoring live network telemetry within a SIEM environment through the PISCES cybersecurity program.

The investigations demonstrate practical Security Operations Center (SOC) analyst skills including intrusion detection monitoring, threat intelligence research, and security event investigation.

---

## Table of Contents

* [About This Portfolio](#about-this-portfolio)
* [Tools and Technologies](#tools-and-technologies)
* [Skills Demonstrated](#skills-demonstrated)
* [Investigations](#investigations)
* [Example Detection Logic](#example-detection-logic)

## About This Portfolio

These investigations were conducted while monitoring real network telemetry through the PISCES cybersecurity monitoring program.

During this monitoring period, suspicious network activity was investigated using intrusion detection alerts, SIEM dashboards, and external threat intelligence resources. Each investigation documents the methodology used to analyze alerts, validate indicators of compromise, and determine whether activity warranted escalation.

This repository demonstrates practical SOC analyst skills including event investigation, threat intelligence correlation, and security incident reporting.

---

## Tools and Technologies

The following platforms and tools were used during monitoring and investigation:

![Elastic Stack](https://img.shields.io/badge/Elastic-Stack-005571?logo=elastic&logoColor=white)
![Kibana](https://img.shields.io/badge/Kibana-Data%20Visualization-E8478B?logo=kibana&logoColor=white)
![Suricata](https://img.shields.io/badge/Suricata-IDS-EF3B2D)
![VirusTotal](https://img.shields.io/badge/VirusTotal-Threat%20Intelligence-394EFF)
![GreyNoise](https://img.shields.io/badge/GreyNoise-Internet%20Scanning%20Intel-4B0082)
![AbuseIPDB](https://img.shields.io/badge/AbuseIPDB-IP%20Reputation-2C7BE5)
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

## Investigations

### Mirai Botnet Scanning Activity

Investigation of intrusion detection alerts associated with Mirai-style botnet scanning activity targeting IoT devices such as DVR systems and routers.

Key investigation steps included:

* Identifying IDS signatures triggered by suspicious traffic
* Analyzing alert patterns within the SIEM dashboard
* Correlating source IP reputation using threat intelligence platforms
* Determining the activity was consistent with automated botnet reconnaissance

---

### TP-Link Router Exploit Attempt (CVE-2023-1389)

Investigation of alerts associated with exploitation attempts targeting a command injection vulnerability affecting TP-Link routers.

Key investigation steps included:

* Reviewing Suricata IDS alerts referencing CVE-2023-1389
* Researching vulnerability details using threat intelligence sources
* Analyzing traffic behavior and alert patterns within the SIEM
* Determining the activity was consistent with known exploitation attempts targeting vulnerable routers

---

### Internet-Wide Scanning Activity (ZMap / Stretchoid)

Investigation of large-scale reconnaissance scanning activity identified through intrusion detection alerts and threat intelligence research.

Key investigation steps included:

* Reviewing IDS alerts indicating potential reconnaissance activity
* Investigating source IP behavior using GreyNoise intelligence data
* Identifying scanning patterns consistent with internet-wide research scanning
* Determining the activity was likely related to large-scale scanning infrastructure such as ZMap or Stretchoid scanning projects

---

## Example Detection Logic

Below are examples of detection logic concepts related to events investigated within this portfolio.

### Mirai Botnet Scanning Detection (Suricata IDS)

Example IDS signature associated with Mirai-style Telnet scanning:

```
alert tcp any any -> any 23 (msg:"Possible Mirai Telnet Scan"; flags:S; threshold:type threshold, track by_src, count 20, seconds 60; sid:1000001;)
```

This type of detection rule helps identify high volumes of Telnet connection attempts commonly associated with Mirai botnet propagation.

---

### Network Reconnaissance Detection

Reconnaissance scanning activity can often be detected by identifying abnormal connection attempts across multiple ports or hosts within a short time window.

Typical indicators include:

* Multiple connection attempts from a single source IP
* Sequential or wide-range port targeting
* High connection rates within a short time interval

These behaviors are commonly associated with automated scanning tools used for internet-wide reconnaissance.

---

### Exploit Attempt Detection (CVE-2023-1389)

Intrusion detection systems may use signatures or detection logic to identify exploit attempts targeting known vulnerabilities.

Indicators may include:

* HTTP requests containing suspicious command injection patterns
* Requests targeting known vulnerable router e
