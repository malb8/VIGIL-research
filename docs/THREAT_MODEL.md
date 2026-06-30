# Threat Model

## Security problem

Modern phishing increasingly succeeds by manipulating user trust rather than exploiting technical vulnerabilities.

Attackers leverage familiar workflows, trusted applications, and expected navigation patterns to guide users toward attacker-controlled destinations. Rather than convincing users to ignore security warnings, many attacks exploit the fact that users naturally transfer trust from one step in a familiar workflow to the next.

VIGIL refers to this phenomenon as **workflow-conditioned trust**.

The objective of VIGIL is to identify these trust transitions and introduce a deliberate verification point before sensitive interactions continue.

Examples include:

* email-driven actions
* collaboration platforms
* chat applications
* password reset workflows
* identity-provider journeys
* cloud administration portals
* calendar invitations
* OAuth authorization flows

---

## In-scope threats

VIGIL focuses on navigation-based attacks that exploit workflow-conditioned trust, including:

* workflow-conditioned trust
* automatic trust transfer
* deceptive login journeys
* identity-provider impersonation
* credential-harvesting redirects
* malicious redirect chains
* external application browser launches
* workflow-driven browser navigations
* phishing attacks that exploit trusted workflows
* OAuth and identity-flow abuse that relies on user trust transfer
* consent phishing
* trusted SaaS navigation abuse
* AiTM phishing campaigns that depend on successfully directing users to attacker-controlled authentication pages
* lookalike and homoglyph domain attacks that visually impersonate legitimate destinations
* first-contact domain deception involving novel or rarely visited domains appearing within otherwise familiar workflows

---

## Out-of-scope threats

VIGIL does not attempt to mitigate:

* endpoint compromise
* malicious browser extensions
* browser vulnerabilities or zero-day exploits
* malware capable of controlling the browser
* physical device compromise
* network-level compromise
* compromise of trusted SaaS providers
* users who intentionally choose to trust an attacker-controlled destination
* post-compromise attacker activity after credentials or authentication tokens have already been stolen
* destinations approved within a recent browsing session, where VIGIL intentionally suppresses repeated prompts using short-lived approval state

---

## Security assumptions

VIGIL assumes that:

* the browser is operating normally
* the extension has not been modified or tampered with
* the operating system has not been compromised
* browser security mechanisms remain functional
* users retain responsibility for final navigation decisions

VIGIL is intended to complement existing browser protections, identity controls, phishing detection, and enterprise security solutions rather than replace them.

---

## Design principles

VIGIL is designed according to the following principles:

* passive by default
* workflow-aware rather than content-aware
* privacy-preserving
* local decision making
* minimal browser permissions
* explainable security decisions
* complementary to existing browser and identity security controls

VIGIL evaluates navigation context rather than attempting to classify every destination as malicious.

---

## Security objective

VIGIL does not attempt to determine whether a destination is objectively safe or malicious.

Instead, it evaluates whether a navigation represents an unexpected trust transition within the user's current workflow and determines whether additional user verification is appropriate before navigation continues.

By interrupting automatic trust transfer at critical navigation points, VIGIL aims to reduce the success of phishing attacks that rely on manipulating user trust rather than exploiting technical vulnerabilities.
