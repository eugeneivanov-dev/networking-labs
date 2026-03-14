# Firewall Lab

## Overview

This lab documents the basic configuration and testing of firewall rules within a home infrastructure lab.

The goal of this lab is to understand how firewalls control network traffic, how rules are applied, and how firewall configuration affects connectivity and security.

The lab focuses on:

- firewall rule structure
- inbound and outbound traffic filtering
- network segmentation
- firewall troubleshooting

---

## Lab Environment

Network components used in this lab:

- router / firewall device
- internal network
- client machine
- internet connection

Example topology:

```
Client → Firewall → Internet
```

In this setup, the firewall controls traffic between the internal network and external networks.

---

## Objectives

- understand how firewall rules work
- configure basic allow and deny rules
- test network access through firewall policies
- observe how firewall configuration impacts connectivity
- troubleshoot blocked network traffic

---

## Tools Used

- Linux
- ping
- traceroute
- netstat
- curl
- firewall configuration interface (router or Linux firewall)

---

## Basic Firewall Concepts

Firewalls operate by evaluating traffic against defined rules.

Common rule parameters include:

- source IP address
- destination IP address
- protocol (TCP / UDP / ICMP)
- port number
- action (allow or deny)

Example rule logic:

```
Allow: internal network → internet
Deny: external network → internal services
```

---

## Example Firewall Rule

Example rule allowing HTTP traffic:

```
Allow TCP port 80
Source: internal network
Destination: internet
```

Example rule allowing HTTPS traffic:

```
Allow TCP port 443
Source: internal network
Destination: internet
```

Example rule blocking inbound connections:

```
Deny all inbound traffic
Source: internet
Destination: internal network
```

---

## Testing Firewall Behavior

Test basic connectivity:

```bash
ping google.com
```

Test HTTP access:

```bash
curl http://example.com
```

Trace network path:

```bash
traceroute google.com
```

If firewall rules are working correctly, only permitted traffic should pass through.

---

## Verification

Verify that:

- internal clients can reach external services
- blocked ports cannot be accessed
- firewall rules apply in correct order

Example test:

```bash
curl https://github.com
```

Expected result:

- successful connection if HTTPS is allowed
- connection failure if blocked

---

## Troubleshooting

Common troubleshooting steps:

Check network connectivity:

```bash
ping 8.8.8.8
```

Check DNS resolution:

```bash
dig google.com
```

Check active connections:

```bash
netstat -tuln
```

Verify firewall rule order and configuration.

Incorrect rule ordering may allow or block traffic unintentionally.

---

## Key Learnings

This lab demonstrates:

- how firewall rules control network traffic
- how network access can be restricted or allowed
- how firewall misconfiguration can impact connectivity
- how to troubleshoot firewall-related network issues

---

## Future Improvements

Possible extensions for this lab:

- implement advanced firewall rules
- configure network segmentation using VLANs
- add logging for firewall events
- implement intrusion detection or prevention systems