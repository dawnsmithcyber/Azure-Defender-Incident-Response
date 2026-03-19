# Forensic-Analysis-Defender-Endpoint
Real-time simulation of a multi-stage cyber attack lifecycle using Microsoft Defender for Endpoint. This project demonstrates active threat hunting, XOR-obfuscated payload analysis, and automated host isolation/remediation to resolve a Brute Force-to-Ransomware incident.

## 📋 Project Overview
### The primary objective of this project was to demonstrate the technical precision required to navigate a modern incident response lifecycle. Moving beyond basic alert monitoring, I conducted a deep-dive investigation into a stealthy entry attempt. This lab highlights the ability to "unmask" hidden threats using Live Response forensics, successfully transitioning from initial detection to full environment hardening and post-incident resolution.
---

## 🚀 The Workflow

### 1. Initial Access: Brute Force Detection
* **Scenario:** Identified a persistent **Brute Force** attack where an unauthorized endpoint attempted to gain access via automated credential guessing.
* **Analysis:** Monitored the attack patterns in real-time, identifying the source IP and the targeted accounts before the "entry" could lead to a full system compromise.
* **Tooling:** Utilized **Microsoft Sentinel** to track failed logon patterns and trigger high-severity incidents based on anomalous authentication traffic.

### 2. Obfuscation Analysis (The "Unmasking")
* **Challenge:** Analyzed a sneaky PowerShell loader designed to bypass static security scanners. 
* **Technical Deep Dive:** The payload used **XOR Encryption** to scramble the code into "gibberish" strings, allowing it to sit on the disk without triggering signature-based alerts.
* **Action:** Developed and executed a decryption script using the identified XOR key (`WinATP-Intro-Injection`) to reveal the hidden command intent and underlying malicious instructions.

### 3. Mitigation & Resolution
* **Containment:** Once the threat was confirmed, I utilized **Microsoft Defender for Endpoint** to **Isolate the Workstation**. This "digital quarantine" prevented lateral movement and blocked the attacker's communication with the C2 (Command & Control) server.
* **Hardening:** Identified the security gaps that allowed the initial access and patched the vulnerabilities.
* **Recovery:** Followed system-recommended actions to ensure the threat was fully neutralized and the incident was marked as resolved.

### 4. Live Response & Forensics
* **Remote Investigation:** Executed forensic scripts via the **Live Response** console to inspect the isolated machine's memory and process tree in real-time.
* **Result:** Successfully identified the attacker's intended payload and collected artifacts for a post-mortem report without requiring physical access to the device.

---

## 🧠 The Cybersecurity Mindset: Beyond the Surface
The most impactful part of this lab was the **de-obfuscation** process. In cybersecurity, we often deal with "invisible ink" - code designed to hide in plain sight. 

By applying XOR decryption, I revealed the **hidden intent** behind a seemingly blank file. This reinforces a vital lesson for any investigator: **Detection is just the beginning.** True security comes from the persistence to look past the surface, decode the attacker's playbook, and understand exactly what is happening in the system's memory.

---

## 🛠️ Technical Skills & Tools
* **SIEM/SOAR:** Microsoft Sentinel (Incident Management & Log Analysis)
* **EDR:** Microsoft Defender for Endpoint (Host Isolation & Remediation)
* **Scripting:** PowerShell (Payload Analysis & Forensic Scripting)
* **Threat Hunting:** XOR Decryption, Base64 Decoding, & IoC Identification
* **Frameworks:** MITRE ATT&CK (Brute Force, Obfuscated Files, PowerShell Execution)

---

## 📸 Evidence & Screenshots
<img width="1259" height="674" alt="2" src="https://github.com/user-attachments/assets/71967476-78c2-4f97-8a2f-efacd04e0134" />
<img width="1271" height="677" alt="3" src="https://github.com/user-attachments/assets/38f1f39c-d75f-43b5-b885-8dd0a2f1da7f" />

