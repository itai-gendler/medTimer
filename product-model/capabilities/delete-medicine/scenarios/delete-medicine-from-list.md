---
kind: primary
routes:
  app: Android app
steps:
- text: The User swipes the medicine away and confirms
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicines
- text: The Product deletes the medicine and its reminders
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: removes}
  - {entity: time-based-reminder, effect: removes, with: medicine}
  - {entity: linked-reminder, effect: removes, with: medicine}
  - {entity: interval-reminder, effect: removes, with: medicine}
  - {entity: windowed-interval-reminder, effect: removes, with: medicine}
  - {entity: out-of-stock-reminder, effect: removes, with: medicine}
  - {entity: expiration-reminder, effect: removes, with: medicine}
  contexts:
    app:
      place: android-app::medicines
---

# Delete a medicine from the list

## Trigger

The User stopped taking the medicine.

## Outcome

The medicine and its reminders are gone; its past events remain in the history.

## Edge cases

- Declining the confirmation keeps the medicine.
