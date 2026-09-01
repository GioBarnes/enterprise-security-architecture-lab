# Cybersecurity Architecture Home Lab

> This lab was created to simulate a segmented enterprise network for SecureFinance LLC, a fictional 150-persson business I created. It will be designed, implemented, monitored, attacked, and defended with every architectural decision documented in this repository. 

**Status:** IN PROGRESS 🟡



## Table of Contents

- [Purpose](#Purpose)
- [Business Context](#business-context-securefinance-llc)
- [Device Topology](#device-topology)
- [Build Phases](#build-phases)
- [Key Findings & Screenshots](#key-findings--screenshots)
- [Repo Structure](#repo-structure)

## Purpose

The purpose of this project was for me to learn more about and gain hands on experience in cybersecurity architecture concepts. Most home labs stop at installing a SIEM and Active Directory, but this project exists beyond that suface level. By its completion, I hope to answer the question: 

    "Given a real business with a limited budget, and a resource-contrained host, how do you securely design, build, and defend an environment while explaining why you made each decision along the way?"

## Business Context: CYSEN SecureFinance LLC

- **Industry:** Financial Services
- **Size:** ~150 employees
- **Departments:** Executive, Finance, HR, IT, Sales, Security
- **Critical assets:** Active Directory, file server, database, web server, employee workstations, security monitoring infrastructure
- **Primary threats modeled:** Ronsomware, credential theft, phishing, insider threat, web comprimise

## Device Topology

This Project will use three physical devices with one job. These are comprised of old laptops I had lying around that could be repurposed along with my main device. A 4th device will be integrated at a later date.

| Device | Role | Runs |
|---|---|---|
| Lenovo Flex 4 | Lab server (home, always on) | Proxmox VE: Wazuh + AD DC always-on, workstation on-demand |
| CTL Chromebook NL7 | Attacker platform (home, always on) | ChromeOS Linux (Crostini) container running Kali's tools |
| Surface Pro 9 | Access client (travels normally) | Tailscale + SSH client only. This is what I connect from remotely |

## Build Phases

Each phase below will link to its own doc, written up once the phase reaches a working, demonstrable state.

| # | Phase | Status | Write-up |
|---|---|---|---|
| 0 | Repository Setup | ✅  | — |
| A | **Infrastructure:** Proxmox host, Chromebook Crostini node, and Surface Pro all joined to Tailscale | ⬜ | TBD |
| B | **Topology Mapping:** document what's actually connected to what | ⬜ | TBD|
| C | **Detection Platform:** Wazuh manager deployed | ⬜ | TBD |
| D | **Identity:** Active Directory domain controller, OU/group structure | ⬜ | TBD|
| E | **Endpoint Telemetry:** workstation joined, Sysmon + Wazuh agent | ⬜  | TBD |
| F | **Attack Simulation:** first controlled attack executed from Kali | ⬜ | [`attacks/`](attacks/) |
| G | **Detection & Investigation:** alert confirmed, first matrix entry | ⬜ | [`detections/`](detections/) |


## Key Findings & Screenshots
Screenshots that correlate to important steps in the process can be found in the [`screenshots/`](screenshots/) folder. They will me named to match the phase/day they came from. They will also be referenced inline from the relevant phase documentation.

Ex: "day6-password-spray-alert.png"

Logs will be kept as I do day-to-day work on this project, outlining my thought process, wins, mistakes, and remediations found in [`logs/`](logs/) . These will not follow any standard format besides dates and titles, and will instead be a raw view of this project's creation process.

## Repo Structure 

```
enterprise-security-architecture-lab/
├── README.md
├── logs/
├── architecture/
├── identity/
├── security/
├── detections/
├── attacks/
├── compliance/
└── screenshots/
```
