---
kind: primary
routes:
  app: Android app
steps:
- text: The User changes the time and the dosage of a reminder on the medicine
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The User leaves the medicine
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The Product keeps the new time and dosage
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::medicine
---

# Change time and dosage

## Trigger

The dose or its time changes.

## Outcome

The reminder notifies at the new time with the new dosage; past events keep theirs.

## Edge cases

- For a linked reminder the field is its delay.
