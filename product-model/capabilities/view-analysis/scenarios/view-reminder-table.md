---
kind: alternative
routes:
  app: Android app
steps:
- text: The User picks the table and types a search
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::analysis
- text: The Product lists every taken or skipped event with taken time, medicine, dosage and reminded time, narrowed by the search and the tag filter
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time, Taken or skipped time, Tags]}
  - {entity: settings, effect: reads, facts: [Tag filter]}
  - {entity: medicine, effect: reads, facts: []}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::analysis
---

# Search the reminder table

## Trigger

The User looks for particular doses.

## Outcome

Matching events are listed and can be sorted.
