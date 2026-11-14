
# CCD_HACKBOX Troubleshooting

This document covers common setup and lab connectivity issues.

## 1. Target Machine Does Not Start

Possible causes:

- Insufficient memory.
- Incorrect virtual disk attachment.
- Unsupported virtualization settings.
- Corrupted virtual machine configuration.

Suggested checks:

1. Review the VirtualBox error message.
2. Confirm the virtual disk is attached.
3. Check available host memory.
4. Review the VM system settings.
5. Restore a known-good snapshot if necessary.

## 2. Target IP Address Is Unknown

Check the target machine's network interface configuration from its console.

Confirm that the network adapter is enabled and has received an IP address.

Do not assume that the development address will be used in every installation.

## 3. Attacker Cannot Reach the Target

Check:

- Host-only Adapter configuration.
- Attacker and target subnet.
- Network interface status.
- Firewall configuration.
- Whether both VMs are connected to the same virtual network.

## 4. SSH Connection Fails

Check:

- Whether the SSH service is running.
- Whether the target IP address is correct.
- Whether the service is listening on the expected interface.
- Whether network connectivity is working.

Do not expose SSH on a public interface simply to bypass a local networking issue.

## 5. Challenge Does Not Behave as Expected

Check:

- Whether the correct challenge environment is being used.
- Whether required services are running.
- Whether challenge files have the expected permissions.
- Whether previous exercises changed the environment.
- Whether a clean snapshot is available.

## 6. VM State Is Corrupted

If a known-good snapshot exists, consider restoring it.

Before restoring:

- Preserve any reports or evidence you need.
- Confirm that the snapshot belongs to the correct VM.
- Avoid overwriting the original development VM without a backup.

## 7. Reporting an Issue

When reporting a problem, include:

- Challenge ID.
- VM version or release.
- Attacker operating system.
- Relevant error message.
- Steps taken before the problem.
- Expected behavior.
- Actual behavior.

Never include private passwords, keys or instructor-only flags in a public issue.
