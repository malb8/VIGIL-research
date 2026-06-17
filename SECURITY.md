# SECURITY

## Reporting vulnerabilities

Please report vulnerabilities responsibly and avoid public disclosure before review.

Include:
- vulnerability description
- reproduction steps
- affected version
- impact assessment

## Security philosophy

VIGIL Gate does not attempt to classify websites as safe.

The project introduces deliberate verification into workflow-driven browser navigations.

## Current hardening areas

- token-based navigation approval
- replay prevention
- tab isolation
- redirect-chain handling
- forged message resistance
- Unicode normalization for homoglyph and lookalike domain detection
- CI-enforced regression testing with unit and E2E coverage
