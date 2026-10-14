---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Reschedule reminder on a raised event and picks a time
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product moves the event to that time and notifies it then
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, facts: [Reminded time]}
  contexts:
    app:
      place: android-app::overview
---

# Reschedule a raised dose

## Trigger

The User wants to take the dose later at a known time.

## Outcome

The dose notifies again at the chosen time.
