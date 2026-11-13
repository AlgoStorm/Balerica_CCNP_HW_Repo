# Lab 000 Report — Packet Tracer & Wireshark Verification

**Course:** Cisco Class (BalericaAI/ciscoclass)  
**Lab:** Lab 000 — First Network & Tool Verification  
**Date:** 13 November 2026  
**Student:** [Your Name]

---

## System Information

| Item                        | Details                          |
|-----------------------------|----------------------------------|
| Operating System            | Windows 11                       |
| Processor Architecture      | x86-64                           |
| Packet Tracer Version       | 8.2.x (Cisco Networking Academy) |
| Cisco Login                 | Successful                       |
| Wireshark Version           | 4.6.9                            |

---

## Packet Tracer Verification

### Topology
One Cisco 2960-24TT switch with two end devices (PC-A and PC-B) connected via copper straight-through cables. Link lights are green.

![Packet Tracer Topology — lab000_first_network.pkt](lab000_network.png)

**File saved as:** `lab000_first_network.pkt`

### IP Configuration
| Device | IPv4 Address   | Subnet Mask     |
|--------|----------------|-----------------|
| PC-A   | 192.168.10.10  | 255.255.255.0   |
| PC-B   | 192.168.10.20  | 255.255.255.0   |

No default gateway was configured (same subnet).

### Connectivity Test
Successful ping from PC-A to PC-B (`192.168.10.20`) after ARP resolution.  
(First ping timed out as expected during ARP; subsequent pings succeeded.)

**Pass condition met:** Packet Tracer opens, Cisco sign-in successful, and PCs can ping each other.

---

## Wireshark Verification

### Capture
Live capture on active Wi-Fi interface. Traffic generated with:

```powershell
ping -n 4 1.1.1.1
ping 8.8.8.8
```

![Wireshark ICMP Capture](lab000_wireshark.png)

Display filter `icmp` applied. ICMP Echo Requests and Echo Replies are visible (successful round-trips to both 1.1.1.1 and 8.8.8.8).

**File saved as:** `lab000_capture.pcapng`  
**Wireshark version:** 4.6.9

**Pass condition met:** Live packets captured on a real interface.

---

## Installation Notes

- No installation errors were encountered for Packet Tracer or Wireshark.
- Npcap was installed with the official Wireshark installer so live capture interfaces are available.
- All verification steps completed successfully on the first attempt after Npcap installation.

---

## Submission Checklist

- [x] Operating system and version (Windows 11)
- [x] Processor architecture (x86-64)
- [x] Installed Packet Tracer version and successful Cisco login
- [x] Screenshot of `lab000_first_network.pkt` showing two PCs and the switch
- [x] Screenshot of successful ping inside Packet Tracer (connectivity verified)
- [x] Installed Wireshark version
- [x] Screenshot of a real Wireshark capture with packets visible
- [x] Installation errors: None

**Lab 000 Status:** Complete
