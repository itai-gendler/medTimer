---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Deactivate all reminders in the medicine menu
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The Product disables every reminder of the medicine
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Enabled]}
  - {entity: linked-reminder, effect: changes, facts: [Enabled]}
  - {entity: interval-reminder, effect: changes, facts: [Enabled]}
  - {entity: windowed-interval-reminder, effect: changes, facts: [Enabled]}
  - {entity: out-of-stock-reminder, effect: changes, facts: [Enabled]}
  - {entity: expiration-reminder, effect: changes, facts: [Enabled]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
---

# Deactivate a medicine's reminders

## Trigger

The User pauses a medicine completely.

## Outcome

No reminder of the medicine notifies; the medicine is marked inactive in the list.
