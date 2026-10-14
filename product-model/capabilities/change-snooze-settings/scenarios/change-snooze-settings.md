---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Snooze settings and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Snooze duration, Location-based snooze]}
  contexts:
    app:
      place: android-app::snooze-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Snooze duration, Location-based snooze]}
  contexts:
    app:
      place: android-app::snooze-settings
---

# Snooze settings

## Trigger

The User wants reminders to behave differently.

## Outcome

The changed settings apply to later reminders.
