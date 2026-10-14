---
kind: alternative
routes:
  app: Android app
steps:
- text: The device arrives at the home location while doses are snoozed until home
  kind: condition
  unattended: true
  entities:
  - {entity: settings, effect: reads, facts: [Home location]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product raises the snoozed doses again and notifies them
  kind: product
  entities:
  - {entity: reminder-event, effect: changes, from: Snoozed until home, to: Raised, facts: []}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Notify again on arriving home

## Trigger

The User comes home after snoozing until home.

## Outcome

The snoozed doses notify again.
