---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Delete on an acknowledged notice or refill and confirms
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Type]}
  contexts:
    app:
      place: android-app::overview
- text: The Product deletes the event from the history
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Acknowledged, to: Deleted, facts: []}
  contexts:
    app:
      place: android-app::overview
---

# Delete an acknowledged notice

## Trigger

A notice is no longer of interest.

## Outcome

The notice is gone from the Overview.
