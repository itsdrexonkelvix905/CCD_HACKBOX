
# CCD_HACKBOX

<p align="center">
  <strong>An Intentionally Vulnerable Linux Training Environment</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-orange">
  <img src="https://img.shields.io/badge/Hypervisor-VirtualBox-blue">
  <img src="https://img.shields.io/badge/Category-Cybersecurity-red">
  <img src="https://img.shields.io/badge/Status-In%20Development-yellow">
</p>

## About

**CCD_HACKBOX** is an intentionally vulnerable Linux virtual machine designed for practical cybersecurity education and authorized penetration testing.

The project provides a controlled environment where students, cybersecurity enthusiasts, and security practitioners can explore vulnerabilities, practice exploitation techniques, perform security assessments, and develop Linux privilege escalation skills.

The platform is designed to provide hands-on experience with real-world security concepts in an isolated laboratory environment.

## Objectives

- Provide practical penetration testing experience.
- Understand network services and their security weaknesses.
- Practice vulnerability discovery and exploitation.
- Explore web application security vulnerabilities.
- Learn Linux enumeration and privilege escalation.
- Understand CVEs and software security misconfigurations.
- Develop practical offensive security skills.

## Planned Modules

| Module | Description |
|---|---|
| Network Security | Network discovery, scanning and service enumeration |
| Web Security | Web application vulnerabilities and exploitation |
| FTP Security | FTP configuration and security weaknesses |
| SSH Security | Authentication and SSH misconfigurations |
| Database Security | Database exposure and access control |
| Linux PrivEsc | Linux privilege escalation techniques |
| CVE Labs | Practical vulnerability research and CVE-based exercises |
| Capture The Flag | Flags, challenges and learning objectives |

## Technology Stack

- Ubuntu Server
- Oracle VirtualBox
- Apache HTTP Server
- PHP
- MySQL / PostgreSQL
- OpenSSH
- Samba
- Additional vulnerable applications and services

*The final technology stack will depend on the implemented modules.*

## Lab Environment

The recommended environment consists of:

- Attacker Machine: Kali Linux
- Target Machine: CCD_HACKBOX
- Hypervisor: Oracle VirtualBox
- Network: Host-only Adapter

The isolated network allows students to perform security testing without exposing intentionally vulnerable services to external networks.

## Installation

1. Download the latest CCD_HACKBOX OVA from GitHub Releases.
2. Open Oracle VirtualBox.
3. Select **File → Import Appliance**.
4. Select the downloaded OVA file.
5. Configure the recommended network settings.
6. Start the virtual machine.

Refer to the installation documentation for detailed instructions.

## Project Structure

```text
CCD_HACKBOX/
├── docs/
├── scripts/
├── challenges/
│   ├── beginner/
│   ├── intermediate/
│   ├── advanced/
│   └── expert/
├── modules/
├── releases/
├── README.md
└── LICENSE
```

## Security Notice

CCD_HACKBOX is intentionally designed to contain vulnerable services and applications for educational purposes.

- Run it only in an isolated laboratory.
- Do not expose vulnerable services to public networks.
- Do not deploy it on production infrastructure.
- Perform testing only against systems you are authorized to assess.

## Project Status

**Currently in development.**

Modules, challenges, vulnerability configurations, and documentation are being developed and tested.

## Author

**CYBER CLUB DIT (CCD)**

Cybersecurity Education | Ethical Hacking | Offensive Security

## Disclaimer

This project is intended strictly for educational purposes and authorized security testing.

The developers are not responsible for misuse or unauthorized activities involving this software.
