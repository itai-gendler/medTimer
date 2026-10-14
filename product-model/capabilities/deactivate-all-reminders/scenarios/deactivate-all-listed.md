---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Deactivate all reminders in the medicine list menu
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product disables every reminder of every medicine the list shows
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: time-based-reminder, effect: changes, facts: [Enabled]}
  - {entity: linked-reminder, effect: changes, facts: [Enabled]}
  - {entity: interval-reminder, effect: changes, facts: [Enabled]}
  - {entity: windowed-interval-reminder, effect: changes, facts: [Enabled]}
  - {entity: out-of-stock-reminder, effect: changes, facts: [Enabled]}
  - {entity: expiration-reminder, effect: changes, facts: [Enabled]}
  contexts:
    app:
      place: android-app::medicines
---

# Deactivate the reminders of every listed medicine

## Trigger

The User pauses everything.

## Outcome

No listed medicine notifies until reactivated.
