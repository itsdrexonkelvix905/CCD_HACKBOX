
# CCD_HACKBOX Network Setup

## 1. Purpose

This document describes the recommended isolated network configuration for CCD_HACKBOX.

## 2. Recommended Network Mode

Use a VirtualBox Host-only Adapter for local training.

Host-only networking allows virtual machines on the configured host-only network to communicate with one another without requiring the vulnerable target to be exposed to the public internet.

## 3. VirtualBox Configuration

For the CCD_HACKBOX virtual machine:

1. Open VirtualBox.
2. Select CCD_HACKBOX.
3. Open Settings.
4. Select Network.
5. Enable Adapter 1.
6. Select Host-only Adapter.
7. Choose the intended Host-only network.
8. Save the configuration.

Configure the attacker virtual machine to use the same Host-only network.

## 4. Addressing

The development environment has used:

| Component | Address |
|---|---|
| Host-only network | 192.168.56.0/24 |
| CCD_HACKBOX target | 192.168.56.103 |

These are development values, not guaranteed addresses for every installation.

## 5. Connectivity Verification

On each machine, inspect the available network interfaces and assigned IP addresses.

Confirm that:

- Both machines use the same intended Host-only network.
- The target has an address in the expected subnet.
- The attacker can reach the target.
- The target is not unintentionally exposed through a bridged or public interface.

## 6. Network Safety

Do not use Bridged Adapter mode for normal training.

Do not expose intentionally vulnerable services to the internet.

If internet access is required for maintenance, plan and configure it separately. Disable unnecessary interfaces after maintenance.

## 7. Troubleshooting

If the attacker cannot reach the target:

- Check that both machines are powered on.
- Confirm both use the same Host-only network.
- Check their IP addresses.
- Check the virtual network adapter status.
- Review firewall rules.
- Restart the affected virtual network adapter if necessary.
