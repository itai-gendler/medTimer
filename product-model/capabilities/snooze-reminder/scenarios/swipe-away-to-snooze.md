---
kind: alternative
routes:
  app: Android app
steps:
- text: The action when dismissing a notification is Snooze
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
- text: The Product raises the dose again after the snooze duration
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  - {entity: settings, effect: reads, facts: [Snooze duration]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Snooze by dismissing the notification

## Trigger

The User dismisses the notification to be reminded later.

## Outcome

The reminder notifies again after the snooze duration.
