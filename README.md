<p align="center">
  <img src="assets/ccd-logo.png" alt="Official Cybersecurity Club DIT logo" width="150">
</p>

<p align="center">
  <strong>CYBERSECURITY CLUB DIT</strong>
</p>

<h1 align="center">
  <img src="assets/ccd-hackbox-wordmark.svg" alt="CCD_HACKBOX" width="520">
</h1>

<p align="center">
  An intentionally vulnerable Linux virtual machine for authorized cybersecurity training.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Organization-Cybersecurity%20Club%20DIT-8B3DFF?style=flat-square&labelColor=10121C" alt="Organization">
  <img src="https://img.shields.io/badge/Platform-Ubuntu%20Server-8B3DFF?style=flat-square&labelColor=10121C" alt="Platform">
  <img src="https://img.shields.io/badge/Hypervisor-VirtualBox-8B3DFF?style=flat-square&labelColor=10121C" alt="Hypervisor">
  <img src="https://img.shields.io/badge/Use-Authorized%20Training-8B3DFF?style=flat-square&labelColor=10121C" alt="Authorized Training">
  <img src="https://img.shields.io/badge/Status-In%20Development-8B3DFF?style=flat-square&labelColor=10121C" alt="Development Status">
</p>

<p align="center">
  <img src="assets/ccd-hackbox-ova.svg" alt="CCD_HACKBOX virtual appliance illustration" width="680">
</p>

---

## Table of Contents

