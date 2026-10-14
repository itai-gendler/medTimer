---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens Medicine settings of the medicine
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Color, Notification priority, Cannot be skipped]}
  contexts:
    app:
      place: android-app::medicine-settings
- text: The User sets a color, the notification priority (Default, High or High + Alarm) or Medicine cannot be skipped
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-settings
- text: The Product keeps the new values for the medicine
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Color, Notification priority, Cannot be skipped]}
  contexts:
    app:
      place: android-app::medicine-settings
---

# Change color, priority or skipping of a medicine

## Trigger

The User wants a medicine to stand out, ring as an alarm or never be skipped.

## Outcome

The medicine's later reminders use its new priority and skipping rule; a new color shows on future events only.

## Edge cases

- High + Alarm shows the reminder as a full-screen alarm, which needs the system permission for full-screen notifications.
