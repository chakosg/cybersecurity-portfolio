# 🛸 Nexus-7: Alien Probe Infiltration (Design Case Study)

**Focus:** Multi-Source Log Correlation & Signal-to-Noise Analysis  
**Difficulty:** Operative | **Duration:** 9 Phases | **Architecture:** Narrative-Driven Investigation

> *A narrative-driven simulation where operatives must identify an anomalous signal within a station's quantum subnet. This module forces users to move beyond single-log analysis and practice correlating data across disparate sources.*

← [Back to 0Day Labs Overview](README.md)

---

## The Design Challenge
In traditional "Capture the Flag" (CTF) events, the answer is often highlighted or easy to find once you know the tool. For **Nexus-7**, I wanted to build something more realistic: a "needle in a haystack" scenario. 

I engineered a synthetic dataset of **1,500+ log entries**. The challenge isn't just knowing the syntax; it’s knowing how to filter out "known-good" station noise to find the subtle indicators of an active breach.

---

## Data Architecture & Schema
I designed the Nexus-7 environment with a complex schema to mirror a professional enterprise SIEM. To succeed, the operative must understand how different logs interact.

| Log Source | Investigative Purpose |
|---|---|
| `neural_transmission` | Identifying initial phishing vectors and sender anomalies. |
| `warp_web` | Tracing egress traffic to unauthorized or typosquatted external domains. |
| `neuralink_endpoint` | Detecting account takeovers and unauthorized command execution. |
| `quantum_comms` | Analyzing network metadata for Command & Control (C2) beaconing. |
| `biosync_interface` | Auditing authentication events and identifying token/credential abuse. |

---

## Investigative Methodology

### Phase 1: Cross-Source Correlation
**The Challenge:** An unknown signal is hitting the station. 
**The Logic:** I designed the dataset so that legitimate Internal IPs are siloed within their respective logs. The probe's IP is the only one that bridges three distinct log types simultaneously. 
*   **Skill Demonstrated:** The operative must use **Join logic** to identify the one IP address appearing where it shouldn't.

### Phase 2: User Behavior Analysis (UBA)
**The Challenge:** The threat actor begins leveraging legitimate crew credentials to move laterally.
**The Logic:** I planted "decoy" accounts that look suspicious but are actually routine. The operative must identify the specific `CrewID` that is consistently failing integrity checks while executing unauthorized "Action" strings in the neuralink logs.
*   **Skill Demonstrated:** Moving from network-based detection to identity-based detection.

### Phase 3: Traffic Blending & C2 Detection
**The Challenge:** Identifying the "Fleet Coordinator" directing the attack from deep space. 
**The Logic:** I planted high-frequency IPs to distract the user. An operative who sorts by "most frequent" will find a decoy. However, the true coordinator only communicates at `CRITICAL` priority. 
*   **Skill Demonstrated:** Prioritizing severity over volume—a critical skill for Tier 1 SOC analysts.

---

## Visual Walkthrough

### [Video: Investigative Workflow]
<!-- 
RECOMMENDED: A 30-second screen recording showing:
1. Writing a SIEQL query.
2. The logs populating the screen.
3. Highlighting a specific anomalous entry.
-->
![Investigative Workflow](images/nexus7-workflow.gif)

### [Screenshot: The Instructional Layer]
<!-- 
RECOMMENDED: A screenshot of a "Debrief Card" or the "NEXUS-AI" guidance. 
This proves the platform teaches the "Why" behind the investigation.
-->
![Educational Debrief](images/debrief.png)

---

## MITRE ATT&CK® Mapping
This simulation provides hands-on practice with the following techniques:

*   **Phishing (T1566):** Analyzing malicious attachments and sender spoofing.
*   **Valid Accounts (T1078):** Identifying lateral movement through compromised internal IDs.
*   **C2 Infrastructure (TA0011):** Tracing communications to unregistered external domains.
*   **Steal Application Access Token (T1528):** Detecting "OVERRIDE" token abuse in authentication logs.

---

*← [Back to 0Day Labs Overview](README.md)*
