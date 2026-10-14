---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Activate all reminders in the medicine list menu
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product enables every reminder of every medicine the list shows
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: time-based-reminder, effect: changes, facts: [Enabled]}
  - {entity: linked-reminder, effect: changes, facts: [Enabled]}
  - {entity: windowed-interval-reminder, effect: changes, facts: [Enabled]}
  - {entity: out-of-stock-reminder, effect: changes, facts: [Enabled]}
  - {entity: expiration-reminder, effect: changes, facts: [Enabled]}
  - {entity: interval-reminder, effect: changes, facts: [Enabled, Interval start time]}
  contexts:
    app:
      place: android-app::medicines
---

# Activate the reminders of every listed medicine

## Trigger

The User resumes everything, for example after a break.

## Outcome

Every listed medicine notifies again; with a tag filter set, only the filtered medicines are affected.
