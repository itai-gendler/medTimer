---
kind: primary
routes:
  app: Android app
steps:
- text: The User drags the medicine to a new place
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Position]}
  contexts:
    app:
      place: android-app::medicines
- text: The Product keeps the medicine at that position
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Position]}
  contexts:
    app:
      place: android-app::medicines
---

# Move a medicine

## Trigger

The User wants the list in another order.

## Outcome

The medicine stays where it was dropped.
