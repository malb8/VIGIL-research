# Architecture

## Overview

VIGIL Gate is a browser extension that evaluates web navigations before trust is silently transferred from one workflow step to the next.

Unlike traditional phishing protection, VIGIL does not attempt to determine whether a website is malicious. Instead, it evaluates whether a navigation is consistent with the user's current workflow and whether the destination deserves renewed attention before sensitive interaction continues.

The architecture is intentionally lightweight. Decisions are made locally within the browser using contextual signals derived from the navigation itself. No cloud service, remote reputation platform, or centralized telemetry is required for normal operation.

The result is a privacy-preserving decision process that complements existing browser protections rather than replacing them.

---

## Architectural philosophy

The architecture is built around a simple observation.

Modern phishing attacks rarely begin with obviously malicious websites. Instead, attackers insert themselves into workflows that users already trust. An email, chat message, calendar invitation or OAuth consent screen becomes the starting point of a navigation sequence in which trust is gradually transferred to an attacker-controlled destination.

VIGIL therefore focuses on the transition between workflow steps rather than on the destination alone.

Every navigation becomes an opportunity to ask a simple question:

> *Does this navigation still fit the user's expected workflow?*

The answer is derived from multiple independent observations rather than from a single indicator.

---

## Navigation pipeline

Whenever the browser prepares to navigate to a new page, VIGIL observes the navigation and constructs a contextual view of how the user arrived there.

This context includes information such as the originating page, the destination, the navigation method, and characteristics of the destination itself. Additional observations, such as redirect behaviour, domain familiarity, or workflow continuity, are evaluated without interrupting the browsing experience.

These observations are translated into security signals. Each signal contributes evidence that the navigation either follows an expected workflow or deviates from it.

The decision engine evaluates these signals as a whole rather than relying on any individual heuristic. Most navigations continue uninterrupted because the observed context matches normal user behaviour. Only when multiple signals indicate an unexpected trust transition does VIGIL introduce a navigation gate.

This keeps interruptions focused on situations where deliberate user verification provides meaningful security value.

---

## Signal-based assessment

VIGIL deliberately separates signal collection from decision making.

Individual signals describe specific observations about the navigation, but no single signal determines the outcome. Instead, the decision engine evaluates the overall context before deciding whether additional user attention is warranted.

This approach makes the system easier to extend. New signal categories can be introduced without fundamentally changing the architecture, while existing signals can evolve independently as attack techniques change.

The signal model currently includes observations related to destination characteristics, workflow continuity, navigation behaviour, and user familiarity with previously visited domains.

---

## Decision engine

The decision engine is responsible for translating individual observations into a single navigation outcome. All evaluation is performed locally within the browser.

Rather than treating any individual signal as authoritative, the engine evaluates the complete navigation context. It does not attempt to classify websites as inherently safe or malicious. Instead, it assesses whether a particular navigation event represents an expected continuation of the user's current workflow or an unexpected trust transition that warrants renewed user attention.

Positive indicators that reinforce workflow continuity are considered alongside observations that suggest increased uncertainty or elevated risk. Before reaching a decision, the engine also evaluates transient contextual state. Recent user approvals, workflow continuity, and other short-lived conditions may suppress unnecessary interruptions during legitimate browsing while still allowing unexpected transitions to surface.

The outcome of the evaluation is intentionally simple. A navigation either continues transparently or is temporarily paused so the user can consciously verify the destination before proceeding. Short-lived approval state prevents repeated interruptions during legitimate workflows while avoiding permanent trust decisions.

This separation between signal generation and decision making allows both parts of the architecture to evolve independently. New signals can be introduced without redesigning the decision engine, while improvements to decision logic do not require changes to individual signal producers.

---

## User interaction

When VIGIL determines that additional verification is appropriate, it temporarily pauses navigation and presents the user with the available context.

The goal is not to declare a destination safe or malicious. Instead, the interface exposes the observations that influenced the assessment and gives the user an opportunity to consciously decide whether the navigation matches their expectations.

This preserves user autonomy while reducing the likelihood of automatic trust transfer.

---

## Privacy by design

VIGIL was designed around local processing from the outset.

Navigation assessment is performed within the browser. URLs, browsing history and workflow information are not transmitted to external services as part of the normal decision process.

This architecture reduces dependency on remote infrastructure, limits unnecessary data exposure, and allows VIGIL to operate in environments where privacy or connectivity requirements make cloud-based inspection undesirable.

---

## Relationship to existing security controls

VIGIL is not intended to replace browser security features, phishing filters, endpoint protection, or identity platforms.

Instead, it operates alongside these controls by addressing a different layer of the attack chain: the moment at which users transfer trust from one workflow step to the next.

Conventional security technologies primarily evaluate content, infrastructure, or reputation. VIGIL evaluates navigation context.

These approaches are complementary. Existing security controls continue to detect known malicious infrastructure and compromised content, while VIGIL helps users recognise unexpected trust transitions that may otherwise appear entirely legitimate.

---

## Looking ahead

The current browser extension represents the first implementation of a broader architectural direction.

Future research explores how browser-derived trust signals can become part of a wider trust ecosystem, where navigation context, identity events and workflow provenance contribute to continuous adaptive trust decisions across enterprise environments.

Within that vision, the browser is not the final destination. It is the point where trust transitions become visible.
