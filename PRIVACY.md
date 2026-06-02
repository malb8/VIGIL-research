# Privacy

## Philosophy

VIGIL Gate is designed around a local-first privacy model.

The project intentionally minimizes data collection and avoids unnecessary external dependencies.

Navigation analysis, workflow-context analysis and user verification decisions are performed locally within the browser.

---

## Default behavior

By default:

* no telemetry is sent
* no analytics are embedded
* no browsing history is uploaded
* no workflow activity is transmitted
* no download activity is transmitted
* no external tracking services are used
* no cloud account is required

---

## Local storage

Configuration, preferences and short-lived operational state remain local to the browser profile.

This may include:

* extension settings
* allowlists
* temporary navigation state
* short-lived approval state required for navigation verification

No local data is transmitted to external services.

---

## Browser permissions

VIGIL requires browser permissions in order to evaluate navigation context and provide workflow-aware verification.

These permissions are used solely for local processing.

VIGIL does not sell, share or transmit collected browser information to third parties.

Additional details are available in `PERMISSIONS.md`.

---

## Downloads and calendar workflows

VIGIL may observe calendar invitation downloads such as `.ics` files when the downloads permission is enabled.

These events are used only as local workflow-context signals.

VIGIL does not:

* read calendar contents
* modify downloaded files
* upload downloaded files
* transmit download metadata

Calendar-related information remains local to the browser.

---

## Data sharing

VIGIL does not sell user data.

VIGIL does not share user data with advertisers, analytics providers or third-party services.

The extension is designed to operate independently without requiring external data-processing infrastructure.
