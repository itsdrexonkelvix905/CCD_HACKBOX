cat > challenges/README.md <<'EOF'
# CCD HACKBOX — Privilege Escalation Challenges

Welcome to the CCD HACKBOX Privilege Escalation Lab.

This directory contains 12 intentionally vulnerable Linux challenges designed for cybersecurity training. Each challenge introduces a different Linux security weakness and provides an opportunity to investigate, understand, and document the vulnerability.

## Lab Objectives

- Understand common Linux privilege escalation vulnerabilities.
- Identify insecure permissions and configurations.
- Investigate SUID binaries and sudo rules.
- Understand cron jobs, services, PATH handling, and shared libraries.
- Practice SSH key security and NFS configuration analysis.
- Develop enumeration, exploitation, and reporting skills.

## Challenge List

| ID | Challenge | Topic | Learning Objective |
|---|---|---|---|
| PE01 | SUID | SUID Misconfiguration | Identify and investigate insecure SUID binaries. |
| PE02 | CRON | Credential Discovery | Investigate exposed information in scheduled-task files and application records. |
| PE03 | SUDO | Sudo Misconfiguration | Examine sudo permissions and identify dangerous command privileges. |
| PE04 | PATH | Insecure File Permissions | Investigate writable scripts and unsafe execution permissions. |
| PE05 | PATH | PATH Hijacking | Understand how an unsafe PATH environment can affect command execution. |
| PE06 | CRON | Cron Job Misconfiguration | Investigate scheduled tasks and their permissions. |
| PE07 | SERVICE | Service Misconfiguration | Examine service scripts, execution privileges, and writable tasks. |
| PE08 | SSH | SSH Key Exposure | Investigate exposed SSH credentials and insecure key storage. |
| PE09 | NFS | NFS Misconfiguration | Examine NFS exports and their security implications. |
| PE10 | LEGACY | Legacy SUID Environment Handling | Investigate unsafe environment handling in privileged programs. |
| PE11 | LIBRARY | Library Hijacking | Understand insecure shared-library loading and execution. |
| PE12 | DIRTY-COW | SUID Script Execution | Investigate insecure privileged script execution and writable task files. |

## Recommended Workflow

Follow these steps for every challenge:

1. Read the challenge description.
2. Identify the target system and relevant files.
3. Enumerate users, groups, permissions, processes, and configurations.
4. Identify the security weakness.
5. Research the underlying Linux security concept.
6. Test your findings in the authorized lab environment.
7. Document the exploitation process.
8. Record the impact and recommended remediation.

## Challenge Details

### PE01 — SUID Misconfiguration

**Category:** Linux Privilege Escalation

**Objective:** Investigate an SUID-enabled executable and understand how incorrect privileged execution can expose another user's permissions.

**Things to investigate:**
- SUID permissions.
- File ownership.
- Executable permissions.
- Program behavior.
- Effective user ID.

**Learning outcome:** Understand how SUID programs operate and why privileged executables must be carefully reviewed.

### PE02 — Credential Discovery

**Category:** Information Disclosure

**Objective:** Investigate application records and maintenance files for exposed or improperly protected information.

**Things to investigate:**
- Application records.
- Backup and cache files.
- File permissions.
- Encoded data.
- Credential handling.

**Learning outcome:** Understand how sensitive information can be exposed through poorly protected application files.

### PE03 — Sudo Misconfiguration

**Category:** Linux Privilege Escalation

**Objective:** Examine sudo permissions and identify security risks caused by excessive command privileges.

**Things to investigate:**
- Sudo configuration.
- User privileges.
- Allowed commands.
- File ownership.
- Command execution behavior.

**Learning outcome:** Understand the principle of least privilege and secure sudo configuration.

### PE04 — Insecure File Permissions

**Category:** Linux File Permissions

**Objective:** Investigate maintenance scripts and executable files with unsafe permissions.

**Things to investigate:**
- Writable files.
- Script ownership.
- Execution permissions.
- Parent directory permissions.
- Privileged execution.

**Learning outcome:** Understand how insecure file permissions can create privilege escalation opportunities.

