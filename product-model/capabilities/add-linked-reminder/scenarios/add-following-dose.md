---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Advanced settings of a time based reminder and chooses Add reminder for following dose
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The User enters the dosage and the delay
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product creates a linked reminder following that reminder
  kind: product
  actor: user
  entities:
  - {entity: linked-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Delay]}
  - {entity: time-based-reminder, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
---

# Add a following dose

## Trigger

The User takes a second dose a set time after the first.

## Outcome

The linked reminder notifies its delay after the first dose is taken or skipped.
