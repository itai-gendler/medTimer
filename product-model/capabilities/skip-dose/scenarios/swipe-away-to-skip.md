---
kind: alternative
routes:
  app: Android app
steps:
- text: The action when dismissing a notification is Skip dose, the default
  kind: condition
  entities:
  - {entity: settings, effect: reads, facts: [Action when dismissing notification]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The User swipes the reminder notification away
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product marks the event skipped
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Skipped, facts: [Taken or skipped time, Stock after]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Skip a dose by dismissing its notification

## Trigger

The User dismisses the notification.

## Outcome

The dose is skipped.
