# Design decisions

Architecture is largely defined by the decisions it deliberately does **not** make.

The following design choices reflect the principles that have guided the development of VIGIL and explain why the architecture differs from traditional phishing detection approaches.

---

## Navigation over reputation

VIGIL does not attempt to determine whether a destination is objectively malicious.

Reputation systems, blocklists and threat intelligence already exist for that purpose. Instead, VIGIL evaluates the navigation that led to the destination. A perfectly legitimate website can still appear in an unexpected workflow, while a newly registered phishing domain may not yet have acquired a negative reputation.

The architecture therefore treats navigation context as the primary security signal.

---

## Signals over signatures

No individual observation is expected to determine the outcome of a navigation.

Instead, VIGIL combines multiple independent observations into a broader assessment of workflow consistency. This makes the decision process more resilient than relying on isolated heuristics or fixed signatures and allows the architecture to evolve as attack techniques change.

---

## Local processing by default

Navigation assessment is performed entirely within the browser.

Keeping the decision process local reduces dependency on external services, limits unnecessary data exposure and allows VIGIL to operate in environments where privacy, availability or network connectivity are important considerations.

Remote services are not required for normal operation.

---

## Deliberate verification instead of automated blocking

The objective of VIGIL is not to replace user judgement.

When sufficient uncertainty exists, the extension introduces a brief verification step before navigation continues. The user remains in control of the final decision, but that decision is made consciously rather than as part of an automatic workflow.

This approach aims to reduce inadvertent trust transfer without unnecessarily restricting legitimate browsing.

---

## Temporary trust rather than permanent trust

Trust is treated as contextual rather than absolute.

A destination that has been consciously approved may continue without interruption for a limited period, reducing friction during legitimate workflows. That approval is intentionally short-lived so that future navigations can be evaluated again as context changes.

The architecture avoids creating permanent trust relationships based solely on previous user behaviour.

---

## Separation of observations and decisions

Signal generation and decision making are independent architectural responsibilities.

Individual signal producers focus on making specific observations about a navigation, while the decision engine evaluates those observations within their broader context. This separation keeps both components easier to understand, test and extend without introducing unnecessary coupling.

---

## Complement existing security controls

VIGIL is not intended to replace browser security features, endpoint protection, identity systems or phishing filters.

Those technologies remain responsible for detecting malicious infrastructure, known threats and compromised content. VIGIL addresses a different point in the attack chain by evaluating whether a navigation represents an unexpected transfer of trust within an otherwise familiar workflow.

The architecture is therefore designed to complement existing security controls rather than compete with them.
