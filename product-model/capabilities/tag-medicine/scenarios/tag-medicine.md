---
kind: primary
routes:
  app: Android app
steps:
- text: The User selects a tag in the Tags of the medicine
  kind: actor
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine-tags
- text: The Product gives the tag to the medicine
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-tags
---

# Select a tag for a medicine

## Trigger

A medicine belongs to an existing group.

## Outcome

The medicine carries the tag in the list, the Overview and its notifications.
