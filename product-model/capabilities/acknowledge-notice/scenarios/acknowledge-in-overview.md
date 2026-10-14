---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Acknowledged on a raised notice in the Overview
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Type]}
  contexts:
    app:
      place: android-app::overview
- text: The Product marks the notice acknowledged
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Acknowledged, facts: [Taken or skipped time]}
  contexts:
    app:
      place: android-app::overview
---

# Acknowledge a notice in the Overview

## Trigger

A notice is still open in the Overview.

## Outcome

The notice is acknowledged.
