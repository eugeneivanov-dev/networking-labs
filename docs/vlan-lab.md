# VLAN Lab

## Overview

This lab documents the configuration and testing of Virtual LANs (VLANs) within a home infrastructure lab.

The goal of this lab is to understand how VLANs segment networks, isolate traffic, and improve network organization and security.

The lab focuses on:

- network segmentation
- VLAN configuration
- inter-VLAN routing
- connectivity testing

---

## Lab Environment

Network components used in this lab:

- router or Layer 3 device
- managed switch
- client machines
- multiple VLAN networks

Example topology:

```
Client VLAN 10
        │
        │
Managed Switch
        │
        │
Router / Gateway
        │
     Internet
```

---

## Objectives

- understand VLAN concepts
- configure VLANs on a managed switch
- assign switch ports to VLANs
- test network isolation
- configure routing between VLANs

---

## VLAN Concepts

A VLAN (Virtual Local Area Network) allows multiple logical networks to exist on the same physical switch.

Benefits of VLANs:

- traffic isolation
- improved security
- easier network management
- broadcast domain separation

Example VLAN design:

```
VLAN 10 — main network
VLAN 20 — IoT devices
VLAN 30 — guest network
```

---

## Example VLAN Configuration

Example switch configuration concept:

```
Port 1–8   → VLAN 10
Port 9–16  → VLAN 20
Port 17–24 → VLAN 30
```

Trunk port example:

```
Switch Port → Router
Allowed VLANs: 10, 20, 30
```

---

## Testing VLAN Isolation

Verify that devices in different VLANs cannot communicate without routing.

Example test:

```bash
ping 192.168.20.10
```

If routing is not configured, the request should fail.

---

## Inter-VLAN Routing

To allow communication between VLANs, routing must be configured.

Example design:

```
VLAN 10 → 192.168.10.0/24
VLAN 20 → 192.168.20.0/24
VLAN 30 → 192.168.30.0/24
```

Router interfaces:

```
192.168.10.1
192.168.20.1
192.168.30.1
```

---

## Verification

Confirm the following:

- devices within the same VLAN can communicate
- devices in different VLANs are isolated
- routing works when enabled
- internet access works through the gateway

---

## Troubleshooting

Common issues include:

- incorrect VLAN assignment
- trunk port misconfiguration
- incorrect gateway configuration

Useful commands:

```bash
ip a
ip route
ping
traceroute
```

---

## Key Learnings

This lab demonstrates:

- how VLANs segment network traffic
- how switches manage multiple networks
- how routing enables communication between VLANs
- how VLAN design improves infrastructure organization

---

## Future Improvements

Possible extensions:

- implement VLANs for IoT devices
- implement guest network isolation
- apply firewall rules between VLANs
- monitor VLAN traffic