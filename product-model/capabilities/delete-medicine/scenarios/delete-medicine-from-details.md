---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Delete in the medicine menu and confirms
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The Product deletes the medicine and its reminders and returns to the list
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

# Delete an open medicine

## Trigger

The User is looking at the medicine they want to remove.

## Outcome

The medicine is deleted and the list is shown.
