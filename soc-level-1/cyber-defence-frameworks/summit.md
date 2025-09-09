---
layout: default
title: Summit – Malware Detection and Threat Simulation
---

In this lab, the focus was on **malware detection and threat simulation** using a purple-team approach. The scenario was based on **PicoSecure**, which initiated a detection engineering exercise after multiple incident response activities. Together with an external penetration tester, malware behavior was analyzed on a simulated internal workstation, and security tools were configured to detect and block malicious actions, following the **Pyramid of Pain** to prioritize adversary indicators.

---

### Sample 1: Hash Blocking
Scanned `sample1.exe` in the **Malware Sandbox** to inspect behavior. After reviewing the report, the **MD5 hash** of the file was selected and blocked in the **Manage Hashes** section.

![Malware report](./images/sample1-1.png)  
![Hash block success](./images/sample1-2.png)

---

### Sample 2: IP Blocking
Analysis of `sample2.exe` showed suspicious network activity, including HTTP requests and multiple TCP/UDP connections to the command-and-control server at IP `154.35.10.113` (Intrabuzz Hosting Limited).  

A firewall rule was created in the **Firewall Rule Manager** to deny all outbound connections to that IP, successfully preventing communication with the server and mitigating the threat.

![Malware report](./images/sample2-1.png)  
![Firewall rule success](./images/sample2-2.png)

---

### Sample 3: Domain Blocking
The report for `sample3.exe` indicated multiple HTTP requests, TCP/UDP connections, and DNS queries to the malicious domain `emudyn.bresonicz.info` (XplorIta Cloud Services).  

A **DNS filter rule** was configured in the **DNS Rule Manager**, categorizing it as **Malware** and denying all queries to this domain, which blocked communication with the C2 server.

![Malware report](./images/sample3-1.png)  
![DNS rule success](./images/sample3-2.png)

---

### Sample 4: Registry Modification Blocking
The analysis of `sample4.exe` showed attempts to modify the Windows Registry to disable real-time protection in Windows Defender.  

A **Registry rule** was created to monitor and block unauthorized modifications to the key:

`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Real-Time Protection`  

This prevented system alterations and mitigated the threat.  

**MITRE ATT&CK ID:** `Defense Evasion (TA0005)`  

![Malware report](./images/sample4-1.png)  
![Registry rule attempt](./images/sample4-2.png)  
![Registry rule success](./images/sample4-3.png)

---

### Sample 5: Beaconing Detection
The report for `sample5.exe` revealed repeated HTTP requests and TCP/UDP connections to the malicious domain `bababa10la.cn` (XplorIta Cloud Services). The malware sent small beaconing payloads every 30 minutes to maintain C2 communication.  

A **Sigma network detection rule** was configured in the **Network Rule Manager** to detect connections with size 97 bytes occurring every 1800 seconds. This successfully disrupted beaconing activity.

![Malware report](./images/sample5-1.png)  
![Beaconing traffic](./images/sample5-2.png)  
![Sigma rule](./images/sample5-3.png)  
![Network rule success](./images/sample5-4.png)

---

### Sample 6: File Exfiltration Blocking
The report for `sample6.exe` showed creation of a text file named `exfiltr8.log` in the `%temp%` directory, containing system and network information.  

A **File Creation/Modification rule** was added in the **File Rule Manager** to monitor and block creation of any file named `exfiltr8.log` in the `%temp%` folder. This prevented local storage of sensitive data.  

**MITRE ATT&CK ID:** `Collection (TA0009)`  

![Malware report](./images/sample6-1.png)  
![File creation detected](./images/sample6-2.png)  
![Blocking rule applied](./images/sample6-3.png)  
![File rule success](./images/sample6-4.png)

---

### Final Overview
The lab demonstrated how multiple **defense strategies** can be applied to detect, block, and mitigate malware behavior at different stages of the attack lifecycle.

![Final summary](./images/sample-final.png)

---
