---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Clear dates
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Production date, Expiration date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product removes the production and expiration dates
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Production date, Expiration date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
---

# Clear the dates

## Trigger

The dates no longer apply.

## Outcome

The medicine has no production or expiration date.
