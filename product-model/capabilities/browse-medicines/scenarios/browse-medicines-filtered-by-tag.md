---
kind: alternative
routes:
  app: Android app
steps:
- text: A tag filter is set
  kind: condition
  entities:
  - {entity: settings, effect: reads, facts: [Tag filter]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The User opens the Medicine tab
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product lists only the medicines carrying at least one of the selected tags
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name, Position]}
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: settings, effect: reads, facts: [Tag filter]}
  contexts:
    app:
      place: android-app::medicines
---

# Browse medicines filtered by tag

## Trigger

The User has filtered by tags and opens the Medicine tab.

## Outcome

Only medicines with a selected tag are listed.
