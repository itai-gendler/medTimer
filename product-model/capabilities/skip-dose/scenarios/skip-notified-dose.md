---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Skipped on the reminder notification
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product marks the event skipped now and removes it from the notification
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Skipped, facts: [Taken or skipped time, Stock after]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Skip a dose from its notification

## Trigger

The User does not take a dose.

## Outcome

The event is skipped; following and interval doses that count from it are scheduled.