### PE05 — PATH Hijacking

**Category:** Environment Variables

**Objective:** Investigate a program that relies on command lookup through the PATH environment variable.

**Things to investigate:**
- PATH variable.
- Command resolution.
- Relative and absolute paths.
- Script behavior.
- Executable search order.

**Learning outcome:** Understand why privileged programs should use trusted absolute command paths.

### PE06 — Cron Job Misconfiguration

**Category:** Scheduled Tasks

**Objective:** Investigate scheduled maintenance tasks and identify insecure permissions or execution configurations.

**Things to investigate:**
- Cron configuration.
- Scheduled scripts.
- Script ownership.
- Writable files.
- Execution frequency.

**Learning outcome:** Understand the security implications of poorly configured scheduled tasks.

### PE07 — Service Misconfiguration

**Category:** Linux Services

**Objective:** Examine service execution scripts and maintenance tasks for insecure configurations.

**Things to investigate:**
- Running services.
- Service scripts.
- Process ownership.
- Writable task files.
- Service execution privileges.

**Learning outcome:** Understand how insecure service configurations can expose privileged execution.

### PE08 — SSH Key Exposure

**Category:** Authentication Security

**Objective:** Investigate exposed SSH key material and understand the risks of insecure credential storage.

**Things to investigate:**
- SSH configuration.
- Private key permissions.
- Backup files.
- Authorized keys.
- Authentication security.

**Learning outcome:** Understand secure SSH key management and why private keys must remain protected.

### PE09 — NFS Misconfiguration

**Category:** Network File Sharing

**Objective:** Examine NFS exports and identify security weaknesses in shared directories.

**Things to investigate:**
- NFS exports.
- Export permissions.
- Network restrictions.
- Shared directory ownership.
- Client access.

**Learning outcome:** Understand the security risks of improperly configured network file shares.

### PE10 — Legacy SUID Environment Handling

**Category:** Legacy Linux Security

**Objective:** Investigate a legacy privileged executable and understand how unsafe environment handling can affect execution.

**Things to investigate:**
- SUID behavior.
- Environment variables.
- Executable permissions.
- Program execution flow.
- Legacy system behavior.

**Learning outcome:** Understand why privileged applications must validate their execution environment.

### PE11 — Library Hijacking

**Category:** Shared Library Security

**Objective:** Investigate how an application loads shared libraries and identify insecure library-loading configurations.

**Things to investigate:**
- Shared libraries.
- Library paths.
- Dynamic linking.
- File permissions.
- Program dependencies.

**Learning outcome:** Understand how unsafe library loading can affect application security.

### PE12 — SUID Script Execution

**Category:** Privileged Script Execution

**Objective:** Investigate a privileged helper that executes a maintenance script and understand the risks of writable scripts in privileged execution paths.

**Things to investigate:**
- SUID helper behavior.
- Script permissions.
- File ownership.
- Execution flow.
- Privileged task execution.

**Learning outcome:** Understand why privileged programs must not execute untrusted or user-writable scripts.

**Note:** Despite the directory name `PE12-DIRTY-COW`, this challenge is a privileged script execution misconfiguration exercise. It is not a verified CVE-2016-5195 Dirty COW exploit.

## Reporting Template

For each completed challenge, document:

- Challenge ID and name.
- Objective.
- Target information.
- Enumeration performed.
- Vulnerability identified.
- Evidence collected.
- Steps taken in the authorized lab.
- Result and impact.
- Recommended remediation.

## Security and Authorization

This platform is designed for authorized cybersecurity education and controlled laboratory practice.

- Use the challenges only in the provided lab environment.
- Do not target systems without explicit permission.
- Do not expose credentials, private keys, flags, or instructor walkthroughs.
- Restore modified files and configurations after testing.
- Follow the Cybersecurity Club DIT ethical hacking guidelines.

## Disclaimer

CCD HACKBOX is an educational project. The challenges are intentionally vulnerable and should not be deployed on production systems or exposed to untrusted networks.

---

**Cybersecurity Club DIT**  
**CCD HACKBOX — Linux Privilege Escalation Training**
EOF



