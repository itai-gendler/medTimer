---
kind: alternative
routes:
  app: Android app
steps:
- text: The User asks for a new expiration date reminder in the stock settings, or picks that type when adding a reminder
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Expiration date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The User enters the days before expiration, once or daily, and the time
  kind: actor
  actor: user
  entities:
  - {entity: expiration-reminder, effect: reads, facts: [Expiration reminder, Remind days before expiration, Time]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product creates the expiration reminder
  kind: product
  actor: user
  entities:
  - {entity: expiration-reminder, effect: creates, facts: [Enabled, Expiration reminder, Remind days before expiration, Time]}
  contexts:
    app:
      place: android-app::new-reminder
---

# Add an expiration reminder

## Trigger

The User wants to replace the medicine before it expires.

## Outcome

The medicine reminds about its expiration as chosen.
