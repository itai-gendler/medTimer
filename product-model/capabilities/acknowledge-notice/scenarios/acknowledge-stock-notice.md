---
kind: primary
routes:
  app: Android app
steps:
- text: The User dismisses an out-of-stock or expiration notification
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Type]}
  contexts:
    app:
      place: android-app::stock-notification
- text: The Product marks the notice acknowledged
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Acknowledged, facts: [Taken or skipped time]}
  contexts:
    app:
      place: android-app::stock-notification
---

# Dismiss a stock notification

## Trigger

The User has seen the notice.

## Outcome

The notice is acknowledged.
