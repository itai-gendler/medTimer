---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Export as CSV or Export as PDF under Medicine data in the options menu
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app
- text: The Product writes each medicine, narrowed by the tag filter, with the dosage and time of its reminders and opens the share sheet
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time, Enter dosage when taken]}
  - {entity: settings, effect: reads, facts: [Tag filter]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app
---

# Export medicines

## Trigger

The User wants a list of what they take.

## Outcome

The medicine list is shared.
