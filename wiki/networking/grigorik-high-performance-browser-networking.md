---
type: Reference
title: High Performance Browser Networking
tags: [networking, web-performance, tcp, tls, http2, quic, websocket, browser]
timestamp: 2026-07-14
source: https://hpbn.co/
---

# High Performance Browser Networking

Ilya Grigorik's *High Performance Browser Networking* (O'Reilly) is a hands-on guide to
how the network stack shapes web performance — and, crucially, it is available free in
full at [hpbn.co](https://hpbn.co/). Its thesis is that **performance is a feature**:
latency and the behavior of the protocols underneath the browser, not just bandwidth,
determine how fast a page feels, and web developers can only make good decisions once
they understand what TCP, TLS, and HTTP are doing on their behalf. It connects the
low-level mechanics to the concrete experience of the Web, so it anchors both
[HTTP and the Web](http-and-the-web.md) and [how the web works](how-the-web-works.md).

## Scope and approach

The book climbs the stack, always framing each layer in terms of its performance cost:

1. **Networking 101** — a primer on latency and bandwidth (the "many components of
   latency," the speed-of-light floor, last-mile delays), then the building blocks of
   TCP: the three-way handshake, flow control, slow-start, and congestion avoidance —
   why a fresh connection is slow before it is fast. Also UDP and the transport-layer
   view of [network protocols](network-protocols.md), plus
   [TLS](tls-ssl-and-certificates.md), including the handshake round-trips, session
   resumption, and why encryption need not be slow.

2. **Performance of wireless networks** — how Wi-Fi, 3G/4G, and mobile radios differ
   from wired links: variable latency, the energy cost of the radio, and what that means
   for how applications should batch and schedule traffic.

3. **HTTP** — the evolution of the application protocol and its performance
   consequences: HTTP/1.x and its head-of-line blocking and connection-management
   workarounds; HTTP/2 with multiplexing, header compression, and server push; and the
   move toward QUIC. This is the performance-centric complement to
   [HTTP and the Web](http-and-the-web.md).

4. **Browser APIs and protocols** — XMLHttpRequest, Server-Sent Events, WebSocket, and
   WebRTC: the delivery mechanisms available in the browser, when each is the right tool,
   and their respective latency and overhead profiles.

## Why it matters

The book's value is that it makes the invisible visible: a slow page is often slow
because of connection setup cost, TLS round-trips, or a protocol's head-of-line
blocking — not the size of the payload. By explaining the handshakes and control loops
concretely, it turns "the site feels slow" into a diagnosable, fixable engineering
problem. For the protocol internals at byte level it complements the packet-trace detail
of a reference like
[TCP/IP Illustrated](stevens-tcp-ip-illustrated.md).

## References

- [High Performance Browser Networking (free, full text)](https://hpbn.co/)
