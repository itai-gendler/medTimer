---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Reschedule reminder on a dose scheduled later and picks a time
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product raises the dose for the chosen time and notifies it then
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  contexts:
    app:
      place: android-app::overview
---

# Reschedule a scheduled dose

## Trigger

A coming dose is better taken at another time today.

## Outcome

The dose notifies at the chosen time instead of its scheduled time.
