---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses By name, Ascending by creation date or Descending by creation date
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Position]}
  contexts:
    app:
      place: android-app::medicines
- text: The Product renumbers every medicine in that order
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Position]}
  contexts:
    app:
      place: android-app::medicines
---

# Sort the medicine list

## Trigger

The User wants the list sorted.

## Outcome

All medicines are listed in the chosen order, which stays until changed.
