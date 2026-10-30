# -NETWORKWALKS-RADSARAN-B084B-WK1-CYBERSECURITY-LAB-SETUP
# Week 1 Lab Setup - Oracle VirtualBox and Kali Linux

## Overview

This lab documents the setup of my cybersecurity practice environment using Oracle VirtualBox and Kali Linux.

Since Kali Linux was already installed on my system, the main objective was to configure the virtual network correctly, provide Internet access, verify connectivity, and create snapshots for recovery.

---

## Lab Environment

### Host Machine
- Windows 10

### Virtualization Platform
- Oracle VirtualBox

### Guest Operating System
- Kali Linux

---

## Network Configuration

### NAT Network Setup

A custom NAT Network was created inside Oracle VirtualBox to provide Internet connectivity to Kali Linux.

#### NAT Network Details

| Setting | Value |
|----------|---------|
| Network Name | lab_net |
| Network Address | 10.0.0.0/24 |
| Gateway | 10.0.0.1 |
| DHCP | Enabled |

### Virtual Machine Network Adapter

| Adapter | Type |
|----------|---------|
| Adapter 1 | NAT Network |

The Kali Linux VM was connected to the NAT Network to receive an IP address automatically and gain Internet access.

---

## IP Address Verification

After starting the virtual machine, the assigned IP address was verified using:

```bash
ip a
```

Example output:

```text
eth0: 10.0.0.x/24
```

Routing information was checked with:

```bash
ip route
```

Expected default route:

```text
default via 10.0.0.1 dev eth0
```

---

## Internet Connectivity Testing

### Test Gateway Connectivity

```bash
ping 10.0.0.1
```

Result:

- Successful replies received
- Gateway reachable

### Test External Network Connectivity

```bash
ping 8.8.8.8
```

Result:

- Successful replies received
- Internet access confirmed

### Test DNS Resolution

```bash
ping google.com
```

Result:

- DNS resolution successful
- Domain names resolved correctly

---

## Network Troubleshooting Commands

Useful commands used during validation:

```bash
ip a
```

Display network interfaces and IP addresses.

```bash
ip route
```

Display routing table.

```bash
ping <destination>
```

Verify network connectivity.

```bash
nslookup google.com
```

Verify DNS functionality.

---

## Kali Linux Update Verification

Internet access was confirmed by updating package information:

```bash
sudo apt update
```

Successful repository access verified that the virtual machine had full Internet connectivity.

---

## Snapshot Creation

After completing the network configuration successfully, a VirtualBox snapshot was created.

### Snapshot Name

```text
Week1-Lab-Completed
```

### Purpose

- Restore system quickly if configuration issues occur
- Preserve a working baseline
- Support future lab activities safely

---

## Learning Outcomes

By completing this lab, I learned how to:

- Configure a NAT Network in Oracle VirtualBox
- Assign network adapters to virtual machines
- Verify IP configuration using Linux networking tools
- Test gateway, Internet, and DNS connectivity
- Troubleshoot network connectivity issues
- Create VirtualBox snapshots for system recovery

---

## Tools Used

- Oracle VirtualBox
- Kali Linux
- Linux Networking Commands
- ICMP (Ping)
- DNS Utilities

---

## Author

Cybersecurity Lab Practice - Week 1

GitHub Repository Documentation

