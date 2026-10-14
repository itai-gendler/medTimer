---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Delete on a taken event, or swipes it away, and confirms
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product deletes the event from the history and gives its deducted dosage back to the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Taken, to: Deleted, facts: []}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Delete a taken event

## Trigger

An event is wrong and should not count.

## Outcome

The event no longer appears in the history, analysis or exports.
