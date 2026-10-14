---
kind: alternative
routes:
  app: Android app
steps:
- text: The User asks for a new out-of-stock reminder in the stock settings, or picks that type when adding a reminder
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The User enters the threshold and chooses once, always or daily below it, with a time for daily
  kind: actor
  actor: user
  entities:
  - {entity: out-of-stock-reminder, effect: reads, facts: [Reminder threshold, Out of stock reminder, Time]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product creates the out of stock reminder
  kind: product
  actor: user
  entities:
  - {entity: out-of-stock-reminder, effect: creates, facts: [Enabled, Reminder threshold, Out of stock reminder, Time]}
  contexts:
    app:
      place: android-app::new-reminder
---

# Add an out of stock reminder

## Trigger

The User wants to know in time when to buy more.

## Outcome

The medicine reminds about its stock as chosen.

## Edge cases

- The threshold starts at the current stock, or 1 when there is none.
