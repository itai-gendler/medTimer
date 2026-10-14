---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Create calendar entry
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Estimated run out date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product opens the calendar app with an entry titled with the medicine name on the run-out date
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name, Estimated run out date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
---

# Create a calendar entry for the run-out date

## Trigger

The User wants to be reminded in their calendar to buy more in time.

## Outcome

The calendar app shows the prepared entry for the User to save.

## Edge cases

- The control is offered only while a run-out date within the simulated period exists.
