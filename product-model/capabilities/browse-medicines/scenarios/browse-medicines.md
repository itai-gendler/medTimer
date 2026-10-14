---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens the Medicine tab
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product lists every medicine in its position with its reminder times, stock, estimated run out date and tags
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name, Icon, Color, Stock amount, Unit, Estimated run out date, Expiration date, Position]}
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: time-based-reminder, effect: reads, facts: [Time, Enabled]}
  contexts:
    app:
      place: android-app::medicines
---

# Browse the medicine list

## Trigger

The User wants to see their medicines.

## Outcome

Every medicine is listed in order; a medicine whose stock is at an out-of-stock threshold or past its expiration date carries a warning, and one whose reminders are all disabled is marked inactive.

## Edge cases

- A medicine whose stock is not tracked shows no stock or run-out date.
- When the stock does not run out within the simulated period, the run-out date reads "After" the last simulated day.
