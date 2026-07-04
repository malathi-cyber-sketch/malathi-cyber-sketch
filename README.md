# Hi, I'm Malathi Mittapalli (Enola) 👋

Aspiring SOC Analyst based in Hyderabad, India — currently job hunting for SOC Analyst / VAPT Analyst roles, with an eye toward eventually moving into threat hunting.

I came out of a 6-month cybersecurity internship (network & packet analysis, IDS/firewall operations, VAPT, web app security, SOC ops, Python/Bash scripting) and decided the fastest way to actually learn this field was to stop reading about SIEMs and IDS tools and just build them myself — break them, fix them, attack them, and document the whole mess honestly. That's what the three projects below are.

---

## 🔬 What I've built

### [Wazuh + Sysmon SIEM Home Lab](https://github.com/malathi-cyber-sketch/wazuh-sysmon-siem-home-lab)
Wazuh manager deployed via Docker on Kali, Windows 10 endpoint wired up with Sysmon, then attacked my own setup with Hydra and Nmap to see what would actually get flagged. Alerts mapped to MITRE ATT&CK (T1105, T1059, T1087). Includes a CIS benchmark compliance scan and a full log of what broke along the way — including the step that silently drops most Sysmon telemetry if you skip it.

`Wazuh` `Docker` `Sysmon` `Hydra` `Nmap` `MITRE ATT&CK`

### [SOC Home Lab — Network Threat Detection with Suricata & Zeek](https://github.com/malathi-cyber-sketch/SOC-Home-Lab-Network-Threat-Detection-with-Suricata-Zeek)
Three-machine lab (Kali attacker, Ubuntu sensor, Windows 10 target) running Suricata and Zeek side by side to compare signature-based detection against behavioral network monitoring. 7 distinct Suricata alert signatures fired across a single attack sequence — including one where the attacker's own hostname leaked in a DHCP broadcast before the first scan even started.

`Suricata` `Zeek` `Nmap` `MITRE ATT&CK` `Network Security Monitoring`

### [VAPT Home Lab — Metasploitable2](https://github.com/malathi-cyber-sketch/vapt-home-lab-metasploitable2)
Full vulnerability assessment of Metasploitable2 using Nmap, Nikto, OWASP ZAP, and OpenVAS/GVM in an isolated VirtualBox environment. CVEs identified and mapped to OWASP categories, with a consolidated findings table across all four tools.

`Nmap` `Nikto` `OWASP ZAP` `OpenVAS/GVM` `Kali Linux` `Vulnerability Assessment`

---

## 🧰 Tools & tech I work with

**SIEM / IDS / NSM:** Wazuh · Suricata · Zeek · IBM QRadar (CE)
**VAPT:** Nmap · Nikto · OWASP ZAP · OpenVAS/GVM · Metasploit
**Endpoint monitoring:** Sysmon · Windows Event Logs
**Platforms:** Kali Linux · Ubuntu Server · VirtualBox
**Scripting:** Python · Bash
**Frameworks:** MITRE ATT&CK

## 🎯 What I'm working toward

Every one of these labs exists because I kept running into the same problem in courses and tutorials: you learn to read someone else's alerts, not to build the pipeline that generates them. So I built the pipelines. Deployed the tools, misconfigured them, watched them fail silently, fixed them, and then attacked my own setups to see if they actually caught anything. Some attacks worked, some didn't (I kept the failed ones in the writeups — a null result is still a result).

Next up: working through BTL1 material and practicing on CyberDefenders / Blue Team Labs Online, with the long-term goal of moving from SOC Tier 1 into threat hunting.

## 📫 Reach out

[LinkedIn](https://linkedin.com/in/malathi-mittapalli-enola-b73208413) — happy to connect, especially with anyone hiring for SOC/VAPT roles or working on similar home lab projects. Feedback on any of the above is always welcome — still learning, and I'd rather know what I got wrong now than later.
