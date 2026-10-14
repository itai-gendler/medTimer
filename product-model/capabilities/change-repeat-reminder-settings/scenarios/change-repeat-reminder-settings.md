---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Repeat reminders and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Repeat reminders, Number of repetitions, Time between repetitions]}
  contexts:
    app:
      place: android-app::repeat-reminders-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Repeat reminders, Number of repetitions, Time between repetitions]}
  contexts:
    app:
      place: android-app::repeat-reminders-settings
---

# Repeat reminders

## Trigger

The User wants reminders to behave differently.

## Outcome

The changed settings apply to later reminders.
