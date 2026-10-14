---
kind: primary
routes:
  app: Android app
steps:
- text: The User deselects a tag in the Tags of the medicine
  kind: actor
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine-tags
- text: The Product takes the tag off the medicine
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-tags
---

# Deselect a tag of a medicine

## Trigger

A medicine no longer belongs to a group.

## Outcome

The medicine no longer carries the tag; its past events keep the tags they were raised with.
