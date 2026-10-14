---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Taken on a skipped event in the Overview
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product marks the event taken and reduces the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Skipped, to: Taken, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Change a skipped dose to taken

## Trigger

The User skipped a dose by mistake or took it after all.

## Outcome

The event is taken.
