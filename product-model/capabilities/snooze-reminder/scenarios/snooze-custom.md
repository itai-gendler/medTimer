---
kind: alternative
routes:
  app: Android app
steps:
- text: The snooze duration is Custom
  kind: condition
  entities:
  - {entity: settings, effect: reads, facts: [Snooze duration]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The User chooses Snooze and enters the minutes in the app
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product raises the dose again after the entered minutes
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  contexts:
    app:
      place: android-app
---

# Snooze for a custom duration

## Trigger

The User wants a different delay each time.

## Outcome

The reminder notifies again after the entered time.
