# Linux Network Security Investigation — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to perform a basic network security audit of a Kali Linux system from a defensive cybersecurity perspective.

The investigation focused on network interfaces, routing information, DNS configuration, listening services, active network connections, host information, firewall status, and network-associated processes.

---

## 2. Network Interface Investigation

### Command Used

```bash
ip addr

### Investigation

The `ip addr` command was used to identify the network interfaces configured on the Kali Linux system.

### Observation

The command displayed the available network interfaces along with their IP addressing and interface status.

### Security Relevance

Network interface information helps analysts understand how a system is connected to a network and which interfaces are currently active.

### Evidence

![Network Interfaces](./screenshots/01-network-interfaces.png)

---

## 3. Routing Table Investigation

### Command Used

```bash
ip route

### Investigation

The routing table was reviewed to understand how network traffic is routed from the local system.

### Observation

The command displayed the configured routes and the default network gateway.

### Security Relevance

Routing information helps analysts understand the network path used by the system and identify unexpected or unusual routes.

### Evidence

![Routing Table](./screenshots/02-routing-table.png)

---

## 4. DNS Configuration Investigation

### Command Used

```bash
cat /etc/resolv.conf

### Investigation

The local DNS resolver configuration was reviewed.

### Observation

The configuration displayed the DNS resolver information available to the system.

### Security Relevance

DNS configuration is important because domain-name resolution is used by many network applications. Unexpected DNS configuration may require further investigation.

### Evidence

![DNS Configuration](./screenshots/03-dns-configuration.png)

---

## 5. Listening Services Investigation

### Command Used

```bash
ss -tuln

### Investigation

The command was used to identify TCP and UDP ports that were listening on the local system.

### Observation

The output displayed locally listening network sockets.

### Security Relevance

Listening services represent potential network exposure. Analysts should identify which services are expected and determine whether unnecessary services should be disabled.

### Evidence

![Listening Services](./screenshots/04-listening-services.png)

---

## 6. Active Network Connections

### Command Used

```bash
ss -tunap

### Investigation

Active TCP and UDP network connections were reviewed.

### Observation

The output displayed active network connections and associated socket information.

### Security Relevance

Reviewing active connections can help analysts identify unexpected network communication and understand the current network activity of an endpoint.

### Evidence

![Active Connections](./screenshots/05-active-connections.png)

---

## 7. Host Information Investigation

### Commands Used

```bash
hostname
hostnamectl

Inverstigation workflow

Identify Network Interfaces
          ↓
Review Routing Table
          ↓
Review DNS Configuration
          ↓
Identify Listening Services
          ↓
Review Active Connections
          ↓
Check Host Information
          ↓
Review Firewall Status
          ↓
Identify Network Processes
          ↓
Document Findings
          ↓
Assess Security Relevance


