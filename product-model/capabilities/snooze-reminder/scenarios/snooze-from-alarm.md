---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Snooze on the alarm
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-alarm
- text: The Product closes the alarm and raises the dose again after the snooze duration
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  - {entity: settings, effect: reads, facts: [Snooze duration]}
  contexts:
    app:
      place: android-app::reminder-alarm
---

# Snooze an alarm

## Trigger

An alarm rings at a bad moment.

## Outcome

The alarm rings again after the snooze duration.
