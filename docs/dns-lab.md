# DNS Lab

## Overview

This lab documents the deployment and testing of a local DNS environment inside a home infrastructure lab.

The goal of this lab is to understand how DNS resolution works, how local DNS servers can be deployed, and how DNS integrates with network infrastructure.

The lab focuses on:

- DNS resolution process
- local DNS server configuration
- DNS forwarding
- DNS troubleshooting

---

## Lab Environment

Network components used in this lab:

- router / gateway
- internal DNS server
- Linux client machine
- local network

Example topology:

```
Client → DNS Server → Upstream DNS → Internet
```

---

## Objectives

- understand DNS resolution flow
- configure a local DNS server
- test DNS queries
- verify DNS forwarding
- troubleshoot DNS issues

---

## Tools Used

- Linux
- dig
- nslookup
- ping
- traceroute

---

## DNS Resolution Test

Example DNS query using `dig`:

```bash
dig google.com
```

Key sections of the response:

```
QUESTION SECTION
ANSWER SECTION
AUTHORITY SECTION
ADDITIONAL SECTION
```

Important values:

- query time
- DNS server used
- resolved IP address

---

## Local DNS Configuration

In this lab a local DNS server is configured to handle DNS queries for internal clients.

Example resolver configuration:

```
/etc/resolv.conf
```

Example:

```
nameserver 192.168.1.1
```

This directs DNS queries from the client to the local DNS server.

---

## DNS Forwarding

The DNS server forwards external requests to upstream public resolvers.

Example upstream DNS:

```
1.1.1.1
8.8.8.8
```

Flow:

```
Client → Local DNS → Public DNS → Internet
```

---

## Verification

Test DNS resolution:

```bash
dig github.com
```

Expected result:

- DNS query returns valid IP address
- query time is reasonable
- no resolution errors

---

## Troubleshooting

Common DNS troubleshooting steps:

Check resolver configuration:

```bash
cat /etc/resolv.conf
```

Test DNS server directly:

```bash
dig @192.168.1.1 google.com
```

Check network connectivity:

```bash
ping 8.8.8.8
```

---

## Key Learnings

This lab demonstrates:

- how DNS queries are resolved
- how local DNS servers integrate with network infrastructure
- how to troubleshoot DNS issues using command line tools

---

## Future Improvements

Possible extensions for this lab:

- deploy dedicated DNS server (Bind / Unbound)
- implement DNS caching
- add internal DNS zones
- monitor DNS queries