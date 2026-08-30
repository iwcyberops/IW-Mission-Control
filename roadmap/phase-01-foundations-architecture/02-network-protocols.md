<!-- 🚩 FLAG: This is Month 2 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 2: Network Protocols, Packet Dissection & Traffic Engineering

> **🎯 Primary Outcome:** Understand network communication at the raw packet byte level, analyze state machines, and master network traffic diagnostics.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Encapsulation & Framing:** OSI vs. TCP/IP models, Ethernet II framing, MTU, packet fragmentation, ARP operation, cache poisoning mechanics.
*   **Layer 3/4 Protocol Mechanics:** IPv4/IPv6 headers, CIDR subnetting, ICMP types, TCP 3-way handshake, sequence/acknowledgment tracking, sliding windows, TCP teardown (FIN/RST), UDP connectionless dynamics.
*   **Core Application Protocols:** DNS query/response binary format, DHCP DORA state machine, HTTP/1.1 methods and headers, TLS handshake records.
*   **Port Scanning Heuristics:** TCP SYN stealth scanning, full connect scanning, UDP ICMP port unreachable dynamics, OS fingerprinting heuristics.

---

### 🛠️ 2. Tools & Operational Environment

`Wireshark` | `tcpdump` | `tshark` | `nmap` | `netcat` | `socat` | `hping3` | `scapy` | `iptables`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Dissect packet headers down to bitfields (IP flags, TCP control bits, window sizes).
*   **Hour 05 (C Track):** Implement basic C memory management; manipulate arrays, pointers, and memory buffers.
*   **Hour 06 (ASM Track):** Learn x86-64 data movement: `mov`, `movzx`, `movsx`, `lea` vs. `mov` differences.
*   **Hour 07 (Hardware Track):** Build combinational logic circuits: Half Adders and Full Adders inside Logisim simulator.
*   **Hours 08–10 (Lab):** Capture lab traffic using `tcpdump`; craft custom malformed TCP packets with `hping3` and `scapy`.
*   **Hour 11 (Reading):** Read RFC 793 (TCP Specification) and RFC 791 (Internet Protocol Specification).
*   **Hour 12 (Documentation):** Draw detailed bit-level header diagrams of IPv4, TCP, and UDP protocols in your notes.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Manual Hex Dump Packet Dissector:** Hand-decode raw hex dumps of ARP, IP, and TCP packets without automated tools.
2.  **Custom Python Raw Socket Sniffer:** Write a raw socket listener in Python that captures, unpacks, and prints TCP flags.
3.  **Lab Protocol Baseline Document:** Complete PCAP captures and detailed analysis of 10 distinct protocols (DNS, SSH, HTTP, TLS, etc.).

---

### 📚 5. Primary Learning Sources

*   📖 *Computer Networking: A Top-Down Approach* (Kurose & Ross)
*   📖 *TCP/IP Illustrated, Volume 1* (W. Richard Stevens)
*   💻 *Wireshark Official Documentation*
*   💻 *Nmap Network Scanning Guide*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Nmap UDP scan takes hours or shows all ports as `open|filtered`.
>
> **🔍 Root Cause:** Linux kernel rate-limits ICMP Destination Unreachable (Type 3, Code 3) error packets to 1 per second.
> 
> **✅ Fix:** Target specific services with version scanning (`nmap -sU -sV -p 53,123,161`) and utilize UDP application payloads.
