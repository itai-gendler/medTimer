---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens the medicine stock settings and enters the amount, unit and refill size
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Stock amount, Unit, Refill size]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product keeps the stock and shows the estimated run out date
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Stock amount, Unit, Refill size]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
---

# Set the stock of a medicine

## Trigger

The User starts tracking how much of a medicine is left.

## Outcome

Stock is tracked: taken doses reduce it and the medicine list shows it with its run-out date.

## Edge cases

- Only non-negative numbers are accepted for the amount and refill size.
