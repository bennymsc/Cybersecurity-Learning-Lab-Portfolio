🧪 LLMNR / NBT-NS Poisoning Analysis – Network Traffic Investigation (CyberDefenders)

## 📌 Scenario Overview

During a routine network monitoring activity, suspicious name resolution traffic was detected within the internal network.  
The behavior suggested a potential **LLMNR/NBT-NS poisoning attack**, commonly abused by attackers to capture authentication hashes and perform lateral movement.

The objective of this lab is to analyze **network traffic using Wireshark** to identify the rogue machine, compromised accounts, and affected systems involved in the attack.

---

## 🎯 Objective

The goals of this investigation are to:

- Analyze packet captures (PCAP) for suspicious name resolution traffic
- Identify **LLMNR and NBT-NS poisoning activity**
- Determine the rogue host responding to name resolution requests
- Identify compromised user accounts and affected systems
- Understand the attack flow from a Blue Team perspective

---

## 🧠 Investigation Methodology

The analysis followed these steps:

1. Load and inspect the PCAP file in Wireshark
2. Filter for LLMNR and NBT-NS traffic
3. Identify abnormal responses to broadcast name resolution requests
4. Determine the source IP and hostname of the rogue machine
5. Analyze authentication attempts and leaked credentials
6. Identify impacted hosts and user accounts

---

## 🔬 Network Traffic Analysis (Wireshark)

### Tool Used
- **Wireshark**

### Key Protocols Analyzed
- LLMNR (UDP/5355)
- NBT-NS (UDP/137)
- SMB authentication traffic

---

## 🚨 Identifying LLMNR / NBT-NS Poisoning

The analysis revealed:

- Broadcast name resolution requests from victim machines
- Unauthorized responses from a rogue host
- The rogue system replying to multiple unresolved hostname queries
- Follow-up authentication attempts using NTLM over SMB

This behavior is characteristic of **LLMNR/NBT-NS poisoning attacks**.

---

## 🖥️ Rogue Machine Identification

By analyzing response packets, the rogue machine was identified based on:

- Source IP address
- MAC address
- Hostname (where available)

This host was responsible for intercepting name resolution requests and initiating credential capture.

---

## 👤 Compromised Accounts & Affected Systems

The PCAP analysis exposed:

- Usernames involved in NTLM authentication attempts
- Systems attempting to authenticate to the rogue host
- Evidence of credential leakage via challenge-response authentication

These findings indicate potential **credential compromise** within the environment.

---

## 🗺️ Attack Flow Summary

1. Victim system sends LLMNR/NBT-NS broadcast request
2. Rogue machine responds, claiming to be the requested host
3. Victim initiates authentication using NTLM
4. Credentials are exposed to the attacker
5. Attacker gains material for offline cracking or relay attacks

---

## 🛡️ Defensive Takeaways

This lab highlights several defensive considerations:

- LLMNR and NBT-NS should be disabled in enterprise environments
- Network monitoring can detect abnormal name resolution behavior
- NTLM authentication is vulnerable to interception and abuse
- Strong network segmentation reduces lateral movement risk

---

## 📚 Skills Practiced

- PCAP analysis with Wireshark
- Detection of name resolution poisoning attacks
- NTLM authentication analysis
- Network-based threat detection
- Blue Team incident investigation

---

## 🏷️ Tags

`Network Analysis` · `LLMNR` · `NBT-NS` · `Wireshark` · `Credential Access` · `Blue Team` · `CyberDefenders`
