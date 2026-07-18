# Winlog Huntbook

**Detect. Hunt. Respond.**

A self-contained, single-file Windows Event ID reference and multi-platform query builder for threat hunting and incident response. No backend, no dependencies, no data leaves the browser — open the HTML file and go.

[Live demo](https://nawazahmad.github.io/winlog-huntbook/) · Part of a [suite of SOC tools](https://nawazahmad.github.io/)

---

## What it does

Digging through Microsoft's event ID documentation mid-incident is slow. This tool puts the 76 event IDs that actually matter for hunting and IR — across Security, Sysmon, PowerShell, System, Task Scheduler, WMI-Activity, Terminal Services, and Windows Defender logs — in one searchable, filterable reference, with a query builder that turns a selection into ready-to-paste hunt queries.

- **76 event IDs**, each with a plain-English description, the fields worth pivoting on, and mapped ATT&CK techniques
- **Search and filter** by Event ID, keyword, log source, or category (Authentication, Persistence, Privilege Escalation, Defense Evasion, Lateral Movement, and more)
- **30 prebuilt hunt scenario bundles** — one click loads the right cluster of event IDs for a known attack pattern (see below)
- **Multi-platform query builder** — select any combination of event IDs and get generated queries for:
  - Splunk SPL
  - Microsoft Sentinel / KQL (with automatic table routing across SecurityEvent and Event, or force a specific table)
  - Elastic / Lucene-style KQL
  - Tanium / live response filters
- **Export** your selection and generated queries as JSON or Markdown for playbooks, tickets, or SIEM onboarding docs

## Hunt scenario bundles

Instead of remembering which five event IDs matter for a given attack pattern, click a bundle:

| Category | Bundles |
|---|---|
| Credential Access | Kerberoasting, Kerberoasting via SPN Injection, AS-REP Roasting Sweep, LSASS Credential Access, NTDS.dit / Credential Database Theft, Token Theft & Impersonation, Brute Force / Password Spray |
| Persistence | WMI Persistence, Registry-Based Persistence, Scheduled Task Persistence Lifecycle |
| Privilege Escalation | Privilege Escalation via Groups, Rogue Account Creation & Escalation, AD Computer Account & Delegation Abuse, AdminSDHolder & ACL Tampering |
| Lateral Movement | Lateral Movement via SMB, PsExec-Style Service Lateral Movement, RDP Session Hijack |
| Execution & Malware | PowerShell Abuse, PowerShell Session Timeline, Malware Drop & Detonation, Process Injection & Hollowing |
| Command & Control | C2 Beaconing & DNS Tunneling, Network Baseline (No Sysmon) |
| Defense Evasion / Anti-Forensics | Log Tampering / Anti-Forensics, Evidence & Artifact Destruction, Ransomware Precursor |
| Session & Account Activity | Session Lifecycle Timeline, Lockout / Reset Abuse, Sensitive File & Registry Access, Process Lifecycle (No Sysmon) |

Each bundle loads its event IDs straight into the query builder and generates all four query formats immediately.

## Usage

1. Open `index.html` in any modern browser — locally or via the GitHub Pages link above
2. Search or filter to find relevant event IDs, or click a hunt scenario bundle to load a preset
3. Check the event IDs you want (individually or via a bundle)
4. Copy the generated SPL / KQL / Elastic / Tanium query, or export the full selection as JSON or Markdown

No install, no build step, no telemetry.

## Tech

Single HTML file. Vanilla JavaScript, no frameworks or external libraries. Dark terminal aesthetic consistent with the rest of the SOC tools suite.

## Part of the SOC tools suite

This tool follows the same build pattern as the rest of the collection: single-file, client-side only, JSON/Markdown export, no dependencies.

- Hunt Hypothesis Workbench — PEAK framework and ABLE hypothesis structure
- IOC Extractor & Query Generator — multi-platform query generation, CISA KEV enrichment, ATT&CK extraction
- IR Runbook Builder — NIST SP 800-61r2 phases, CSF 2.0 tags
- ATT&CK Kill Chain Playbook
- Tenable × ATT&CK Fusion Board
- BOD 26-04 Remediation Clock — live KEV and Vulnrichment lookups
- ATT&CK Coverage Terrain heatmap
- Security Impact Analysis CM-4 intake tool
- STRIDE-based Threat Hunting Playbook
- **Winlog Huntbook** (this tool)

## License

MIT

---

*Detect. Hunt. Respond.*
