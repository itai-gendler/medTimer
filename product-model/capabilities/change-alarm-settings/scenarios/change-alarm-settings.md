---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Alarm settings and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [No alarm sound when silent, No vibration when silent, Alarm ringtone]}
  contexts:
    app:
      place: android-app::alarm-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [No alarm sound when silent, No vibration when silent, Alarm ringtone]}
  contexts:
    app:
      place: android-app::alarm-settings
---

# Alarm settings

## Trigger

The User wants reminders to behave differently.

## Outcome

The changed settings apply to later reminders.
