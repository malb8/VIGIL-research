# Signal model

## Overview

VIGIL evaluates navigations by observing multiple independent characteristics of a navigation event rather than relying on a single indicator.

Each observation is represented as a signal. Individually, signals provide only a limited view of the navigation. Together, they form a broader picture that allows the decision engine to assess whether a navigation appears consistent with the user's current workflow.

This approach avoids dependence on individual heuristics, signatures or reputation services and allows the assessment model to evolve as workflows and attack techniques change.

Signals describe observations. The decision engine determines their significance.

---

## Architectural approach

The signal model is designed around a simple principle: a navigation should be evaluated in context.

Rather than asking whether a destination is malicious, VIGIL asks whether the navigation itself is consistent with the user's expected workflow. A navigation is therefore evaluated from multiple perspectives, each contributing independent observations that help establish confidence or introduce uncertainty.

No single perspective is expected to determine the outcome. Confidence emerges from the combination of observations rather than from any individual signal.

---

## Signal categories

To maintain a clear separation of responsibilities, VIGIL groups related observations into logical signal categories. Each category examines a different aspect of the navigation without prescribing how those observations should influence the final decision.

These categories may include observations related to:

* the surrounding workflow and user context
* characteristics of the navigation destination
* the navigation path taken by the browser
* identity and authentication journeys
* previously established browsing context
* other contextual observations relevant to trust assessment

The composition of these categories is intentionally flexible and may evolve as new workflows, technologies and attack techniques emerge.

---

## Signal independence

Signals are intentionally independent of one another.

Each signal represents a single observable characteristic without requiring knowledge of other signals or of the decision logic itself. This separation allows individual observations to be refined, replaced or extended without requiring fundamental architectural changes.

Likewise, the decision engine can evolve independently from the signals that supply its input.

---

## Explainability

Every signal corresponds to an observable property of a navigation event.

When VIGIL requests additional user verification, it is able to present the observations that contributed to the assessment rather than relying on opaque classifications. This helps users understand why attention is being requested while avoiding unnecessary exposure of internal implementation details.

Explainability is therefore considered an architectural property of the signal model rather than a user interface feature.

---

## Evolution

The signal model is intended to evolve over time.

As web technologies, authentication mechanisms and user workflows change, new observations can be incorporated without altering the underlying architectural principles. Existing observations may be refined or retired as their relevance changes.

This allows VIGIL to adapt to evolving attack techniques while preserving a stable architectural framework centred on navigation trust assessment rather than static detection rules.
