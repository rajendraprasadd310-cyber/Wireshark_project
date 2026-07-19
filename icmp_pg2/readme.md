# ICMP Packet Analysis Using Wireshark

## Overview

This project demonstrates how the Internet Control Message Protocol (ICMP) is used to verify network connectivity and troubleshoot communication issues. A virtual lab was created using Windows 11, Windows XP, VirtualBox Host-Only Networking, and Wireshark to capture and analyze ICMP Echo Request and Echo Reply packets.

---

## Objectives

- Understand the working of ICMP.
- Capture and analyze ICMP packets using Wireshark.
- Study ICMP Echo Request and Echo Reply messages.
- Verify network connectivity using the `ping` command.
- Troubleshoot connectivity issues using ICMP.
- Understand the impact of firewall and network configuration on ICMP communication.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Host OS | Windows 11 |
| Virtual Machine | Windows XP |
| Virtualization | Oracle VirtualBox |
| Network | Host-Only Adapter |
| Protocol | ICMP |
| Tool | Wireshark |

---

## Network Topology

```
Windows 11 Host
192.168.56.1
        │
VirtualBox Host-Only Network
        │
Windows XP VM
192.168.56.107
```

---

## Project Workflow

1. Configure the VirtualBox Host-Only Network.
2. Verify IP configuration using `ipconfig`.
3. Verify ARP entries using `arp -a`.
4. Start packet capture in Wireshark.
5. Apply the display filter:

```
icmp
```

6. Ping the Windows XP virtual machine.

```
ping 192.168.56.107
```

7. Analyze:
   - ICMP Echo Request (Type 8)
   - ICMP Echo Reply (Type 0)
   - Identifier
   - Sequence Number
   - TTL
   - Response Time

---

## Troubleshooting Scenarios

### Scenario 1 – Firewall Enabled

**Observation**

- ICMP Echo Requests were transmitted.
- No Echo Replies were received.
- Ping resulted in **Request Timed Out**.

**Cause**

The Windows XP firewall blocked incoming ICMP Echo Requests.

---

### Scenario 2 – Firewall Disabled

**Observation**

- Echo Requests and Echo Replies were successfully exchanged.
- Ping completed with **0% packet loss**.

**Result**

Network connectivity between the Windows 11 host and Windows XP virtual machine was successfully verified.

---

### Scenario 3 – Internet Disconnected

**Observation**

The Windows 11 host and Windows XP virtual machine continued to communicate successfully even after disconnecting the Internet.

**Reason**

Both systems were connected through the **VirtualBox Host-Only Network**, which operates independently of Internet connectivity.

---

### Scenario 4 – Different Networks

Devices on different networks cannot communicate directly.

Communication requires a **router (default gateway)** to forward packets between networks.

---

## Key Packet Analysis

### ICMP Echo Request

- Type: **8**
- Code: **0**
- Source: **192.168.56.1**
- Destination: **192.168.56.107**

Purpose:

Checks whether the destination host is reachable.

---

### ICMP Echo Reply

- Type: **0**
- Code: **0**
- Source: **192.168.56.107**
- Destination: **192.168.56.1**

Purpose:

Confirms successful communication.

---

## Key Learning Outcomes

- Learned how ICMP works.
- Captured and analyzed ICMP packets using Wireshark.
- Understood ICMP Echo Request and Echo Reply.
- Used the `ping` command for network troubleshooting.
- Verified the relationship between ARP and ICMP.
- Observed how firewall configuration affects ICMP communication.
- Understood why Internet connectivity is not required within a Host-Only network.
- Learned why devices on different networks require routing.

---

## Repository Structure

```
icmp_packet_analysis/
│
├── README.md
├── icmp_concept.png
├── icmp_request.png
├── icmp_reply.png
├── host_unreachable.png
├── ping_commands.png
├── icmp.pcapng
└── ICMP_Packet_Analysis_Report.docx
```

---

## Tools Used

- Wireshark
- Oracle VirtualBox
- Windows 11
- Windows XP
- Command Prompt

---

## Future Improvements

- ICMP Destination Unreachable analysis
- Time Exceeded packet analysis
- Traceroute using ICMP
- ICMPv6 packet analysis
- Firewall rule analysis
- Network latency comparison

---

## Author

**Rajendra_Prasad_D**

Cybersecurity Enthusiast | SOC Analyst Aspirant
