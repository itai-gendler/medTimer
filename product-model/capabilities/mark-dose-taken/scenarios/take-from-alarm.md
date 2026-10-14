---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Taken on the alarm
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-alarm
- text: The Product marks the event taken and reduces the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Taken, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::reminder-alarm
---

# Take a dose from its alarm

## Trigger

A high priority medicine rings as an alarm.

## Outcome

The alarm closes and the dose is taken.
