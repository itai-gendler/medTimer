---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Notification and reminder settings and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Always play notification sound, Action when dismissing notification, Reminders cannot be skipped, Persistent reminders on lock screen, Exact reminders]}
  contexts:
    app:
      place: android-app::notification-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Always play notification sound, Action when dismissing notification, Reminders cannot be skipped, Persistent reminders on lock screen, Exact reminders]}
  contexts:
    app:
      place: android-app::notification-settings
---

# Notification and reminder settings

## Trigger

The User wants reminders to behave differently.

## Outcome

The changed settings apply to later reminders.

## Edge cases

- Always playing the sound and exact reminders each need a system permission the app asks the User to grant.
