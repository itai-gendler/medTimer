---
kind: alternative
routes:
  app: Android app
steps:
- text: Exact reminders are off and the warning has not been dismissed
  kind: condition
  entities:
  - {entity: settings, effect: reads, facts: [Exact reminders]}
  contexts:
    app:
      place: android-app::overview
- text: The User chooses Enable on the exact reminders warning in the Overview
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::overview
- text: The Product switches exact reminders on and hides the warning
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Exact reminders]}
  contexts:
    app:
      place: android-app::overview
---

# Enable exact reminders from the Overview

## Trigger

The Overview warns that reminders may come late.

## Outcome

Reminders are raised at the exact minute.
