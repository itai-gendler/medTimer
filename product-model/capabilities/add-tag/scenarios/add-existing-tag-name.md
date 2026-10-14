---
kind: edge
routes:
  app: Android app
steps:
- text: The User adds a tag with the name of an existing tag
  kind: actor
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine-tags
- text: The Product gives the existing tag to the medicine instead of creating another
  kind: product
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-tags
---

# Add a tag whose name exists

## Trigger

The User types a name already in use.

## Outcome

No duplicate tag is created; the medicine carries the existing tag.
