---
layout: default
title: Cyber Defence Frameworks
---

# Cyber Defence Frameworks

This section introduces key cybersecurity frameworks and models used to understand, detect, and mitigate adversary behavior.  
Each subtopic provides a different perspective on how analysts and organizations can approach cyber defense.

---

## Junior Security Analyst Intro
Focuses on concepts related to the role and daily activities, highlighting:  

* Monitoring  
* Triage  
* Incident escalation

---

## Pyramid of Pain
Explores how different types of indicators impact adversary adaptation and guide detection and response priorities:  

* File hashes  
* IPs  
* Domains  
* Host and network artifacts  
* Attacker tools or techniques  

---

## Cyber Kill Chain
Covers the stages of a network intrusion, showing how understanding each phase supports detection, prevention, and defense:  

1. **Reconnaissance**  
2. **Weaponization**  
3. **Delivery**  
4. **Exploitation**  
5. **Installation**  
6. **Command & Control**  
7. **Actions on Objectives (Exfiltration)** 

---

## Unified Kill Chain
A detailed attack framework complementing traditional kill chains, emphasizing:  

* All stages from reconnaissance to data exfiltration and attacker motivation  
* Real-world attacks often revisiting earlier phases  

---

## Diamond Model
Covers core elements of the Diamond Model of Intrusion Analysis to support threat assessment:  

* Adversary  
* Infrastructure  
* Capability  
* Victim  

---

## [MITRE](./mitre.md)
Resources provided by **MITRE** for understanding adversary behavior and building cybersecurity defenses.

---

## [Summit](./summit.md)
Simulates tracking an adversary through detection and defense exercises:  

* Uses the Pyramid of Pain to increase the effort required for attackers to succeed  

---

## Eviction
A scenario-driven lab simulating the role of a SOC analyst at *E-corp*, using the **MITRE ATT&CK Navigator layer** to investigate intelligence on **APT28**.  
The exercise applies practical threat intelligence to detect, analyze, and mitigate adversary actions throughout the intrusion lifecycle. Key phases include:  

* **Reconnaissance & Initial Access** – Adversaries may employ spearphishing links or compromise email accounts to prepare resources for the attack.  
* **Execution & Persistence** – Malicious files or links can trigger code execution, often observed through scripting interpreters such as *PowerShell* and *Windows Command Shell*. Persistence may be achieved by modifying registry run keys.  
* **Defense Evasion** – Techniques like proxy execution using *rundll32* illustrate how attackers attempt to blend malicious activity with legitimate processes.  
* **Discovery & Lateral Movement** – Tools like *tcpdump* indicate network sniffing, while exploitation of remote services (e.g., SMB/Windows Admin shares) demonstrates how adversaries expand their access.  
* **Collection & Exfiltration Attempts** – Intellectual property hosted in repositories such as *SharePoint* is a likely target. Exfiltration may be attempted through external or multi-hop proxies, though blocking command-and-control connections can prevent data theft.

---
