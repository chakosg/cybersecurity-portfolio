# Cybersecurity Portfolio – Gabriel Chakos

This repository contains documented security investigations conducted while monitoring live network telemetry through the PISCES cybersecurity monitoring program.

The investigations demonstrate hands-on experience with:

* SIEM monitoring and alert triage
* Intrusion detection analysis
* Threat intelligence research
* Network traffic investigation
* Security incident documentation and escalation

## Tools Used

* Elastic Stack (SIEM)
* Kibana dashboards
* Suricata IDS
* VirusTotal
* GreyNoise
* AbuseIPDB
* Talos Intelligence

## Investigations

### Mirai Botnet Scanning Activity

Investigation of intrusion detection alerts associated with automated botnet scanning activity targeting vulnerable IoT devices. Analysis focused on identifying botnet behavior and correlating IDS alerts with threat intelligence sources.

[View Investigation](mirai-botnet-investigation.md)

---

### TP-Link Router Exploit Attempt (CVE-2023-1389)

Investigation of alerts associated with exploitation attempts targeting vulnerable TP-Link Archer AX21 routers. The analysis included vulnerability research and correlation with known command injection exploits affecting IoT devices.

[View Investigation](tplink-router-exploit-investigation.md)

---

### Internet-Wide Scanning Activity (Zmap / Stretchoid)

Investigation of automated scanning activity targeting exposed services. Analysis identified multiple scanning hosts using Zmap user-agent signatures and infrastructure linked to stretchoid.com, an organization conducting large-scale internet scanning.

[View Investigation](internet-scanning-investigation.md)

---
## Example Detection Logic

Below are examples of detection signatures and logic related to the types of security events investigated in this portfolio.

### Mirai Botnet Scanning Detection (Suricata IDS)

Example IDS signature associated with Mirai-style scanning activity:

```
alert tcp any any -> any 23 (msg:"Possible Mirai Telnet Scan"; flags:S; threshold:type threshold, track by_src, count 20, seconds 60; sid:1000001;)
```

This type of signature helps detect high volumes of Telnet connection attempts commonly associated with Mirai botnet propagation.

---

### Network Reconnaissance Detection

Reconnaissance scanning activity can often be detected by identifying abnormal connection attempts across multiple ports or hosts within a short time window.

Example detection logic concept:

* Multiple connection attempts from a single source IP
* Sequential or wide-range port targeting
* High connection rate within a short time interval

This behavior is commonly associated with automated scanning tools used for internet-wide reconnaissance.

---

### Exploit Attempt Detection (CVE-2023-1389)

Intrusion detection systems may use signatures to identify exploit attempts targeting known vulnerabilities.

Example detection logic may include:

* HTTP requests containing suspicious command injection patterns
* Requests targeting known vulnerable router endpoints
* Indicators matching known exploit payload structures

## About This Portfolio

These investigations were conducted while monitoring real network telemetry through the PISCES cybersecurity monitoring program.

During this monitoring period, suspicious network activity was investigated using intrusion detection alerts, SIEM dashboards, and external threat intelligence resources. Each investigation documents the methodology used to analyze alerts, validate indicators of compromise, and determine whether activity warranted escalation.

This repository demonstrates practical SOC analyst skills including event investigation, threat intelligence correlation, and security incident reporting.


