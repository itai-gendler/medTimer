---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Analysis and picks Charts and a range of 1 to 30 days
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::analysis
- text: The Product shows taken versus skipped doses for the range and overall, and a per-day bar chart per medicine in its color
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Reminded time]}
  - {entity: medicine, effect: reads, facts: [Name, Color]}
  contexts:
    app:
      place: android-app::analysis
---

# View charts

## Trigger

The User wants to see how well they kept to their doses.

## Outcome

The charts summarise taken and skipped doses.
