---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Clear all history and confirms
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product deletes every event and schedules the reminders anew
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, as: raised, effect: removes, from: Raised}
  - {entity: reminder-event, as: snoozed-until-home, effect: removes, from: Snoozed until home}
  - {entity: reminder-event, as: taken, effect: removes, from: Taken}
  - {entity: reminder-event, as: skipped, effect: removes, from: Skipped}
  - {entity: reminder-event, as: acknowledged, effect: removes, from: Acknowledged}
  - {entity: reminder-event, as: deleted, effect: removes, from: Deleted}
  contexts:
    app:
      place: android-app
---

# Clear all history

## Trigger

The User wants to start the history afresh.

## Outcome

The history is empty; this cannot be undone.
