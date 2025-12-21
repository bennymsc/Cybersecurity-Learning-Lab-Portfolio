🧪 Yellow RAT Lab – Malware & Threat Intelligence Analysis (CyberDefenders)

## 📌 Scenario Overview

During a routine IT security check at **GlobalTech Industries**, abnormal outbound network traffic was detected from multiple employee workstations.  
Further investigation revealed that users’ search queries were being **redirected to unfamiliar external websites**, raising concerns of a possible malware infection.

The incident suggested the presence of a **malicious program capable of intercepting browser traffic**, potentially exposing users to further compromise or data leakage.

This lab focuses on analyzing malware-related artifacts using **threat intelligence platforms** to understand the nature of the threat, its infrastructure, and its objectives.

---

## 🎯 Objective

The goal of this investigation is to:

- Identify malware-related **Indicators of Compromise (IOCs)**
- Use **threat intelligence sources** (e.g., VirusTotal) to analyze suspicious artifacts
- Understand the malware’s behavior and potential **Command & Control (C2)** infrastructure
- Assess the **impact and intent** of the attack
- Derive **defensive insights** for detection and mitigation

---

## 🧠 Investigation Approach

The analysis was conducted following a structured incident investigation methodology:

1. Identification of suspicious artifacts (hashes, domains, URLs)
2. Enrichment using threat intelligence platforms
3. Correlation of indicators with known malware families
4. Analysis of infrastructure and adversary behavior
5. Assessment of security impact and response considerations

---

## 🔍 Threat Intelligence Analysis

### Tools Used
- **VirusTotal**
- Open-source intelligence (OSINT)

### Key Findings
- The suspicious artifacts were associated with a **Remote Access Trojan (RAT)** commonly referred to as *Yellow RAT*
- The malware exhibited behaviors consistent with:
  - Browser traffic manipulation
  - Search query redirection
  - Communication with external servers
- Multiple antivirus engines flagged the samples as malicious, indicating known threat patterns

---

## 🌐 Command & Control (C2) Infrastructure

Threat intelligence enrichment revealed:

- External IP addresses and/or domains associated with malicious activity
- Infrastructure with low reputation scores
- Indicators suggesting centralized command-and-control communication

These findings reinforce the conclusion that infected hosts were likely communicating with attacker-controlled servers.

---

## 🧩 Attack Assessment

Based on the collected evidence:

- **Initial Access:** Likely achieved via user interaction (malicious download, browser exploit, or bundled software)
- **Execution:** Malware executed on multiple endpoints
- **Persistence:** Possible via browser modification or startup mechanisms
- **Impact:** Traffic interception, redirection, and potential exposure to secondary payloads

---

## 🛡️ Defensive Takeaways

From a defensive standpoint, this investigation highlights:

- The importance of monitoring **DNS and HTTP redirection patterns**
- The value of **threat intelligence enrichment** during incident response
- The need for endpoint protection capable of detecting browser-based threats
- The usefulness of IOC-based detection for early identification

---

## 📚 Skills Practiced

- Malware triage using threat intelligence platforms
- IOC extraction and correlation
- Understanding RAT behavior and infrastructure
- Incident analysis from a defensive (Blue Team) perspective
- Structured documentation of security investigations

---

## 🏷️ Tags

`Malware Analysis` · `Threat Intelligence` · `RAT` · `Blue Team` · `Incident Response` · `CyberDefenders`
