
<p align="center">
  <img src="assets/ccd-logo.png" alt="Cybersecurity Club DIT Logo" width="145">
</p>

<p align="center">
  <strong>CYBERSECURITY CLUB DIT</strong>
</p>

<h1 align="center">
  <img src="assets/ccd-hackbox-wordmark.svg" alt="CCD_HACKBOX" width="520">
</h1>

<p align="center">
  An intentionally vulnerable Linux environment for authorized cybersecurity training.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Organization-Cybersecurity%20Club%20DIT-8B3DFF?style=flat-square&labelColor=10121C">
  <img src="https://img.shields.io/badge/Platform-Linux-8B3DFF?style=flat-square&labelColor=10121C">
  <img src="https://img.shields.io/badge/Architecture-32--bit-8B3DFF?style=flat-square&labelColor=10121C">
  <img src="https://img.shields.io/badge/Hypervisor-VirtualBox-8B3DFF?style=flat-square&labelColor=10121C">
  <img src="https://img.shields.io/badge/Focus-Linux%20Privilege%20Escalation-8B3DFF?style=flat-square&labelColor=10121C">
  <img src="https://img.shields.io/badge/Status-In%20Development-8B3DFF?style=flat-square&labelColor=10121C">
</p>

---

## Table of Contents

- [Overview](#overview)
- [Project Objectives](#project-objectives)
- [Lab Environment](#lab-environment)
- [Network Architecture](#network-architecture)
- [Linux Privilege Escalation Challenges](#linux-privilege-escalation-challenges)
- [Challenge Learning Areas](#challenge-learning-areas)
- [Getting Started](#getting-started)
- [VirtualBox Network Configuration](#virtualbox-network-configuration)
- [Accessing CCD_HACKBOX Through SSH](#accessing-ccd_hackbox-through-ssh)
- [Student Account and Administrator Access](#student-account-and-administrator-access)
- [Starting the Challenges](#starting-the-challenges)
- [Challenge Methodology](#challenge-methodology)
- [Repository Organization](#repository-organization)
- [Security Guidelines](#security-guidelines)
- [Development Roadmap](#development-roadmap)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)
- [Credits](#credits)

---

## Overview

**CCD_HACKBOX** is an intentionally vulnerable Linux virtual machine developed by **Cybersecurity Club DIT** for practical cybersecurity education.

The project provides a controlled laboratory environment where students can explore Linux security weaknesses, perform system enumeration, identify misconfigurations, and practice privilege escalation techniques.

The initial challenge series focuses on Linux privilege escalation through deliberately misconfigured permissions, executables, scheduled tasks, services, authentication material, network shares, and shared libraries.

CCD_HACKBOX is designed for authorized laboratory use with Kali Linux or another suitable security testing machine.

## Project Objectives

- Provide practical Linux security training.
- Develop system enumeration skills.
- Teach identification of Linux security misconfigurations.
- Demonstrate common privilege escalation techniques.
- Improve penetration testing methodology.
- Encourage ethical hacking and responsible security practices.
- Support hands-on cybersecurity learning at DIT.

## Lab Environment

The current development target uses the following configuration:

| Component | Configuration |
|---|---|
| Hostname | CCD_HACKBOX |
| Operating System | Legacy Ubuntu-based Linux |
| Kernel | Linux 2.6.24-16-server |
| Architecture | i686 (32-bit) |
| Virtualization | Oracle VirtualBox |
| Attacker Machine | Kali Linux |
| Network | VirtualBox Host-only |
| Target IP used during development | 192.168.56.103 |
| Student Username | ccdlabuser |
| Student Starting Privilege | Standard Linux User |

The VM intentionally preserves legacy system components to demonstrate security weaknesses associated with older Linux environments.

Actual IP addresses and configurations may vary between VM snapshots and releases.

## Network Architecture

The laboratory uses a VirtualBox Host-only network to provide communication between Kali Linux and the vulnerable target.

```text
+---------------------------+
|         KALI LINUX        |
|      Attacker Machine     |
|       192.168.56.x        |
+---------------------------+
             |
             |
+---------------------------+
|     HOST-ONLY NETWORK     |
|      192.168.56.0/24      |
+---------------------------+
             |
             |
+---------------------------+
|       CCD_HACKBOX         |
|       Linux Target        |
|      192.168.56.103       |
+---------------------------+
```

The target should remain isolated from production networks and unauthorized external access.

## Linux Privilege Escalation Challenges

The initial practical challenge series contains twelve Linux privilege escalation exercises.

| ID | Challenge | Learning Focus |
|---|---|---|
| PE01 | SUID Binary | SUID permissions and executable behavior |
| PE02 | Credential Discovery | Credential discovery and archived records |
| PE03 | Sudo Misconfiguration | Sudo permissions and privilege boundaries |
| PE04 | Insecure File Permissions | Linux file ownership and permissions |
| PE05 | PATH Hijacking | Executable search path weaknesses |
| PE06 | Cron Job Misconfiguration | Scheduled task security |
| PE07 | Service Misconfiguration | Service execution and permissions |
| PE08 | SSH Key Exposure | SSH authentication material exposure |
| PE09 | NFS Misconfiguration | Network file system permissions |
| PE10 | SUID Execution Handling | SUID environment and execution behavior |
| PE11 | Library Hijacking | Shared library loading weaknesses |
| PE12 | SUID Script Execution Misconfiguration | Unsafe privileged script execution |

**PE12 clarification:** The internal directory is named `PE12-DIRTY-COW`, but the implemented and verified challenge behavior concerns SUID script execution. It should not be presented as a verified Dirty COW exploit.

Challenge implementation, student validation, and release status should be tracked separately.

## Challenge Learning Areas

The current PE series covers:

- Linux users and groups.
- File ownership and permission models.
- SUID executables.
- Sudo configuration.
- Credential discovery.
- Environment variables and executable paths.
- Cron jobs and scheduled execution.
- Service security.
- SSH key handling.
- NFS exports and permissions.
- Shared library loading.
- Privileged script execution.

These exercises help students understand how configuration weaknesses can affect Linux system security.

## Getting Started

### Requirements

- Oracle VirtualBox.
- Kali Linux or another authorized Linux testing machine.
- CCD_HACKBOX virtual machine.
- VirtualBox Host-only network.
- Basic Linux command-line knowledge.
- SSH client installed on the attacker machine.

### Importing the Virtual Machine

When a tested OVA release is published:

1. Download the CCD_HACKBOX OVA from the official GitHub Releases page.
2. Open Oracle VirtualBox.
3. Select **File → Import Appliance**.
4. Choose the downloaded OVA file.
5. Review the virtual machine settings.
6. Complete the import process.
7. Configure the Host-only network.
8. Start CCD_HACKBOX.

An OVA should only be considered officially available after export, testing, and publication.

## VirtualBox Network Configuration

Both Kali Linux and CCD_HACKBOX must use the same Host-only network.

### Configure CCD_HACKBOX

1. Open VirtualBox.
2. Select the CCD_HACKBOX virtual machine.
3. Open **Settings → Network**.
4. Select the appropriate adapter.
5. Enable the network adapter.
6. Choose **Host-only Adapter**.
7. Select the same Host-only network used by Kali Linux.
8. Save the configuration.

### Configure Kali Linux

Configure Kali Linux to use the same Host-only network.

Verify network connectivity before attempting SSH.

The current development network uses:

| Machine | Address |
|---|---|
| Kali Linux | 192.168.56.x |
| CCD_HACKBOX | 192.168.56.103 |
| Network | 192.168.56.0/24 |

The target address may change depending on the VirtualBox configuration.

## Accessing CCD_HACKBOX Through SSH

Students access CCD_HACKBOX remotely from Kali Linux using SSH.

### Student Login Credentials

| Field | Value |
|---|---|
| Username | `ccdlabuser` |
| Password | `ccd123` |
| Host | `192.168.56.103` |
| Access Level | Standard Linux User |

**Important:** These are development laboratory credentials. They should be changed before distributing the VM publicly or to a wider group of students.

### Step 1: Open Kali Linux Terminal

Open a terminal on Kali Linux.

### Step 2: Connect to the Target

The current legacy SSH server requires compatibility with the older RSA host-key algorithm.

Use:

```bash
ssh -o HostKeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa ccdlabuser@192.168.56.103
```

This enables the legacy RSA algorithms for this connection only.

### Step 3: Authenticate

When prompted:

```text
Username: ccdlabuser
Password: ccd123
```

Confirm the host key only after verifying that the target is your CCD_HACKBOX VM.

### Step 4: Verify the Session

After successful authentication, execute:

```bash
whoami
hostname
id
```

Expected username:

```text
ccdlabuser
```

Expected hostname:

```text
CCD_HACKBOX
```

The student should now be connected to the target environment.

## Student Account and Administrator Access

CCD_HACKBOX separates student access from administrator access.

### Student Account

The student account is:

```text
Username: ccdlabuser
Password: ccd123
```

The student account should:

- Be a normal Linux user.
- Have no unrestricted sudo privileges.
- Not belong to privileged administrative groups such as `admin`, `sudo`, or `wheel`.
- Be used for starting privilege escalation challenges.

Verify the account on the target:

```bash
id ccdlabuser
```

The UID should not be `0`.

### Instructor / Administrator Access

The instructor maintains a separate administrative account and root password.

To switch to root:

```bash
su -
```

Enter the root password when prompted.

Alternatively, an administrator account with sudo privileges can use:

```bash
sudo -i
```

**Security distinction:**

| Account | Purpose |
|---|---|
| ccdlabuser | Student challenge access |
| root | Full system administration |
| Instructor account | Authorized VM maintenance |

Do not distribute the root password or instructor credentials in the public repository.

### Important Privilege Separation

Students must not start with unrestricted root access.

The purpose of the lab is to investigate and demonstrate privilege escalation weaknesses from a standard user account.

The instructor should retain administrative access for:

- Installing and maintaining challenges.
- Resetting challenge environments.
- Managing student accounts.
- Reviewing system configuration.
- Preparing VM snapshots.
- Exporting and maintaining the OVA.

## Starting the Challenges

After successfully connecting as `ccdlabuser`, students can begin their assigned exercises.

The challenge directory on the target VM is:

```text
/opt/ccd-hackbox/privesc/challenges/
```

The challenge folders currently used in the development VM are:

```text
/opt/ccd-hackbox/privesc/challenges/
|
+-- PE01-SUID/
+-- PE02-CRON/
+-- PE03-SUDO/
+-- PE04-PATH/
+-- PE05-PATH/
+-- PE06-CRON/
+-- PE07-SERVICE/
+-- PE08-SSH/
+-- PE09-NFS/
+-- PE10-LEGACY/
+-- PE11-LIBRARY/
+-- PE12-DIRTY-COW/
```

### Student Workflow

1. Log in to CCD_HACKBOX using the `ccdlabuser` account.
2. Start with the challenge assigned by your instructor.
3. Inspect the relevant challenge resources.
4. Enumerate the system and identify potential weaknesses.
5. Investigate the identified misconfiguration.
6. Demonstrate its impact within the authorized laboratory.
7. Verify the challenge objective.
8. Document findings and defensive recommendations.
9. Proceed to the next challenge when instructed.

Students should not assume that every challenge uses the same starting account or privilege boundary. Follow the specific instructions provided for each exercise.

### Privilege Escalation Verification

At the beginning of a challenge:

```bash
whoami
id
```

After successfully completing an authorized privilege escalation exercise:

```bash
whoami
id
```

Expected elevated identity:

```text
root
uid=0(root) gid=0(root)
```

The objective is to understand the vulnerability and its impact, not to provide students with unrestricted administrative access from the beginning.

## Challenge Methodology

Each challenge should guide students through a structured security assessment:

1. **Identification:** Understand the assigned challenge and its starting conditions.
2. **Enumeration:** Inspect relevant users, groups, permissions, services, and system configuration.
3. **Analysis:** Identify the security weakness.
4. **Investigation:** Determine how the weakness affects the system.
5. **Demonstration:** Validate the issue within the authorized VM.
6. **Verification:** Confirm whether the challenge objective has been achieved.
7. **Documentation:** Record findings, impact, and defensive recommendations.

The objective is to develop practical security assessment skills rather than simply execute commands without understanding their impact.

## Repository Organization

The public repository is intended to contain:

- Project documentation.
- Student-facing challenge descriptions.
- Public challenge resources.
- Installation and network configuration instructions.
- Screenshots and architecture diagrams.
- Release information.
- Contribution and security guidelines.

The challenge directory structure in the VM is maintained separately from the repository's public documentation structure.

Private instructor walkthroughs, real challenge flags, credentials, private SSH keys, and sensitive configuration must never be committed to the public repository.

## Security Guidelines

CCD_HACKBOX intentionally contains vulnerable configurations.

- Use the VM only in authorized environments.
- Keep the target isolated from production networks.
- Do not expose vulnerable services to the public internet.
- Do not test systems without explicit permission.
- Take VM snapshots before destructive exercises.
- Do not share private keys, passwords, or challenge flags.
- Do not commit sensitive information to public repositories.
- Use the laboratory for education and authorized security testing only.

## Development Roadmap

- [x] Initial CCD_HACKBOX virtual machine development
- [x] Linux privilege escalation challenge series development
- [x] PE01–PE12 challenge implementations
- [x] Initial challenge verification activities
- [ ] Complete student-side validation of all challenges
- [ ] Finalize student-facing challenge documentation
- [ ] Improve challenge reset and verification procedures
- [ ] Complete OVA packaging and testing
- [ ] Publish a stable public release
- [ ] Expand the laboratory with additional security modules

## Contributing

Contributions from Cybersecurity Club DIT members and authorized collaborators are welcome.

Contributors should:

- Follow the existing project structure.
- Test changes in isolated environments.
- Document technical modifications.
- Use reliable technical references.
- Avoid committing credentials, flags, and private materials.
- Follow responsible cybersecurity practices.

## Disclaimer

CCD_HACKBOX is developed exclusively for authorized cybersecurity education and controlled laboratory exercises.

The maintainers do not authorize the use of this environment against systems, networks, accounts, or data without explicit permission.

Users are responsible for complying with applicable laws, institutional policies, and ethical cybersecurity practices.

## Credits

Developed by **CYBERSECURITY CLUB DIT**.

<p align="center">
  <strong>CYBERSECURITY CLUB DIT</strong>
  <br>
  Learn. Practice. Secure.
</p>
