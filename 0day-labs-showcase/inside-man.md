# 🏢 Inside Man: Insider Threat Detection (Design Case Study)

**Focus:** Physical-Digital Correlation & Host-Based Forensics  
**Difficulty:** Normal | **Duration:** 12 Phases | **Architecture:** Behavioral Timeline Analysis

> *A simulation built around the hardest threat to detect — the actor who already has a badge. Operatives must bridge physical access logs, local DHCP records, endpoint process trees, and unstructured data streams to attribute an active insider exfiltration.*

← [Back to 0Day Labs Overview](README.md)

---

## The Design Challenge
Insider threats are uniquely difficult because the adversary behaves like a legitimate user — they badge into the facility, log into an authenticated session, and leverage native system utilities. Traditional perimeter defenses fail because the network connections themselves map to valid credentials.

For **Inside Man**, the core design objective was to build a scenario where no single log source tells the entire story. The environment enforces **Multi-Source Attribution**. Operatives cannot rely on pre-built SIEM dashboards; instead, they must manually stitch together indicators from proxy flows, physical badge access telemetry, local endpoint forensics, and raw, unstructured text files to identify the threat actor.

---

## Data Architecture & Schema
The corporate environment uses six log sources to generate the synthetic dataset. Success relies on an operative's ability to cross-correlate physical timestamps with digital system modifications.

| Log Source | Investigative Purpose |
|---|---|
| `proxy` | Auditing outbound traffic volume and identifying unauthorized exfiltration destinations. |
| `dhcp` | Mapping non-standard IP leases to hardware MAC addresses and device hostnames. |
| `endpoint` | Tracing local process execution trees, system commands, and anti-forensics activity. |
| `badge` | Tracking physical access events across localized keycard readers. |
| `netflow` | Analyzing persistent connections and protocol tunnels post-exfiltration. |
| `notes` | Parsing unstructured, suspect-authored files for operational intelligence and metadata. |

---

## Investigative Methodology

### Act I: Initial Detection & Rogue Hardware (Phases 1–3)
The investigation triggers on a high-volume outbound data spike, but the source device cannot be traced to the standard asset inventory.
*   **The Challenge:** High-frequency proxy logs contain deliberate "noise," including multiple decoy IPs conducting large data transfers. Operatives must isolate the specific anomalies within the volume metrics to find the true rogue device. They then run a DHCP lookup to uncover an unmapped device hostname that violates the corporate naming convention, concluding with a hardware OUI lookup on the MAC address prefix to confirm that a physical rogue asset was planted on-premises.
*   **Skill Demonstrated:** **Baseline Analysis & Asset Identification.** Verifying hardware vendor prefixes via Organizationally Unique Identifiers (OUI) and isolating malicious traffic among volume-heavy decoys.

### Act II: Suspect Identification & Staging (Phases 4–6)
The simulation pivots from network-layer anomalies to host-based and physical forensics.
*   **The Challenge:** Operatives audit physical badge logs for the specific area where the rogue hardware was installed, correlating access timestamps with the exact minute the device leased an IP. Once a suspect is isolated, the hunt moves to local endpoint logs to reconstruct the file-staging pipeline—identifying specific archiving utilities creating password-protected archives and locating hidden configuration details buried inside the suspect's unstructured personal text files.
*   **Skill Demonstrated:** **Physical-Digital Correlation & Process Chain Analysis.** Mapping physical employee movement to endpoint system modifications and reverse-engineering local file compression events.

### Act III: Timeline Reconstruction & Quantification (Phases 7–9)
This act tests an operative’s data integrity validation and incident reporting capabilities.
*   **The Challenge:** Operatives are required to extract granular time metrics directly from network handshakes to build a rigid evidentiary timeline. They must accurately quantify the breach size by filtering out decoy destinations and aggregating only the specific bytes sent to the threat actor's infrastructure. The act finishes with the analysis of geographic coordinates recovered from text logs to map operational dead drops.
*   **Skill Demonstrated:** **Data Aggregation & Forensic Precision.** Calculating absolute data transfer sizes and evaluating chain-of-custody decisions when presented with branching containment playbooks.

### Act IV: Anti-Forensics & Advanced Attribution (Phases 10–12)
The final phases focus on tracking defensive evasion tactics and identifying external orchestration.
*   **The Challenge:** The adversary attempts to cover their tracks by executing host log-clearing commands. Operatives must filter through administrative event logs to distinguish legitimate corporate queries from unauthorized system deletions. Netflow analysis is then required to identify a long-duration, persistent protocol tunnel established over a standard port, culminating in the extraction of the external threat group's unique identifier.
*   **Skill Demonstrated:** **Defensive Evasion Detection & Threat Group Mapping.** Identifying event log manipulation, auditing protocol tunneling characteristics, and conducting final threat actor attribution.

---

## Visual Walkthrough

### [Screenshot: Physical-Digital Correlation] ## 🚧 Under Construction
<!--
RECOMMENDED: A screenshot showing badge log results alongside DHCP results,
illustrating the moment the suspect is identified by timestamp overlap.
-->
![Physical Correlation](../images/inside-man-correlation.png)

### [Screenshot: Endpoint Forensics Timeline] ## 🚧 Under Construction
<!--
RECOMMENDED: A screenshot of the endpoint log filtered to DAVE-PC,
showing the 7z.exe → robocopy.exe process chain sorted by timestamp.
-->
![Endpoint Forensics](../images/inside-man-endpoint.png)

---

## MITRE ATT&CK® Mapping
This simulation provides hands-on practice with the following techniques:

*   **Exfiltration Over Web Service (T1567):** Identifying unauthorized volume spikes directed at external web servers.
*   **System Information Discovery (T1082):** Leveraging hardware registration signatures to profile rogue assets.
*   **Archive Collected Data (T1560):** Tracing local endpoint process trees to isolate automated file compression and staging commands.
*   **Credentials in Files (T1552.001):** Extracting cleartext security metrics and passwords from unstructured application notes.
*   **Indicator Removal (T1070):** Detecting localized event log destruction commands using platform utilities (`wevtutil`).
*   **Protocol Tunneling (T1572):** Isolating persistent, long-duration encrypted network connections hiding within standard administrative traffic.

---

*← [Back to 0Day Labs Overview](README.md)*

