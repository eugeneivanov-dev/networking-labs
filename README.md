# Networking Labs

Hands-on networking experiments performed in a personal infrastructure lab.

This repository documents practical networking exercises focused on understanding core networking concepts and how they apply to real infrastructure environments.

The goal of these labs is to build hands-on experience with network configuration, troubleshooting, and infrastructure architecture.

---

# Network Topology

The networking labs are performed within a home infrastructure environment built on a dedicated network stack.

This topology provides a controlled environment for testing DNS, VLAN segmentation, firewall rules, and VPN connectivity.

[View full network topology](docs/network-topology.svg)

Key components:

- UniFi Dream Machine Pro Max (gateway / firewall)
- UniFi Switch (PoE)
- VLAN segmented networks
- Linux lab servers
- Synology NAS
- Wireless infrastructure

---

# Lab Topics

The repository currently includes the following networking labs.

## DNS Lab

Understanding how DNS resolution works and how DNS servers interact with clients and upstream resolvers.

Topics covered:

- DNS resolution process
- DNS query testing
- resolver configuration
- DNS troubleshooting

Documentation: 
[DNS Lab](docs/dns-lab.md)

---

## Firewall Lab

Understanding how firewall rules control network traffic and how security policies are applied within a network.

Topics covered:

- inbound and outbound traffic filtering
- firewall rule structure
- network access control
- troubleshooting blocked traffic

Documentation: 
[Firerwall Lab](docs/firewall.md)

---

## VLAN Lab

Understanding how VLANs segment networks and improve network organization and security.

Topics covered:

- VLAN fundamentals
- network segmentation
- switch port configuration
- inter-VLAN routing

Documentation: 
[VLAN Lab](docs/vlan-lab.md)

---

## VPN Lab

Understanding how VPN tunnels provide secure remote access to internal networks.

Topics covered:

- VPN fundamentals
- encrypted tunnels
- remote network access
- connectivity troubleshooting

Documentation: 
[VPN Lab](docs/vpn-lab.md)

---

# Lab Environment

These labs are performed within a personal home infrastructure lab environment that includes:

- router / firewall
- managed switch
- internal network
- Linux client systems
- internet connectivity

This environment allows testing of real networking concepts in a controlled infrastructure setup.

---

# Repository Purpose

The purpose of this repository is to:

- document networking experiments
- practice infrastructure troubleshooting
- build hands-on networking knowledge
- develop engineering documentation skills

---

# Author

Eugene Ivanov  
Infrastructure Engineering  
Austin, Texas

Website  
https://eugeneivanov.dev

LinkedIn  
https://www.linkedin.com/in/eugeneivanov-dev