---
kind: alternative
routes:
  app: Android app
steps:
- text: The User deselects every tag in the tag filter
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Tag filter]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::tag-filter
- text: The Product shows everything again
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Tag filter]}
  contexts:
    app:
      place: android-app::tag-filter
---

# Clear the tag filter

## Trigger

The User wants to see everything again.

## Outcome

No tag filter is applied.
