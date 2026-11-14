
# CCD_HACKBOX Lab Guide

## 1. Introduction

This guide explains how to prepare and use CCD_HACKBOX for authorized cybersecurity training.

The exercises focus on Linux system enumeration, misconfiguration discovery and privilege escalation concepts.

## 2. Requirements

You need:

- Oracle VirtualBox.
- CCD_HACKBOX virtual machine.
- Kali Linux or another suitable Linux attacker machine.
- Basic Linux terminal knowledge.
- Sufficient RAM and disk space for both virtual machines.

## 3. Lab Network

Recommended configuration:

- Network mode: Host-only Adapter.
- Attacker machine: Connected to the same Host-only network.
- Target machine: Connected to the same Host-only network.

Current development target:

`192.168.56.103`

The IP address may differ in another environment.

## 4. Starting the Lab

1. Open VirtualBox.
2. Start the CCD_HACKBOX virtual machine.
3. Start the attacker machine.
4. Confirm that both machines are connected to the intended isolated network.
5. Identify the target IP address.
6. Confirm connectivity before beginning an exercise.

## 5. Challenge Workflow

For each challenge:

1. Read the challenge objective.
2. Identify the starting access level.
3. Enumerate the target system.
4. Investigate relevant permissions and configurations.
5. Identify the security weakness.
6. Demonstrate the intended learning objective.
7. Record your findings.
8. Restore the environment if required.

## 6. Challenge Series

| Challenge | Learning Topic |
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

## 7. Lab Safety

- Do not connect the vulnerable target directly to a public network.
- Do not use personal credentials inside the lab.
- Do not scan systems without authorization.
- Take a snapshot before major changes.
- Keep instructor-only materials private.

## 8. Reporting Results

A useful lab report should include:

- Challenge ID.
- Objective.
- Initial access level.
- Enumeration performed.
- Vulnerability identified.
- Impact.
- Evidence of successful verification.
- Recommended remediation.

Do not publish private challenge flags or instructor credentials.
