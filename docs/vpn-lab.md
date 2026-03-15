# VPN Lab

## Overview

This lab documents the configuration and testing of a Virtual Private Network (VPN) within a home infrastructure lab.

The goal of this lab is to understand how VPNs provide secure remote access to internal networks and protect traffic across public networks.

The lab focuses on:

- VPN concepts
- remote access configuration
- encrypted tunnels
- connectivity testing

---

## Lab Environment

Network components used in this lab:

- router or VPN server
- internal network
- remote client device
- internet connection

Example topology:

```
Remote Client
      │
      │ (encrypted VPN tunnel)
      │
VPN Server / Router
      │
Internal Network
```

---

## Objectives

- understand VPN fundamentals
- configure a VPN server
- establish secure remote connections
- verify encrypted traffic
- troubleshoot VPN connectivity

---

## VPN Concepts

A VPN creates a secure encrypted tunnel between a client and a remote network.

Benefits:

- secure remote access
- encrypted traffic
- access to internal resources
- protection when using public networks

Common VPN protocols:

```
WireGuard
OpenVPN
IPsec
```

---

## Example VPN Setup

Example configuration:

```
VPN server address: public IP
VPN network: 10.0.0.0/24
Internal network: 192.168.1.0/24
```

Flow:

```
Remote client → VPN tunnel → internal network
```

---

## Testing VPN Connection

Verify VPN connection status.

Example test:

```bash
ping 192.168.1.1
```

Test access to internal services.

Example:

```bash
ssh user@192.168.1.10
```

Verify internet access through VPN if configured.

---

## Verification

Confirm the following:

- VPN client connects successfully
- internal network resources are reachable
- traffic is encrypted
- DNS resolution works through the VPN

---

## Troubleshooting

Common VPN issues:

- incorrect routing
- firewall blocking VPN ports
- DNS configuration problems
- authentication errors

Useful commands:

```bash
ping
traceroute
ip route
```

Check VPN interface:

```bash
ip a
```

---

## Key Learnings

This lab demonstrates:

- how VPN tunnels are established
- how secure remote access works
- how VPN routing integrates with internal networks
- how to troubleshoot VPN connectivity issues

---

## Future Improvements

Possible extensions:

- deploy WireGuard for high performance VPN
- implement site-to-site VPN
- add multi-factor authentication
- monitor VPN traffic and connections