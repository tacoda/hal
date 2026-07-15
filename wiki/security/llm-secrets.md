---
type: Reference
title: "LLM Secrets: Protect .env Secrets from Claude Code"
tags: [security, secrets, ai-code-security, claude-code, encryption, open-source]
timestamp: 2026-07-14
source: https://llmsecrets.com/
---

# LLM Secrets: Protect .env Secrets from Claude Code

LLM Secrets is a **local secrets manager for AI coding assistants** (branded around
Claude Code). It addresses a specific, documented leak: coding assistants have been
observed auto-loading local `.env` files, pulling API keys and database credentials into
model context without an explicit prompt. LLM Secrets lets the assistant **deploy, test,
and run commands without ever seeing the plaintext secret** — [Data Governance](../ai-governance/data-governance.md)
lists it alongside [CodeGate](codegate-stacklok.md) as a local data-loss control that
keeps secrets out of the model's reach.

## How it works

The vault is encrypted, hardware-bound, and unlocked by a phone / laptop / passkey; the
CLI is `scrt4`:

- Install via one line; register a passkey (iPhone Face ID, Google passkey, or security
  key); `scrt4 setup` (~60s). Import existing files with `scrt4 import .env`.
- `scrt4 unlock` starts a session (~20h) with one tap.
- **AES-256-GCM** authenticated encryption. Setup ~60s. **Zero** secrets exposed to the AI.

The security model is entirely local:

- **Client-side only** — all encryption/decryption happens on your machine; no server sees
  your data.
- **Isolated subprocesses** — secrets are injected at runtime; the assistant sees only
  `$env[NAME]`, never the value (e.g. `forge script` / `hardhat deploy` can use
  `$env:PRIVATE_KEY` to deploy contracts while the key stays hidden).
- **Hardware-bound key** — the master key is derived from your device and never leaves it.
- **In-memory only** — plaintext is never written to disk.
- **Fully auditable** — open source under **AGPL-3.0**, with an independent AI code audit
  (DeepWiki) and published release checksums. Recovery requires setting up backup
  passkeys beforehand.

The result: no one — not Anthropic, not the LLM Secrets developers, not a cloud provider
— is positioned to see your secrets, because every step runs locally on hardware you
control. It is a narrow, effective mitigation for OWASP
[LLM02 Sensitive Information Disclosure](../ai-governance/owasp-llm-top-10.md), complementary to
CodeGate's broader proxy.

## Related

- [Data Governance](../ai-governance/data-governance.md) — cites LLM Secrets as a local data-loss control.
- [CodeGate / Stacklok](codegate-stacklok.md) — sibling local privacy layer for coding
  assistants.
- [OWASP LLM Top 10](../ai-governance/owasp-llm-top-10.md) — the LLM02 risk this addresses.
- [AI Code Security](ai-code-security.md) — the broader coding-assistant security surface.

## References
- [LLM Secrets — Protect .env Secrets from Claude Code](https://llmsecrets.com/)
