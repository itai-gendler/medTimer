---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens Advanced settings of a linked reminder and chooses Add reminder for following dose
  kind: actor
  actor: user
  entities:
  - {entity: linked-reminder, as: followed, effect: reads, facts: [Dosage]}
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
- text: The Product creates a linked reminder following the linked reminder
  kind: product
  actor: user
  entities:
  - {entity: linked-reminder, as: following, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Delay]}
  - {entity: linked-reminder, as: followed, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
---

# Chain a following dose

## Trigger

The User takes a sequence of doses, each some hours after the previous one.

## Outcome

The chain notifies dose after dose, each after its delay.
