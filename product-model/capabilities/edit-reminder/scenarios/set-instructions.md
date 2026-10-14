---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens Dosing instructions and writes instructions or picks a sample
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Instructions]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the instructions
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Instructions]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Set dosing instructions

## Trigger

A dose must be taken in a particular way.

## Outcome

The instructions appear with the reminder.