- [Overview](#overview)
- [Project Objectives](#project-objectives)
- [System Architecture](#system-architecture)
- [Learning Modules](#learning-modules)
- [Current Lab Status](#current-lab-status)
- [Lab Environment](#lab-environment)
- [Getting Started](#getting-started)
- [Network Configuration](#network-configuration)
- [Repository Structure](#repository-structure)
- [Challenge Framework](#challenge-framework)
- [Security Guidelines](#security-guidelines)
- [Project Roadmap](#project-roadmap)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)
- [Credits](#credits)

---

## Overview

**CCD_HACKBOX** is an intentionally vulnerable Linux virtual machine developed by **Cybersecurity Club DIT** for practical cybersecurity education.

It provides a controlled environment in which students can investigate common security weaknesses, understand how vulnerabilities affect Linux systems and services, and practice penetration-testing techniques in an authorized lab.

The project is being developed around a portable virtual-machine environment, with structured exercises covering Linux privilege escalation, service security, network security, web application security, and other practical cybersecurity topics.

The goal is to make hands-on cybersecurity training more accessible through repeatable labs, clear learning objectives, and documented challenge workflows.

## Project Objectives

- Provide a practical environment for cybersecurity education.
- Develop hands-on penetration-testing and vulnerability-assessment skills.
- Demonstrate common Linux and network-service misconfigurations.
- Help students understand how security weaknesses can be identified and mitigated.
- Provide structured challenges for different experience levels.
- Promote ethical hacking and responsible security practices.
- Support collaborative cybersecurity learning within Cybersecurity Club DIT.

## System Architecture

CCD_HACKBOX runs as a virtual machine and is designed to be tested from a separate attacker machine.

| Component | Purpose |
|---|---|
| Kali Linux | Attacker and security-testing machine |
| CCD_HACKBOX | Intentionally vulnerable Linux target |
| Oracle VirtualBox | Virtualization platform |
| Host-only Network | Isolated communication between lab machines |
| OVA Appliance | Planned portable distribution format |

### Network Architecture

```text
+----------------------+
|      Kali Linux      |
|   Attacker Machine   |
+----------------------+
           |
           |
+----------------------+
|   Host-only Network  |
|   Isolated Lab LAN   |
+----------------------+
           |
           |
+----------------------+
|     CCD_HACKBOX      |
|   Linux Target VM    |
+----------------------+
```

The lab is intended to operate independently of production networks and public-facing infrastructure.

## Learning Modules

The planned learning areas include:

| Module | Description |
|---|---|
| Network Security | Network discovery, port scanning, and service enumeration |
| Web Security | Common web-application vulnerabilities |
| FTP Security | FTP enumeration and service misconfigurations |
| SSH Security | SSH configuration and authentication weaknesses |
| Database Security | Database enumeration and access-control weaknesses |
| Linux Privilege Escalation | Linux permissions, SUID, sudo, cron, PATH, and related techniques |
| Vulnerability Research | Understanding and safely reproducing selected, verified vulnerabilities |

Module availability depends on implementation and testing progress. A topic listed here is not necessarily available in the current VM build.

## Current Lab Status

The current development effort has focused on Linux privilege-escalation exercises.

| Challenge range | Focus |
|---|---|
| PE01–PE11 | Foundational Linux privilege-escalation techniques and misconfigurations |
| PE12 | SUID script-execution misconfiguration |

Challenge names, objectives, and techniques should be confirmed against the corresponding student-facing challenge documentation. Only challenges that have been tested from the intended student account should be described as verified.

Other learning modules remain planned or under development. The project does not currently claim that every module listed in this README is implemented.

## Lab Environment

The recommended environment consists of:

- Kali Linux as the testing machine.
- CCD_HACKBOX as the vulnerable target.
- Oracle VirtualBox for virtualization.
- A dedicated Host-only network for communication.
- Sufficient memory and storage for both virtual machines.

Exact CPU, memory, and storage recommendations will be published after the appliance has been packaged and tested.

## Getting Started

### Option 1: Import the OVA Appliance

The intended distribution format is:

```text
CCD_HACKBOX.ova
```

The OVA should be downloaded from the project's GitHub Releases once a tested release has been published.

1. Download the OVA release asset.
2. Open Oracle VirtualBox.
3. Select **File → Import Appliance**.
4. Choose the downloaded `CCD_HACKBOX.ova`.
5. Review the virtual-machine configuration.
6. Configure the recommended isolated network.
7. Start the virtual machine and follow the student guide.

> **Release status:** The OVA is not considered available until a tested appliance has been uploaded to GitHub Releases. Do not treat this repository's source files as a ready-to-import appliance.

### Option 2: Build or Install from Source

An automated installation method may be provided for users who want to configure the lab from a clean Linux installation. Follow the deployment documentation when that process is available and tested.

## Network Configuration

A dedicated VirtualBox Host-only network is recommended.

- Use a VirtualBox Host-only Adapter for attacker-to-target communication.
- Keep the vulnerable target isolated from production and personal networks.
- Use NAT only when temporary internet access is required for controlled maintenance.
- Disconnect temporary NAT access before student exercises.
- Avoid Bridged Networking.
- Never expose vulnerable services directly to the public internet.

## Repository Structure

The public repository should contain student-facing documentation, challenge materials, safe setup scripts, and project assets.

```text
CCD_HACKBOX/
│
├── assets/
│   ├── branding/
│   ├── screenshots/
│   ├── diagrams/
│   └── banners/
│
├── docs/
│   ├── deployment/
│   ├── architecture/
│   ├── INSTALLATION.md
│   ├── NETWORK-SETUP.md
│   ├── STUDENT-GUIDE.md
│   └── PRIVILEGE-ESCALATION.md
│
├── config/
│   ├── network/
│   ├── services/
│   └── system/
│
├── scripts/
│   ├── setup/
│   ├── verification/
│   ├── reset/
│   └── utilities/
│
├── modules/
│   ├── network-security/
│   ├── web-security/
│   ├── ftp-security/
│   ├── ssh-security/
│   ├── database-security/
│   └── linux-privesc/
│
├── challenges/
│   ├── linux-privesc/
│   ├── network-security/
│   └── web-security/
│
├── hints/
├── releases/
│
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── LICENSE
└── .gitignore
```

**Private instructor materials must be stored separately from the public repository.** This includes real flags, answer keys, full walkthroughs, credentials, private keys, and backups. A `.gitignore` file helps prevent accidental additions, but it does not remove files that are already tracked by Git.

## Challenge Framework

Challenges should be organized by module and difficulty. A typical student-facing challenge directory may contain:

```text
challenge-name/
├── README.md
├── objectives.md
├── hints.md
├── references.md
├── setup.sh
└── verify.sh
```

Each challenge should document:

- Learning objectives and prerequisites.
- The lab account or starting point.
- The task and expected outcome.
- Safe setup and reset instructions, where applicable.
- A verification method that does not disclose the solution.
- Relevant technical references.

Instructor solutions and real flag values belong in a separate private instructor repository or another access-controlled location.

## Security Guidelines

CCD_HACKBOX intentionally contains vulnerable components. To use it responsibly:

1. Run it only in an authorized training environment.
2. Use an isolated virtual network.
3. Never connect vulnerable services to production infrastructure.
4. Do not expose the appliance to the public internet.
5. Do not test systems or networks without explicit authorization.
6. Take VM snapshots before potentially destructive exercises.
7. Keep credentials, private flags, private keys, and instructor walkthroughs out of public repositories.
8. Revert or rebuild the lab after exercises if its state has been changed.

## Project Roadmap

CCD_HACKBOX is under active development. The roadmap below distinguishes project goals from completed deliverables.

- [x] Initial repository creation
- [x] Initial project documentation framework
- [x] Initial Linux privilege-escalation challenge development
- [ ] Complete student-side verification of all PE challenges
- [ ] Finalize public challenge documentation
- [ ] Validate network and service configurations
- [ ] Implement network-security challenges
- [ ] Implement web-security challenges
- [ ] Implement FTP and SSH challenges
- [ ] Implement database-security challenges
- [ ] Add verified vulnerability-research exercises
- [ ] Add automated challenge verification and reset procedures
- [ ] Build and test the OVA appliance
- [ ] Publish a documented public release

A checkbox should be marked complete only after the corresponding deliverable has been implemented and tested.

## Contributing

Contributions are welcome from club members and collaborators interested in cybersecurity education.

Before contributing:

- Review the project documentation.
- Follow the repository structure.
- Use reliable and verifiable technical references.
- Document changes and dependencies.
- Test scripts and configurations in an isolated environment.
- Never submit real credentials, private flags, instructor walkthroughs, or unauthorized data.

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

## Disclaimer

CCD_HACKBOX is developed exclusively for authorized cybersecurity education and controlled laboratory exercises.

The project maintainers do not authorize use of this appliance against systems, networks, accounts, or data without explicit permission. Users are responsible for complying with applicable laws, institutional policies, and ethical cybersecurity practices.

## Credits

Developed by **CYBERSECURITY CLUB DIT**.

The official club logo should be used in its original form and proportions.

### Visual Identity

| Element | Value |
|---|---|
| Background | `#08080D` |
| Surface | `#10121C` |
| Primary | `#8B3DFF` |
| Text | `#FFFFFF` |
| Secondary text | `#A0A0B0` |

<p align="center">
  <strong>CYBERSECURITY CLUB DIT</strong>
</p>

<p align="center">
  Learn. Practice. Secure.
</p>
