# Day 09 — Linux Network Security Investigation

## Objective

The objective of this investigation was to perform a basic network security audit of a Kali Linux system.

The investigation focused on network interfaces, routing information, DNS configuration, listening services, active network connections, host information, firewall status, and network-associated processes.

## Investigation Areas

- Network interface identification
- Routing table analysis
- DNS configuration review
- Listening network services
- Active network connections
- Host information
- Firewall status
- Network-associated processes

## Tools Used

- Kali Linux
- Linux Terminal
- `ip`
- `ss`
- `hostname`
- `hostnamectl`
- `ufw`
- `lsof`

## Evidence

Screenshots documenting the investigation are stored in the `screenshots/` directory.

## Security Relevance

Network security auditing helps identify active interfaces, network paths, exposed listening services, active connections, and network-related processes.

These observations can help analysts understand the network exposure of a Linux endpoint and identify areas requiring further defensive investigation.

## Ethical Scope

This investigation was performed on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.

All commands were executed locally for defensive security auditing purposes.

## Learning Outcomes

Through this investigation, I practiced:

- Linux network enumeration
- Network interface analysis
- Routing table analysis
- DNS configuration review
- Listening service identification
- Active connection analysis
- Firewall status verification
- Network process investigation
- Security-focused documentation
