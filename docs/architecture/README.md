# CCD_HACKBOX Architecture

## Overview

CCD_HACKBOX is designed as an intentionally vulnerable Ubuntu Server
virtual machine for authorized cybersecurity training.

## Main Components

- Kali Linux: Attacker and testing environment.
- Ubuntu Server: Vulnerable target.
- VirtualBox: Virtualization platform.
- Host-only Network: Isolated lab communication.
- OVA: Portable virtual appliance distribution format.

## Network Design

Kali Linux communicates with CCD_HACKBOX through an isolated
Host-only network.

## Security Requirements

- Do not use bridged networking for the vulnerable target.
- Do not expose vulnerable services to the public internet.
- Keep private flags and credentials out of the public repository.

Detailed implementation and network configuration will be documented
as the appliance is developed and tested.
