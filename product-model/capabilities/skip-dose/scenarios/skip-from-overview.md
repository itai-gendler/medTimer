---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Skipped on a taken event in the Overview
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product marks the event skipped and gives its dosage back to the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Taken, to: Skipped, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Change a taken dose to skipped

## Trigger

The User marked a dose taken by mistake.

## Outcome

The event is skipped and the stock is as before the dose.
