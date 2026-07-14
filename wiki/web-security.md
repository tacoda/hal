---
type: Reference
title: "Web Security: A WhiteHat Perspective"
tags: [web-security, appsec, xss, csrf, sql-injection, authentication, secure-development]
timestamp: 2026-07-14
source: https://www.routledge.com/Web-Security-A-WhiteHat-Perspective/Wu-Zhao/p/book/9781466592612
---

# Web Security: A WhiteHat Perspective

A practitioner's field guide to web application security by Hanqing Wu (a founding
security engineer at Alibaba) and Liz Zhao. The through-line is a defender's mindset:
you cannot secure a system you don't understand as an attacker would. The book is
organized in four movements — a philosophy of security, client-side attacks, server-side
attacks, and the operational reality of running security at an internet company.

## The security worldview

Security is treated as an ongoing *process*, not a product you buy or a box you check —
there is no silver bullet. The recurring design principles are the ones that hold up
regardless of the specific vulnerability:

- **Secure by default** — prefer whitelists over blacklists, and grant least privilege.
- **Defense in depth** — layer independent controls so one failure isn't total failure.
- **Separate data from code** — most injection classes are a failure of this boundary.
- **Unpredictability** — make tokens, layouts, and identifiers hard to guess so attackers
  can't script their way through.

A real security program starts from asset classification, then threat analysis, then risk
analysis, and only then designs controls proportional to the risk. This is the same
discipline that makes [AI-generated code security](ai-code-security.md) tractable: you
reason about what can go wrong *before* you trust the output.

## Client-side attacks

The browser is the trust boundary. Its core defense is the **same-origin policy** —
scripts from one origin can't freely read another's data — reinforced by sandboxing and
malicious-URL interception. Every client attack is essentially a way to bend or bypass
that boundary.

- **XSS (Cross-Site Scripting)** — attacker script executes in the victim's session.
  Three flavors: *reflected* (echoed from the request), *stored* (persisted server-side),
  and *DOM-based* (introduced entirely in client JavaScript). Defense is layered: input
  validation, correct *output* encoding matched to the context (HTML body, attribute,
  event handler, CSS, URL — each needs different escaping), `HttpOnly` cookies so stolen
  script can't read the session, and careful handling of rich text. Worms like Samy show
  how an XSS payload can self-propagate across a social graph.
- **CSRF (Cross-Site Request Forgery)** — the victim's browser is tricked into sending an
  authenticated request they didn't intend. Defenses: anti-CSRF tokens (the primary fix),
  `Referer` checks, and understanding that browser cookie-sending policy is what makes the
  attack possible.
- **Clickjacking** — a transparent overlay tricks the user into clicking something other
  than what they see (including drag-based data theft and mobile "tapjacking"). Defense is
  frame-busting and the `X-Frame-Options` header.
- **HTML5 surface** — new tags create new XSS vectors, while CORS, `postMessage`, and Web
  Storage each widen the attack surface and need their own guardrails. The `iframe`
  sandbox attribute is a useful containment tool.

## Server-side attacks

- **Injection** — SQL injection is the marquee example (including *blind* and *timing*
  variants where the attacker infers data without seeing it directly). The correct defense
  is parameterized/precompiled statements, then type checking and safe functions — not
  hand-rolled escaping. The same data/code confusion drives XML, CRLF, and code injection.
- **File upload** — an upload feature becomes a vulnerability when a server mis-parses the
  uploaded file as executable code (Apache/IIS/PHP-CGI parsing quirks). Secure uploads
  constrain type, storage location, and execution.
- **Authentication & session management** — passwords, multi-factor, and the lifecycle of
  a session. Key attacks: session fixation (forcing a known session id onto the victim)
  and session-keep attacks. Single sign-on centralizes the risk.
- **Access control** — *vertical* (privilege escalation between roles) vs *horizontal*
  (accessing another same-level user's data). OAuth is examined as a delegation model.
- **Crypto & randomness** — cautionary tales rather than algorithm tutorials: reused-key
  and bit-flipping attacks on stream ciphers, ECB mode leaking structure, the padding
  oracle attack, MD5 length-extension, and weak pseudorandom number generators that make
  "random" tokens predictable. The lesson: use vetted primitives and a CSPRNG.
- **Framework security** — MVC frameworks, template auto-escaping, built-in CSRF defense,
  and HTTP header management centralize protection, but the frameworks themselves have
  had critical RCEs (Struts 2, Spring MVC, Django).
- **Application-layer DoS** — CC attacks, Slowloris, HTTP POST DoS, and ReDoS (catastrophic
  regex backtracking); defended with request-rate limiting and CAPTCHAs.
- **PHP & server config** — file-inclusion and variable-coverage bugs, plus hardening
  Apache, Nginx, Tomcat/JBoss, and defending against HTTP parameter pollution.

## Operating security at scale

The final section is the part most attack-focused books skip: how a company actually runs
security. It covers business-logic flaws (broken password-recovery flows, account theft),
spam and phishing defense, user-privacy protection, and — most importantly — the **Secure
Development Lifecycle (SDL)**: baking security into requirements, design, development, and
test phases (including an *agile* SDL), plus security operations (patch process, monitoring,
intrusion detection, emergency response).

This maps onto how modern AI-assisted development needs its own SDL. The
[OWASP LLM Top 10](owasp-llm-top-10.md) is essentially the same threat-modeling exercise
applied to LLM applications — prompt injection is injection, insecure output handling is an
output-encoding failure, excessive agency is a least-privilege failure. The vocabulary
carries over directly.

## References

- [Web Security: A WhiteHat Perspective](https://www.routledge.com/Web-Security-A-WhiteHat-Perspective/Wu-Zhao/p/book/9781466592612) — Hanqing Wu and Liz Zhao, Auerbach Publications / CRC Press, 2015 (ISBN 978-1-4665-9262-9)
