---
type: Index
title: Networking & the Internet
tags: [networking, internet, protocols, dns, tls, cloud, index]
timestamp: 2026-07-14
---

# Networking & the Internet

How computers talk to each other, and how the internet actually works — from the OSI layers
up through DNS, TLS, and HTTP to hosting a site and running it in the cloud. This is the
dedicated deep-dive; the one-note survey lives at
[computer science → computer networks](../computer-science/computer-networks.md), and the
delivery/ops side is in [DevOps & SRE](../devops-sre/index.md). Networking is the substrate
of [distributed systems](../distributed-systems/index.md) and every web application.

## The shape of the field

Networking is layered ([OSI & TCP/IP models](osi-and-tcp-ip-models.md)) across
[topologies and network types](network-topologies-and-types.md), running
[protocols](network-protocols.md) (IP/TCP/UDP) over
[IP addressing and routing](ip-addressing-and-routing.md). The internet's application layer
is names ([DNS](dns.md)), the web protocol ([HTTP](http-and-the-web.md)), and its security
([TLS/SSL & certificates](tls-ssl-and-certificates.md), [network security](network-security.md)).
Put together, that's [how the web works](how-the-web-works.md) — the step-by-step path from a
browser request to a rendered page. To run your own: [hosting and deployment](hosting-and-deployment.md)
(domains, DNS records, SSL, reverse proxies, CDNs), [cloud computing](cloud-computing.md),
and [APIs and web services](apis-and-web-services.md) — with the ops discipline in
[DevOps & SRE](../devops-sre/index.md).

## Concepts

- [OSI and TCP/IP Models](osi-and-tcp-ip-models.md) — the 7 OSI layers and the TCP/IP model; encapsulation; why layering
- [Network Topologies and Types](network-topologies-and-types.md) — PAN/LAN/WAN → the internet; bus/star/mesh; switches vs routers; standards bodies
- [Network Protocols](network-protocols.md) — IP (best-effort), TCP vs UDP, ports & sockets, the three-way handshake
- [IP Addressing and Routing](ip-addressing-and-routing.md) — IPv4/IPv6, CIDR & subnets, NAT, DHCP, routing tables, BGP
- [DNS](dns.md) — the name hierarchy, recursive resolution, record types (A/AAAA/CNAME/MX/TXT), caching & TTL
- [HTTP and the Web](http-and-the-web.md) — request/response, methods & status, headers, cookies, HTTP/1.1 → /2 → /3
- [TLS, SSL, and Certificates](tls-ssl-and-certificates.md) — the handshake, the CA chain of trust, ACME/Let's Encrypt, HTTPS
- [Network Security](network-security.md) — the threat model (MITM, spoofing, DDoS), firewalls, VPNs, segmentation, zero trust
- [How the Web Works](how-the-web-works.md) — the ordered walkthrough: URL → DNS → TCP → TLS → HTTP → parse → render → interactive
- [Hosting and Deployment](hosting-and-deployment.md) — domains, DNS records, servers/PaaS, reverse proxies, SSL certs, CDNs; localhost → public URL
- [Cloud Computing](cloud-computing.md) — IaaS/PaaS/SaaS, regions & AZs, elasticity, serverless, the shared-responsibility model
- [APIs and Web Services](apis-and-web-services.md) — REST, gRPC, GraphQL, webhooks, auth (API keys/OAuth/JWT), rate limiting, versioning

## Canonical works

- [Computer Networks](tanenbaum-computer-networks.md) — Tanenbaum & Wetherall; the classic layered survey
- [TCP/IP Illustrated, Vol. 1](stevens-tcp-ip-illustrated.md) — W. Richard Stevens; the definitive protocol reference
- [High Performance Browser Networking](grigorik-high-performance-browser-networking.md) — Ilya Grigorik; the network stack & web performance (free)
- [Cloudflare Learning Center](cloudflare-learning-center.md) — plain-language explainers for DNS, TLS, CDN, DDoS
- [Computer Networking: A Top-Down Approach](../computer-science/kurose-ross-computer-networking.md) — Kurose & Ross (in computer-science)

## Related fields

[Computer science](../computer-science/computer-networks.md) (the survey),
[distributed systems](../distributed-systems/index.md) (systems over the network),
[DevOps & SRE](../devops-sre/index.md) (deploy & operate), [security](../security/index.md)
(web/network security), [Linux](../linux/networking-on-linux.md) (the stack in practice), and
[web & frontend](../web-frontend/index.md) (what runs on top).
