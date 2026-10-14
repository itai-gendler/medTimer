---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Activate all reminders in the medicine menu
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The Product enables every reminder of the medicine, moving a continuous interval reminder's interval start time to today
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Enabled]}
  - {entity: linked-reminder, effect: changes, facts: [Enabled]}
  - {entity: windowed-interval-reminder, effect: changes, facts: [Enabled]}
  - {entity: out-of-stock-reminder, effect: changes, facts: [Enabled]}
  - {entity: expiration-reminder, effect: changes, facts: [Enabled]}
  - {entity: interval-reminder, effect: changes, facts: [Enabled, Interval start time]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
---

# Activate a medicine's reminders

## Trigger

The User resumes a medicine they had paused.

## Outcome

All reminders of the medicine notify again, keeping their configuration.
