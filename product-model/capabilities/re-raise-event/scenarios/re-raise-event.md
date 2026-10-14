---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Re-raise event on a taken event and confirms
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product deletes the event and gives its deducted dosage back to the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: removes, from: Taken}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
- text: The Product schedules the reminder again, so it notifies for that time
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Time]}
  contexts:
    app:
      place: android-app::overview
---

# Re-raise a taken event

## Trigger

The User answered a reminder by mistake and wants to be reminded again.

## Outcome

The event is gone and its reminder is raised again.

## Edge cases

- A skipped event is re-raised the same way, without a stock change.
- Additional doses cannot be re-raised; they have no reminder.
