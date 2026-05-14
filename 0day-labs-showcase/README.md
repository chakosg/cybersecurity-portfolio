# 0 Day Labs — Cybersecurity Investigation Simulator

> *The best way to learn threat hunting is to hunt threats.*

**0 Day Labs** is a gamified, narrative-driven cybersecurity training platform I am designing and building to teach real investigative techniques through immersive, multi-phase simulations. Operatives receive realistic synthetic log data, query it using a purpose-built query language, and progress by finding actual answers buried in noise — no multiple choice, no hand-holding.

---

## Table of Contents

- [The Mission](#the-mission)
- [Platform Overview](#platform-overview)
- [SIEQL — The Query Language](#sieql--the-query-language)
- [Simulations](#simulations)
- [Instructional Design Philosophy](#instructional-design-philosophy)
- [Design & Implementation](#design--implementation)

---

## The Mission

Most cybersecurity training tools teach *about* security. 0 Day Labs teaches you to *do* security.

During my studies, I discovered a passion for the hunt — triage, escalation, mitigation. After graduation, I ran into the industry's Catch-22: you can't get the job without experience, but you can't get SOC experience without the job.

I am building 0 Day Labs to break that cycle. It is my personal laboratory where I continue to sharpen my investigative edge — and a sandbox others can use to bridge the gap between classroom theory and real-world SOC operations.

---

## Platform Overview

0 Day Labs is a browser-based investigation environment designed to replicate the workflow of a Tier 1 Security Operations Center (SOC). It functions as a "bridge" between theoretical learning and professional toolsets by immersing the user in a persistent, narrative-driven simulation.

### The Ecosystem
The platform consists of a specialized investigation terminal where operatives interact with a live-simulated database. Unlike static labs, the environment is dynamic; users must manage their own "Case Notes," track Indicators of Compromise (IOCs), and navigate a multi-act storyline where their decisions and query accuracy directly impact their final performance rating.

### Key Components:
*   **The Command Terminal:** A central hub where operatives execute SIEQL queries to parse through thousands of synthetic log entries. It is designed to mimic the high-pressure environment of a real SIEM dashboard.
*   **Narrative Objectives:** Simulations are broken into "Acts" and "Phases." Operatives are given mission briefings and must discover specific technical evidence; such as malicious IP addresses, file hashes, or unauthorized user accounts to advance the story.
*   **Real-World Integration:** The platform encourages the use of external tools. Operatives often have to take data discovered within 0 Day Labs and verify it using real-world OSINT resources like VirusTotal, AbuseIPDB, and Shodan.
*   **The Debrief System:** Upon completion, the platform generates a comprehensive Incident Report. This report correlates the operative’s actions with real-worl frameworks, providing a clear map of how the simulated hunt translates to actual defensive skills.

---

## SIEQL — The Query Language

A core design decision was building a custom query language rather than relying on free-text search. Operatives write structured queries that mirror real SIEM tooling — Splunk SPL, Microsoft Sentinel KQL — in a controlled, instructional environment.

**Type == "quantum_comms" | where Severity == "CRITICAL" | sort Timestamp desc | take 10**

Operatives learn field-based filtering, pipeline operators, boolean logic, and severity triage — transferable skills, not platform-specific trivia.

---

## Simulations

### 🛸 [Nexus-7: Alien Probe Infiltration](nexus7.md)

An alien probe has breached Nexus-7 Orbital Station's quantum subnet. Operatives analyze 1,500+ dynamically generated SIEM log entries across six log types to trace the intrusion from initial scan to kill-switch neutralization.

**9 phases · 3 acts · MITRE ATT&CK aligned**

---

### 🎣 [Phish & Ships: Maritime Supply Chain Attack](phish-and-ships.md)

A fishing charter company's boss clicked a suspicious invoice. Operatives use SIEM logs and external OSINT tools — VirusTotal, AbuseIPDB, Shodan — to trace a QakBot-style intrusion from phishing delivery to C2 identification.

**9 phases · 3 acts · real OSINT tools integrated**

---

### 🛡️ [Inside Man: Insider Threat Investigation](inside-man.md)

Anomalous data exfiltration detected from a breakroom terminal. Operatives trace a rogue device, correlate DHCP logs with badge access records, reconstruct a 9.5GB exfiltration timeline, and identify the external handler through dead drop coordinates buried in suspect notes.

**12 phases · 4 acts · physical-digital correlation**

---

### 🔐 [Lost in Translation: Cryptanalysis Division](lost-in-translation.md)

A ransomware operator has been coordinating through layered classical ciphers. Ten intercepted transmissions, ten encoding schemes: Base64, hex, Caesar, binary, Vigenère, URL encoding, XOR, hash cracking, Morse code, and chained multi-layer ciphers.

**10 phases · 2 acts · 3 difficulty tiers**

---

## Instructional Design Philosophy

Every element of 0 Day Labs is designed around one principle: **the operative has to earn the answer.**

- **No multiple choice** — operatives submit exact values discovered within log data
- **Randomized answers** — simulations generate unique answers per session; sharing answers between operatives does not help
- **Tiered AI guidance** — the in-game analyst provides Socratic hints calibrated to attempt count, managing frustration without removing the challenge
- **Debrief cards** — after every phase, a field note maps the technique to MITRE ATT&CK and provides real-world context and further reading
- **Consequence system** — branch decisions are scored and reflected in the final AI-generated SOC incident report

---

## Design & Implementation

I designed the full simulation architecture — threat scenarios, MITRE mappings, phase objectives, branching logic, query language, and all educational content. Development was accelerated by leveraging AI as a technical force-multiplier, allowing me to function as a one-person product and security design team while shipping a full-stack platform across four simulations simultaneously.

The AI handled implementation of specifications I authored. Every phase objective, clue, answer logic, consequence narrative, and debrief card was written by me.

---

*0Day Labs is a private R&D platform. Source code is not public. This showcase documents the design, architecture, and educational intent of the project.*
