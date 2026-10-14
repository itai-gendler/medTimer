---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Snooze on the reminder notification
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product removes the notification and raises the dose again after the snooze duration; the event stays raised
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  - {entity: settings, effect: reads, facts: [Snooze duration]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Snooze from the notification

## Trigger

The User cannot take the dose right now.

## Outcome

The reminder notifies again after the snooze duration.
