---
kind: primary
routes:
  app: Android app
steps:
- text: The User deletes a tag in the Tags of a medicine and confirms
  kind: actor
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-tags
- text: The Product deletes the tag, takes it off every medicine and out of the tag filter
  kind: product
  actor: user
  entities:
  - {entity: tag, effect: removes}
  - {entity: settings, effect: changes, facts: [Tag filter]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-tags
---

# Delete a tag

## Trigger

A group is no longer needed.

## Outcome

No medicine carries the tag any more.
