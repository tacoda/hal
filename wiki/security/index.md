---
type: Index
title: Security
timestamp: 2026-07-14
---

# Security

Security & cybersecurity — web security, secure code, secrets, supply chain.

- [AI Code Security](ai-code-security.md) — scan agent code as untrusted input; SAST/secrets/supply-chain shifted left; guards the artifact (vs runtime traffic, vs containment)
- [Building Secure and Reliable Systems (Google)](building-secure-and-reliable-systems.md) — least privilege and the reconciler as safety mechanism; security and reliability as one discipline
- [Cisco CodeGuard: Security Skills](cisco-codeguard-security-skills.md) — eval-backed security skills injected into the agent; 47%→84% secure-code
- [CodeGate / Stacklok](codegate-stacklok.md) — local secrets/PII proxy for coding assistants, now K8s-native governed MCP
- [Does AI Generate Secure Code? (Caleb Sima)](does-ai-generate-secure-code.md) — AI writes insecure code because we do; injection is a control/data-plane problem
- [Essential Cybersecurity Science](essential-cybersecurity-science.md) — the scientific method (hypothesis, controlled experiment, measurement, reproducibility) applied to security claims
- [The Hidden Vulnerabilities Behind AI Code (Brandel)](hidden-vulnerabilities-ai-code.md) — correctness climbs while security benchmarks stay flat
- [litellm PyPI Supply-Chain Attack](litellm-pypi-supply-chain-attack.md) — malicious .pth harvests creds and pivots into Kubernetes
- [LLM Secrets — Protect .env from Claude Code](llm-secrets.md) — hardware-bound local vault so the agent runs commands without seeing plaintext secrets
- [Web Security: A WhiteHat Perspective](web-security.md) — a defender-mindset tour of web attacks (XSS, CSRF, injection, clickjacking) and running an SDL at scale
