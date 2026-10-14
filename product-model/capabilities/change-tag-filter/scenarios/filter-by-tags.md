---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens the tag filter from the title bar and selects tags
  kind: actor
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: settings, effect: reads, facts: [Tag filter]}
  contexts:
    app:
      place: android-app::tag-filter
- text: The Product keeps the selection and shows only medicines and events carrying one of the selected tags
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Tag filter]}
  - {entity: medicine, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::tag-filter
---

# Filter by tags

## Trigger

The User looks after the medicines of one person among several.

## Outcome

The lists show only the selected tags' medicines and events until the filter is cleared.

## Edge cases

- The filter is offered only once a tag exists.
- Charts and the calendar of the analysis are not filtered by tags.
