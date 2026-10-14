---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Refill on the out-of-stock notification
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Refill size]}
  - {entity: reminder-event, as: notice, effect: reads, facts: [Medicine name]}
  contexts:
    app:
      place: android-app::stock-notification
- text: The Product adds the refill size to the stock and records a stock refill event
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  - {entity: reminder-event, as: refill, effect: creates, to: Acknowledged, facts: [Medicine name, Dosage, Type, Reminded time, Taken or skipped time, Tags, Color and icon]}
  contexts:
    app:
      place: android-app::stock-notification
- text: The Product acknowledges the out-of-stock notice and removes its notification
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, as: notice, effect: changes, from: Raised, to: Acknowledged, facts: [Taken or skipped time]}
  contexts:
    app:
      place: android-app::stock-notification
---

# Refill from an out-of-stock notification

## Trigger

An out-of-stock notification reminds the User to refill.

## Outcome

The stock is refilled and the notice is acknowledged.
