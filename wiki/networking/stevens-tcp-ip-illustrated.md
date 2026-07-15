---
type: Reference
title: "TCP/IP Illustrated, Volume 1: The Protocols"
tags: [networking, tcp-ip, protocols, packet-analysis, reference]
timestamp: 2026-07-14
source: https://www.informit.com/store/tcp-ip-illustrated-volume-1-the-protocols-9780321336316
---

# TCP/IP Illustrated, Volume 1: The Protocols

W. Richard Stevens' *TCP/IP Illustrated, Volume 1* (second edition revised by Kevin R.
Fall) is the definitive protocol-level reference for the Internet suite. Where a survey
textbook explains what each layer is *for*, this book shows what actually goes on the
wire: it walks through the protocols one at a time and grounds every explanation in
real captured packets, so the reader sees the exact header fields, flags, and byte
sequences a protocol produces. The "Illustrated" method — narrate a scenario, run a
packet-capture tool, dissect the resulting trace — is what makes it a working reference
rather than a summary. It is the detailed companion to the higher-level
[network protocols](network-protocols.md) note.

## Scope and approach

The book proceeds up the stack, devoting a focused chapter to each protocol and to the
attacks that target it:

- **The Internet address architecture** — how IPv4 and IPv6 addresses are expressed and
  structured, CIDR and route aggregation, special-use ranges, and address allocation —
  the concrete substrate behind [IP addressing and routing](ip-addressing-and-routing.md).
- **Link layer** — Ethernet and the IEEE 802 LAN/MAN standards, bridges and switches,
  Wi-Fi (802.11), PPP, MTU and path-MTU discovery, and tunneling.
- **ARP** — resolving IP addresses to link-layer addresses, the ARP cache, and proxy/
  gratuitous ARP.
- **IP** — the IPv4 and IPv6 datagram formats, fragmentation, and forwarding.
- **ICMP / ICMPv6** — error and diagnostic messaging, the basis of `ping` and
  `traceroute`.
- **System configuration** — DHCP and stateless address autoconfiguration; how a host
  actually gets an address and a route.
- **UDP and TCP** — the two transport protocols in depth: UDP's minimal datagram service,
  and TCP's connection setup and teardown, sliding-window flow control, timeout and
  retransmission, and congestion control across several chapters.
- **DNS** — the name-resolution protocol and its message format.
- **Security** — a treatment of TLS, DNSSEC, and IPsec, plus per-protocol sections
  cataloging the attacks each layer enables.

A distinctive feature of the second edition is that nearly every chapter ends with an
**"attacks"** section, tying protocol mechanics directly to how they are exploited.

## Why it endures

Because it is built from actual packet traces, the book is the reference engineers reach
for when they need to know precisely what a protocol emits — debugging a handshake,
reading a `tcpdump`/Wireshark capture, or reasoning about an edge case the RFCs leave
implicit. It pairs naturally with a top-down survey such as
[Kurose & Ross, Computer Networking](../computer-science/kurose-ross-computer-networking.md):
read the survey for the concepts, keep Stevens open for the bytes.

## References

- [TCP/IP Illustrated, Volume 1: The Protocols — InformIT](https://www.informit.com/store/tcp-ip-illustrated-volume-1-the-protocols-9780321336316)
