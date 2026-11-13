# Deployment Guide

CCD_HACKBOX is intended to run in an isolated VirtualBox environment.

Recommended topology:

Kali Linux (Attacker)
        |
        | Host-only Network
        |
Ubuntu Server (CCD_HACKBOX Target)

Use NAT temporarily for updates when necessary.
Disable NAT during vulnerable lab exercises unless explicitly required.
Never expose intentionally vulnerable services to the public internet.
