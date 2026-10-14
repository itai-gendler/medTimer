---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Export as CSV or Export as PDF under Event data in the options menu
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product writes every event except deleted ones and notices to the file, narrowed by the tag filter, and opens the share sheet
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time, Taken or skipped time, Tags, Notes]}
  - {entity: settings, effect: reads, facts: [Tag filter]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app
---

# Export events

## Trigger

The User needs a record of their doses.

## Outcome

The file is shared where the User chooses.

## Edge cases

- With a tag filter set the Product says that only data with matching tags is exported.
