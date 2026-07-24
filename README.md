# Hi, I'm Malathi Mittapalli (Enola) 👋

Aspiring SOC Analyst based in Hyderabad, India — currently job hunting for SOC Analyst / VAPT Analyst roles, with an eye toward eventually moving into threat hunting.

I came out of a 6-month cybersecurity internship (network & packet analysis, IDS/firewall operations, VAPT, web app security, SOC ops, Python/Bash scripting) and decided the fastest way to actually learn this field was to stop reading about SIEMs and IDS tools and just build them myself — break them, fix them, attack them, and document the whole mess honestly. That's what the projects below are.

---

## 🔬 What I've built

### [Living-off-the-Land Ransomware Precursor Detection Lab](https://github.com/malathi-cyber-sketch/Living-off-the-Land-Ransomware-Precursor-Detection-Lab)
Ran a full intrusion against my own Windows 10 box — Nmap recon, Hydra brute force against SMB, persistence through a rogue account/registry key/scheduled task, a couple of LOLBin defense-evasion tricks, and finally `vssadmin delete shadows` — the shadow-copy deletion that's basically every ransomware crew's move right before encryption starts. Wazuh caught pieces of it out of the box, but I wrote a custom correlation rule that fires when multiple precursor techniques land on the same host inside a 5-minute window, instead of leaving an analyst to piece together six separate low-priority alerts. Full attacker-vs-defender SOC response guide included, mapped to MITRE ATT&CK.
`Wazuh` `Docker` `Sysmon` `Nmap` `Hydra` `Detection Engineering` `MITRE ATT&CK` `Custom Correlation Rules`

### [Threat Hunting with Wazuh and Shuffle SOAR](https://github.com/malathi-cyber-sketch/Threat-Hunting-with-Wazuh-and-Shuffle-SOAR)
Follow-up to my Wazuh + Sysmon lab below — that one stopped at "Wazuh raises an alert, I go look." This one closes the loop: alerts get pushed to Shuffle (a self-hosted SOAR platform) over a webhook, which authenticates against the live Wazuh REST API and fires an automated email notification. The official Shuffle-Wazuh integration turned out to reference a dead Docker image, so I built the authentication and webhook path manually with an HTTP node and JWT auth instead of hiding it behind a broken connector. Load-tested with a scripted loop of alerts and validated against real endpoint attack simulation — 213+ hits logged in Wazuh's Threat Hunting view by the end, including a severity-15 detection.
`Wazuh` `Shuffle SOAR` `Docker` `Sysmon` `SOC Automation` `MITRE ATT&CK` `Incident Response`

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

**SIEM / IDS / NSM / SOAR:** Wazuh · Suricata · Zeek · Shuffle · IBM QRadar (CE)
**VAPT:** Nmap · Nikto · OWASP ZAP · OpenVAS/GVM · Metasploit
**Endpoint monitoring:** Sysmon · Windows Event Logs
**Platforms:** Kali Linux · Ubuntu Server · VirtualBox · Docker
**Scripting:** Python · Bash
**Frameworks:** MITRE ATT&CK

## 🎯 What I'm working toward

Every one of these labs exists because I kept running into the same problem in courses and tutorials: you learn to read someone else's alerts, not to build the pipeline that generates them. So I built the pipelines. Deployed the tools, misconfigured them, watched them fail silently, fixed them, and then attacked my own setups to see if they actually caught anything. Some attacks worked, some didn't (I kept the failed ones in the writeups — a null result is still a result).

Next up: working through BTL1 material and practicing on CyberDefenders / Blue Team Labs Online, with the long-term goal of moving from SOC Tier 1 into threat hunting.

## 📫 Reach out

[LinkedIn](https://linkedin.com/in/malathi-mittapalli-enola-b73208413) — happy to connect, especially with anyone hiring for SOC/VAPT roles or working on similar home lab projects. Feedback on any of the above is always welcome — still learning, and I'd rather know what I got wrong now than later.
