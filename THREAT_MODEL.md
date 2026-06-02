# Threat Model

## Primary problem addressed

VIGIL Gate primarily addresses workflow-conditioned trust.

Modern attacks increasingly succeed by exploiting trusted workflows rather than relying solely on obviously malicious content.

Users frequently transfer trust from familiar workflows to browser navigations without consciously reassessing the destination.

Examples include:

* email-driven actions
* collaboration platforms
* chat applications
* password reset workflows
* identity-provider journeys
* cloud administration portals
* calendar invitations
* OAuth authorization flows

VIGIL attempts to interrupt these automatic trust transitions and restore conscious verification before navigation continues.

---

## In-scope threats

VIGIL primarily focuses on:

* workflow-conditioned trust
* automatic trust transfer
* deceptive login journeys
* credential-harvesting redirects
* malicious redirect chains
* external application browser launches
* workflow-driven browser navigations
* phishing attacks that exploit trusted workflows
* OAuth and identity-flow abuse that relies on user trust transfer

---

## Out-of-scope threats

VIGIL does not attempt to address:

* endpoint compromise
* malicious browser extensions
* browser vulnerabilities and zero-days
* malware with browser control
* physical access compromise
* network-level compromise
* user-approved malicious destinations
* attacker-controlled systems that the user consciously chooses to trust
* compromise of trusted SaaS providers
* account compromise that has already occurred

---

## Security assumptions

VIGIL assumes:

* the browser is operating normally
* the extension itself has not been tampered with
* the operating system is not compromised
* users remain responsible for final navigation decisions

VIGIL is intended to complement existing browser, identity and phishing controls rather than replace them.

---

## Security objective

The primary objective of VIGIL is not to determine whether a destination is safe.

The primary objective is to introduce deliberate verification at workflow trust-transition points and reduce the likelihood of automatic trust transfer.
