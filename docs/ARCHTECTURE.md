
# CCD_HACKBOX Architecture

## 1. Overview

CCD_HACKBOX is an intentionally vulnerable Linux virtual machine designed for practical cybersecurity training.

The environment provides controlled exercises focused on Linux privilege escalation and system misconfiguration.

## 2. Main Components

### Target Machine

The target machine hosts the intentionally vulnerable Linux environment.

Known environment details:

- Hostname: CCD_HACKBOX
- Architecture: 32-bit i686
- Kernel: 2.6.24-16-server
- Target IP used during development: 192.168.56.103

These values describe the current development environment and may change between releases.

### Attacker Machine

A separate machine, such as Kali Linux, is used by learners to interact with the target during authorized exercises.

### Virtualization

VirtualBox is used to run the target machine in an isolated environment.

### Networking

The recommended development network is a VirtualBox Host-only network.

This allows communication between the attacker and target machines without intentionally exposing vulnerable services to the public internet.

## 3. Challenge Categories

The current privilege escalation series includes:

| ID | Topic |
|---|---|
| PE01 | SUID Binary |
| PE02 | Credential Discovery |
| PE03 | Sudo Misconfiguration |
| PE04 | Insecure File Permissions |
| PE05 | PATH Hijacking |
| PE06 | Cron Job Misconfiguration |
| PE07 | Service Misconfiguration |
| PE08 | SSH Key Exposure |
| PE09 | NFS Misconfiguration |
| PE10 | SUID Environment Handling |
| PE11 | Library Hijacking |
| PE12 | SUID Script Execution Misconfiguration |

## 4. Challenge Execution Model

A typical exercise follows this workflow:

1. The learner connects to the isolated target.
2. The learner enumerates the environment.
3. The learner identifies a system misconfiguration.
4. The learner investigates the relevant security weakness.
5. The learner demonstrates the intended privilege escalation.
6. The learner verifies the result.
7. The environment is reset when required.

## 5. Security Boundaries

The project separates:

- Public student documentation.
- Challenge environment files.
- Instructor-only materials.
- Private credentials and flags.

Private instructor materials must not be included in public releases.

## 6. Future Improvements

Potential improvements include:

- Automated challenge validation.
- Standardized challenge metadata.
- Improved reset mechanisms.
- Additional privilege escalation categories.
- Documented OVA deployment process.
