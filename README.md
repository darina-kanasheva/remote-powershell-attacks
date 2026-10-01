# Remote PowerShell Attacks via WinRM

This repository contains our weekly Cyber Threat Intelligence course project. We study how PowerShell Remoting via WinRM can be abused and how such activity can be investigated using public sources, MISP, and attack-analysis frameworks.

## Group Members

- Darina Kanasheva
- Aruzhan Abdulina

## Project Focus

Our project focuses on two MITRE ATT&CK sub-techniques:

- **T1059.001 — PowerShell:** execution of commands and scripts.
- **T1021.006 — Windows Remote Management:** remote access used for lateral movement.

PowerShell and WinRM are legitimate administration technologies. Their use alone does not prove malicious activity. Analysis requires context about the account, source host, target system, and executed commands.

## Weekly Reports

### Week 1 — Cyber Threat Intelligence Fundamentals

Defined project-specific terms, classified threats and their sources, and introduced the relevant MITRE ATT&CK techniques.

### Week 2 — OSINT Data Collection and Data Source Mapping

Used Shodan, MalwareBazaar, VirusTotal, and Maltego to collect and examine public information. Created a data source mapping table documenting each source’s contribution.

### Week 3 — Data Processing and Exploitation

Deployed a local MISP instance using Docker Compose. Manually filtered and normalized the findings and created an unpublished event containing one SHA-256 hash and three reference links.

### Week 4 — Cyber Kill Chain Analysis

Analyzed Storm-0501 activity using the seven stages of the Cyber Kill Chain. Compared the model with MITRE ATT&CK and proposed detection and prevention measures.

The weekly reports include supporting screenshots and source information.

## Key Findings and Limitations

- An exposed WinRM service indicates an attack surface, not confirmed compromise.
- In the examined 2025 Storm-0501 campaign, Evil-WinRM supported lateral movement after domain administrator privileges had already been obtained. It was not the initial-access method.
- The Embargo-family sample examined in Week 2 has no confirmed connection to Storm-0501.
- The Week 3 MISP event remains unpublished. Its reference links provide context and are not malicious indicators.
- IP addresses without sufficient evidence of malicious activity were excluded as malicious indicators.
- The Week 4 analysis combines information from the 2024 and 2025 campaigns rather than reconstructing one complete incident.
- Port 5985 uses HTTP, but this does not automatically mean PowerShell commands are transmitted without encryption. WinRM can use message-level encryption with Kerberos or NTLM.

These clarifications guide the interpretation of earlier wording in the Week 2 report.

## References

- [MITRE ATT&CK: PowerShell — T1059.001](https://attack.mitre.org/techniques/T1059/001/)
- [MITRE ATT&CK: Windows Remote Management — T1021.006](https://attack.mitre.org/techniques/T1021/006/)
- [MITRE ATT&CK: Storm-0501 — G1053](https://attack.mitre.org/groups/G1053/)
- [Microsoft Learn: Security Considerations for PowerShell Remoting Using WinRM](https://learn.microsoft.com/en-us/powershell/scripting/security/remoting/winrm-security)
- [Microsoft Threat Intelligence: Storm-0501 — Ransomware Attacks Expanding to Hybrid Cloud Environments, September 2024](https://www.microsoft.com/en-us/security/blog/2024/09/26/storm-0501-ransomware-attacks-expanding-to-hybrid-cloud-environments/)
- [Microsoft Threat Intelligence: Storm-0501’s Evolving Techniques Lead to Cloud-Based Ransomware, August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## AI Usage

We used ChatGPT as an assistant while preparing the project materials:

- **Week 1 — Cyber Threat Intelligence Fundamentals:** helped draft explanations of terms related to PowerShell Remoting and WinRM and improve the English wording of the threat classification.
- **Week 2 — OSINT Data Collection and Data Source Mapping:** helped plan open-source searches.
- **Week 3 — Data Processing and Exploitation:** helped understand how to document the MISP import.
- **Week 4 — Cyber Kill Chain Analysis:** ChatGPT helped improve the English wording of the analysis.

AI-generated explanations are not treated as evidence of malicious activity or campaign attribution. The reports document the sources and limitations of the collected findings.
