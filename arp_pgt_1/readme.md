# 🛡️ ARP Packet Analysis Using Wireshark

> A hands-on networking project demonstrating how the **Address Resolution Protocol (ARP)** resolves IP addresses to MAC addresses before communication. This project uses **Wireshark** and **Oracle VirtualBox** to capture and analyze ARP and ICMP packets in a controlled Host-Only network environment.

---

## 📖 Project Overview

The Address Resolution Protocol (ARP) is one of the fundamental networking protocols used in IPv4 networks. Before a device can send an Ethernet frame to another device on the same network, it must know the destination's MAC address. If only the IP address is known, ARP is used to discover the corresponding MAC address.

In this project, a virtual lab was created using **Windows 11**, **Windows XP**, and **Kali Linux** in **Oracle VirtualBox**. Wireshark was used to capture ARP and ICMP packets, allowing detailed analysis of how devices communicate within a local network.

---

## 🎯 Objectives

- Understand the working of Address Resolution Protocol (ARP).
- Learn why ARP is required before ICMP communication.
- Capture ARP Request and ARP Reply packets using Wireshark.
- Analyze packet flow between virtual machines.
- Understand ARP Cache and MAC address resolution.
- Learn VirtualBox Host-Only networking.

---

## 🧪 Lab Environment

| Component | Details |
|-----------|---------|
| Host Operating System | Windows 11 |
| Virtual Machine 1 | Windows XP |
| Virtual Machine 2 | Kali Linux |
| Virtualization Software | Oracle VirtualBox |
| Network Mode | Host-Only Adapter |
| Packet Analyzer | Wireshark |

---

## 🌐 Network Topology

```text
                    Windows 11 Host
                  192.168.56.1
                         │
          VirtualBox Host-Only Network
        ─────────────────────────────────
            │                       │
            │                       │
     Windows XP VM           Kali Linux VM
   192.168.56.107          192.168.56.106
```

---

## ⚙️ Project Workflow

```text
Start Virtual Machines
        │
Configure Host-Only Network
        │
Open Wireshark
        │
Start Packet Capture
        │
Ping Windows XP
        │
ARP Request
        │
ARP Reply
        │
ICMP Echo Request
        │
ICMP Echo Reply
        │
Analyze Packets
```

---

## 📂 Repository Structure

```text
ARP-Packet-Analysis/
│
├── README.md
├── docs/
│   └── ARP_Revision_Guide.pdf
│
├── screenshots/
│   ├── arp-concept.png
│   ├── host-network.png
│   ├── windows-xp-ipconfig.png
│   ├── kali-ip.png
│   ├── arp-cache.png
│   ├── wireshark-capture.png
│   └── ping-test.png
│
├── packet-captures/
│   └── arp_packet_capture.pcapng
│
└── LICENSE
```

---

## 📷 Project Screenshots

### ARP Concept

> ARP overview and packet structure.

---

### Host Network Configuration

> Windows 11 VirtualBox Host-Only Adapter configuration.

---

### Windows XP Configuration

> IP configuration of the Windows XP virtual machine.

---

### Kali Linux Configuration

> IP configuration of the Kali Linux virtual machine.

---

### ARP Cache

> ARP table after successful communication.

---

### Wireshark Packet Capture

> Captured ARP Request, ARP Reply, and ICMP packets.

---

## 📦 Packet Analysis

The captured packets demonstrate the complete ARP resolution process.

### ARP Request

- Source: Windows 11 (`192.168.56.1`)
- Destination: Broadcast (`FF:FF:FF:FF:FF:FF`)
- Purpose: Discover the MAC address of `192.168.56.107`

### ARP Reply

- Source: Windows XP (`192.168.56.107`)
- Destination: Windows 11
- Purpose: Provide the MAC address associated with the requested IP.

### ICMP Echo Request

- Sent after successful ARP resolution.
- Used to verify connectivity.

### ICMP Echo Reply

- Response from Windows XP.
- Confirms successful communication.

---

## 🔍 Key Concepts Covered

- Address Resolution Protocol (ARP)
- IP Address
- MAC Address
- Ethernet Frame
- Broadcast Communication
- Unicast Communication
- ARP Cache
- ICMP (Ping)
- Host-Only Networking
- Packet Analysis using Wireshark

---

## 📚 Learning Outcomes

After completing this project, I was able to:

- Understand how ARP resolves IP addresses into MAC addresses.
- Capture and analyze ARP packets using Wireshark.
- Explain why ARP occurs before ICMP communication.
- Understand ARP cache functionality.
- Configure and troubleshoot VirtualBox Host-Only networking.
- Analyze network traffic using Wireshark.

---

## 🚀 Future Work

This project serves as the foundation for the next networking security project:

- ARP Spoofing (ARP Poisoning)
- Man-in-the-Middle (MITM) Attack
- Detecting ARP Poisoning
- Preventing ARP-based Attacks
- ARP Inspection Techniques

---

## 🛠️ Tools Used

- Oracle VirtualBox
- Wireshark
- Windows 11
- Windows XP
- Kali Linux

---

## 📖 References

- RFC 826 – Address Resolution Protocol (ARP)
- Wireshark Documentation
- Oracle VirtualBox Documentation
- Microsoft Networking Documentation

---

## 👨‍💻 Author

**Rajendra Prasad D**

Cybersecurity Enthusiast | Networking | Wireshark | Linux | VirtualBox

---

⭐ **If you found this project helpful, feel free to star the repository!**
