---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Duplicate in the Advanced settings menu
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product creates a copy of the reminder in the same medicine and returns to the medicine
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Time, Weekdays, Days of month, First cycle start, Active days, Pause days]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
---

# Duplicate a reminder

## Trigger

The User needs a second, similar dose.

## Outcome

The medicine has an identical second reminder to adjust.
