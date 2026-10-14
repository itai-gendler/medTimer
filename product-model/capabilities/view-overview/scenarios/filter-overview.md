---
kind: alternative
routes:
  app: Android app
steps:
- text: The User selects Taken, Skipped, Scheduled or Raised in the filter row
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::overview
- text: The Product lists only events and doses in the selected states and remembers the filter
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
---

# Filter by state

## Trigger

The User looks for what is still open, or what was skipped.

## Outcome

Only the selected states are listed.
