---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Weekend mode and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Weekend mode, Weekend days, Weekend start time, Weekend end time]}
  contexts:
    app:
      place: android-app::weekend-mode-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Weekend mode, Weekend days, Weekend start time, Weekend end time]}
  contexts:
    app:
      place: android-app::weekend-mode-settings
---

# Weekend mode

## Trigger

The User sleeps longer on some days.

## Outcome

Reminders falling in the range on those days notify at its end.
