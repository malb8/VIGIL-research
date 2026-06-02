# VIGIL Gate

VIGIL Gate is a Sentyra research initiative exploring workflow-aware browser security, trust-transition verification and contextual user assurance. It is a Chromium browser extension that intercepts selected external browser navigations and introduces a deliberate verification boundary before navigation continues.

Project website:
https://sentyra.nl/onderzoek/vigil-gate/

Privacy Policy:
https://sentyra.nl/onderzoek/vigil-gate/privacy/

The project focuses on a specific security problem that traditional phishing defenses and awareness training often fail to address:

```text
workflow-conditioned trust
```

---
# The problem VIGIL Gate tries to solve

Modern phishing attacks rarely succeed because users are unintelligent or completely unaware of phishing risks.

In many real-world environments, attacks succeed because users operate inside deeply conditioned workflows.

When employees interact with:

- email
- chat systems
- ticketing platforms
- SSO login flows
- password reset notifications
- Teams or Slack messages
- cloud collaboration tools
- finance systems
- desktop applications
- enterprise notifications

…the brain increasingly treats the workflow itself as trusted.

This creates a cognitive shortcut:

> “This came from a familiar workflow, therefore the destination is probably legitimate.”

The trust is transferred automatically from:

```text
workflow familiarity
→ destination legitimacy
```

The problem is often not lack of security knowledge.

The problem is operational autopilot.

---

# Why traditional phishing training is often insufficient

Most phishing-awareness training focuses primarily on:

- suspicious spelling
- strange sender addresses
- urgency cues
- fake domains
- suspicious attachments
- obvious scams

While useful, these approaches often do not address:

- workflow habituation
- cognitive automation
- task-switch overload
- operational pressure
- trust transfer
- approval fatigue
- repetitive SSO normalization
- conditioned enterprise-tool trust

An employee may correctly identify phishing during training while still clicking a malicious workflow link during:

- rapid inbox processing
- multitasking
- meeting transitions
- ticket triage
- high operational load
- notification-driven task switching

VIGIL Gate is designed specifically around this human-factors problem.

---

# Core design philosophy

VIGIL Gate does **not** attempt to be:

- an AI phishing classifier
- a cloud reputation engine
- a browsing analytics platform
- a telemetry-heavy endpoint product

Instead, the extension focuses on a simpler principle:

```text
interrupt automatic trust transitions
```

The extension attempts to insert a deliberate verification boundary between:

```text
external workflow
→ browser navigation
```

The goal is to restore conscious verification before sensitive navigation continues.

---

# Core capabilities

VIGIL Gate attempts to distinguish between:

- normal in-browser browsing behavior
- external workflow-driven navigation

Normal browsing should remain fast and uninterrupted.

Potentially workflow-conditioned external navigations can be gated with:

- destination visibility
- hostname visibility
- redirect visibility
- risk indicators
- domain similarity indicators
- homoglyph detection
- confirmation challenges
- hostname typing verification
- cooling-off delays
- redirect unwrapping
- short-lived approval tokens
- tab-isolated approval state

---

# Security model

The extension is designed around several defensive principles:

- token-based navigation approval
- short-lived approval state
- tab isolation
- redirect-chain protection
- replay prevention
- minimal trust in UI state
- local-first operation
- explicit verification boundaries
- browser-native security constraints

---

# Privacy principles

VIGIL Gate is designed with a local-first privacy model.

By default:

- no telemetry is sent
- no analytics are embedded
- no browsing history is uploaded
- no remote account is required
- no cloud processing is required
- no external tracking services are used

Operational state remains local to the browser profile.

---

# Human factors foundation

The broader psychology behind this area overlaps with research into:

- habituation
- automaticity
- cognitive load
- attentional blindness
- conditioned trust
- security fatigue
- decision fatigue
- heuristic processing
- dual-process cognition
- human factors engineering

The problem strongly overlaps with:

```text
System 1 vs System 2 decision-making
```
See: [https://thedecisionlab.com/reference-guide/philosophy/system-1-and-system-2-thinking]

where fast operational behavior overrides deliberate inspection.

VIGIL Gate should therefore be viewed as:

```text
a human-factors-oriented navigation control layer
```

rather than a traditional phishing detector.

---

# Current project status

Current baseline:

```text
v0.4.0 – First Chrome Web Store submission
```

# Documentation

Additional documentation:

Additional public documentation:

- THREAT_MODEL.md
- HUMAN_FACTORS.md
- KNOWN_LIMITATIONS.md
- SECURITY.md
- PRIVACY.md

---

# Threat model scope

VIGIL Gate primarily focuses on:

- workflow-conditioned navigation trust
- phishing redirects
- deceptive login flows
- external application browser launches
- malicious redirect chains
- operational autopilot behavior

The project does **not** attempt to solve:

- endpoint compromise
- malicious extensions
- browser zero-days
- local malware
- physical device compromise
- user-approved malicious destinations

---

# Important disclaimer

VIGIL Gate is an experimental defensive security project.

It should not be considered a complete anti-phishing solution.

The extension is intended to reduce specific classes of workflow-conditioned navigation risk and should be combined with:

- security awareness
- strong identity protections
- MFA
- endpoint protection
- browser hardening
- enterprise monitoring
- least-privilege access control

---

# Public repository scope

This repository contains selected public research material related to the VIGIL Gate project.

The browser extension implementation, internal architecture, development workflows, CI/CD processes, test automation and release engineering artifacts are not published in this repository. This repository focuses on the research concepts, threat models, human factors and security considerations that underpin the project.

The project remains an active research initiative and public documentation may evolve over time.

---

# License

Documentation copyright © Sentyra.

Licensing terms for project materials may be updated as the research evolves.
