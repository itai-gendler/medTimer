---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens a taken event and switches it to Skipped
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage]}
  contexts:
    app:
      place: android-app::edit-event
- text: The Product marks the event skipped and gives the dosage back to the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Taken, to: Skipped, facts: [Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::edit-event
---

# Change an event to skipped

## Trigger

The User realises a dose was not taken.

## Outcome

The event is skipped and the stock restored.
