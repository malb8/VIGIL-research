# Human Factors and Workflow Psychology

## The core problem

Traditional phishing awareness training often assumes that users fail because they:

- cannot recognize suspicious URLs
- do not understand phishing
- are careless
- ignore security guidance

In reality, many modern phishing attacks succeed even against technically capable and security-aware employees.

The problem is frequently not lack of intelligence.

The problem is workflow-conditioned trust.

## Workflow-conditioned trust

In modern working environments, employees operate inside highly repetitive and cognitively optimized workflows.

Examples include:

- email triage
- ticket handling
- SSO login flows
- cloud collaboration tools
- HR systems
- finance approvals
- password reset flows
- internal portals
- Teams/Slack notifications
- project-management systems

Over time, users become increasingly familiar with these workflows and begin to treat them as trusted operational environments.

This creates a form of cognitive automation.

Instead of consciously evaluating every navigation decision, users increasingly rely on previously established trust relationships and workflow expectations.

The user may subconsciously reason:

"This came from a familiar workflow.
Therefore it is probably legitimate."

This creates a trust transition.

Trust that originally belonged to a familiar workflow becomes implicitly transferred to a browser navigation, login journey or destination.

The challenge is not that users stop thinking.

The challenge is that familiar workflows encourage efficient decision-making, reducing the likelihood that trust will be consciously reassessed at every step.

## Why standard phishing training is often insufficient

Many traditional phishing-awareness programs focus primarily on:

- suspicious spelling
- strange sender addresses
- urgent language
- fake domains
- suspicious attachments
- obvious scams

While useful, this model does not fully address:

- workflow habituation
- cognitive autopilot
- task-switch overload
- operational pressure
- approval fatigue
- trust transfer from enterprise tooling
- repeated SSO/login normalization
- repeated SSO and login normalization

As attackers increasingly abuse legitimate platforms, trusted SaaS environments and familiar workflows, many of the traditional warning signs become less visible.

## Relevant psychological concepts

The broader psychology behind this area overlaps with research into:

- habituation
- automaticity
- cognitive load
- attentional blindness
- conditioned trust
- human factors engineering
- security fatigue
- decision fatigue
- heuristic processing
- dual-process cognition

The problem is strongly related to:

```text
System 1 vs System 2 decision-making
```

where fast, low-friction operational behavior overrides deliberate inspection.

## VIGIL Gate's design response

VIGIL Gate is designed around a simple principle:

interrupt automatic trust transitions

The extension attempts to introduce a deliberate verification boundary between:

workflow
→ browser navigation

The goal is not to classify websites as safe or to eliminate trust.

The goal is to restore conscious verification before navigation continues and to create a brief moment of reassessment before trust is transferred from one context to another.

In this sense, VIGIL is not designed to reduce trust but designed to make trust transitions visible and conscious.