---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Taken on a raised event in the Overview
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product marks the event taken, reduces the stock and updates the notification
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Taken, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Take a raised dose in the Overview

## Trigger

The User opens the app rather than the notification.

## Outcome

The event is taken and its notification no longer shows it.
