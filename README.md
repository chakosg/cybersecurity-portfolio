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

## About This Portfolio

These investigations were conducted while monitoring real network telemetry through the PISCES cybersecurity monitoring program.

During this monitoring period, suspicious network activity was investigated using intrusion detection alerts, SIEM dashboards, and external threat intelligence resources. Each investigation documents the methodology used to analyze alerts, validate indicators of compromise, and determine whether activity warranted escalation.

This repository demonstrates practical SOC analyst skills including event investigation, threat intelligence correlation, and security incident reporting.
