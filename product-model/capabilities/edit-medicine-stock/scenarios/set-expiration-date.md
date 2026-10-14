---
kind: alternative
routes:
  app: Android app
steps:
- text: The User picks the production date and the expiration date
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Production date, Expiration date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product keeps both dates and marks the medicine once the expiration date has passed
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Production date, Expiration date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
---

# Set production and expiration dates

## Trigger

The User records when the medicine expires.

## Outcome

The dates are kept; after expiry the medicine shows an expired mark.
