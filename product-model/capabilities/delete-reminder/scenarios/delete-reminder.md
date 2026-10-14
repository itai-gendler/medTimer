---
kind: primary
routes:
  app: Android app
steps:
- text: The User swipes the reminder away on the medicine, or chooses Delete, and confirms
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The Product deletes the reminder and every linked reminder that follows it, directly or through others
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: removes}
  - {entity: linked-reminder, effect: removes, with: time-based-reminder}
  contexts:
    app:
      place: android-app::medicine
---

# Delete a reminder

## Trigger

A dose is no longer needed.

## Outcome

The reminder and its following doses are gone; their past events stay in the history.

## Edge cases

- Declining the confirmation keeps the reminder.
