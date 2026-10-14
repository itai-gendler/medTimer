---
kind: alternative
routes:
  app: Android app
steps:
- text: The action when dismissing a notification is Taken
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
- text: The Product marks the event taken and reduces the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Taken, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Take a dose by dismissing its notification

## Trigger

The User clears notifications only after taking the dose.

## Outcome

The dose is taken; the notification then offers Skipped and Snooze as buttons.
