
<p align="center">
  <img src="assets/ccd-logo.png" alt="Official Cybersecurity Club DIT logo" width="168" />
</p>

<p align="center">
  <strong>CYBERSECURITY CLUB DIT</strong>
</p>

<h1 align="center">
  <img src="assets/ccd-hackbox-wordmark.svg" alt="CCD_HACKBOX" width="520" />
</h1>

<p align="center">
  An intentionally vulnerable Linux virtual machine for authorized cybersecurity training.
</p>

<p align="center">
  <img alt="Club: Cybersecurity DIT" src="https://img.shields.io/badge/Club-Cybersecurity%20DIT-8B3DFF?style=flat-square&labelColor=10121C" />
  <img alt="Product: CCD_HACKBOX" src="https://img.shields.io/badge/Product-CCD__HACKBOX-8B3DFF?style=flat-square&labelColor=10121C" />
  <img alt="Platform: Linux" src="https://img.shields.io/badge/Platform-Linux-8B3DFF?style=flat-square&labelColor=10121C" />
  <img alt="Use: Authorized Lab" src="https://img.shields.io/badge/Use-Authorized%20Lab-8B3DFF?style=flat-square&labelColor=10121C" />
  <img alt="Status: In Development" src="https://img.shields.io/badge/Status-In%20Development-8B3DFF?style=flat-square&labelColor=10121C" />
</p>

<p align="center">
  <img src="assets/ccd-hackbox-ova.svg" alt="CCD_HACKBOX virtual machine package illustration" width="720" />
</p>

---

## Documentation

- [Overview](#overview)
- [Objectives](#objectives)
- [Product Architecture](#product-architecture)
- [Learning Modules](#learning-modules)
- [Installation](#installation)
- [Network Configuration](#network-configuration)
- [Repository Structure](#repository-structure)
- [Screenshots](#screenshots)
- [Security and Lab Boundaries](#security-and-lab-boundaries)
- [Project Status](#project-status)
- [Brand and Credits](#brand)

---

## Overview

CCD_HACKBOX is an intentionally vulnerable Linux virtual machine developed for the Cybersecurity Club DIT.

The project provides a controlled environment where students and cybersecurity enthusiasts can develop practical skills through hands-on security exercises.

It is designed to support learning in network security, web application security, service enumeration, vulnerability assessment, exploitation fundamentals, and Linux privilege escalation.

The appliance is intended for authorized training, supervised exercises, and isolated cybersecurity labs.

## Objectives

- Provide a practical environment for cybersecurity education.
- Help students understand common Linux and network security weaknesses.
- Develop penetration testing and vulnerability assessment skills.
- Provide realistic exercises based on documented security vulnerabilities.
- Encourage responsible disclosure and ethical security practices.
- Support collaborative cybersecurity training within CYBERSECURITY CLUB DIT.

## Product Architecture

CCD_HACKBOX is designed as a Linux virtual machine distributed in Open Virtualization Format (OVA).

The intended lab environment consists of:

| Component | Role |
|---|---|
| Kali Linux | Attacker and testing machine |
| Ubuntu Server | CCD_HACKBOX vulnerable target |
| VirtualBox | Virtualization platform |
| Host-only Network | Isolated communication between lab machines |
| CCD_HACKBOX OVA | Portable virtual appliance for distribution |

<p align="center">
  <img src="assets/diagrams/network-topology.png" alt="CCD_HACKBOX network topology" width="760" />
</p>

## Learning Modules

The project is organized into the following training areas:

| Module | Learning Area |
|---|---|
| Network Security | Reconnaissance, port scanning and enumeration |
| Web Security | Common web application vulnerabilities |
| FTP Security | FTP service weaknesses and misconfigurations |
| SSH Security | SSH configuration and authentication weaknesses |
| Database Security | Database enumeration and access control |
| Linux Privilege Escalation | Linux permissions, SUID, sudo and capabilities |
| CVE Labs | Practical exercises based on verified CVEs |

**Note:** Module availability depends on implementation and testing status. Planned exercises are not necessarily available in the current VM.

## Installation

The final appliance is intended to be distributed as:

`CCD_HACKBOX.ova`

Once a tested release is published:

1. Download the OVA from the project's GitHub Releases.
2. Open Oracle VirtualBox.
3. Select **File → Import Appliance**.
4. Select the downloaded OVA.
5. Review the virtual machine settings.
6. Configure an isolated Host-only network.
7. Start the virtual machine.

Do not import or run an untrusted appliance on a production network.

## Network Configuration

The recommended lab topology is:

```text
Kali Linux
    |
    |
Host-only Network
    |
    |
CCD_HACKBOX
(Ubuntu Server)
```

Recommended configuration:

- Use a VirtualBox Host-only Adapter for the lab.
- Keep the vulnerable target isolated from production networks.
- Use NAT temporarily only when internet access is needed for controlled updates.
- Do not use Bridged Networking for the vulnerable appliance.
- Do not expose vulnerable services to the public internet.

## Repository Structure

```text
CCD_HACKBOX/
│
├── assets/              # Branding, screenshots and diagrams
├── docs/                # Project and installation documentation
├── config/              # Service and system configurations
├── scripts/             # Setup, verification and reset scripts
├── modules/             # Cybersecurity learning modules
├── challenges/          # Practical training challenges
├── flags/               # Flag management documentation
├── hints/               # Challenge hints
├── walkthroughs/        # Learning walkthroughs
├── instructor-private/  # Private instructor resources
├── releases/            # Release documentation
│
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── SECURITY.md
└── .gitignore
```

## Screenshots

Screenshots will document the actual appliance and its practical exercises.

<p align="center">
  <img src="assets/screenshots/ubuntu-server.png" alt="Ubuntu Server environment" width="720" />
</p>

<p align="center">
  <em>Ubuntu Server environment — replace with an actual project screenshot.</em>
</p>

<p align="center">
  <img src="assets/screenshots/nmap-scan.png" alt="Network enumeration demonstration" width="720" />
</p>

<p align="center">
  <em>Network enumeration — replace with an actual lab screenshot.</em>
</p>

## Security and Lab Boundaries

CCD_HACKBOX intentionally contains vulnerable services and configurations.

Users must follow these rules:

- Use the appliance only for authorized cybersecurity training.
- Run it within an isolated virtual lab.
- Never connect it directly to production networks.
- Never expose intentionally vulnerable services to the public internet.
- Do not target systems, accounts, or data without permission.
- Keep private flags, credentials and instructor-only materials out of the public repository.
- Take snapshots before performing potentially destructive exercises.

## Project Status

CCD_HACKBOX is under active development.

The project will progress through:

- [x] Initial repository structure
- [x] Core documentation structure
- [ ] Ubuntu Server lab configuration
- [ ] Vulnerable service deployment
- [ ] Practical challenge implementation
- [ ] Challenge verification and testing
- [ ] OVA packaging and validation
- [ ] Public release

Only completed and tested components should be marked as available.

## Brand and Credits

CCD_HACKBOX is developed under Cybersecurity Club DIT.

The official club logo is retained in its original form and proportions. The product uses a purple-on-near-black visual identity.

| File | Role |
|---|---|
| `assets/ccd-logo.png` | Official club logo |
| `assets/ccd-logo.jpeg` | Original supplied logo file |
| `assets/ccd-hackbox-wordmark.svg` | CCD_HACKBOX wordmark |
| `assets/ccd-hackbox-ova.svg` | Appliance package illustration |

**Developed for cybersecurity education by CYBERSECURITY CLUB DIT.**

<p align="center">
  <strong>Learn. Practice. Secure.</strong>
</p>
