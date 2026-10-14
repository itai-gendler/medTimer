---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Refill now
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Stock amount, Refill size]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product adds the refill size to the stock
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product records an acknowledged stock refill event showing the stock before and after
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: creates, to: Acknowledged, facts: [Medicine name, Dosage, Type, Reminded time, Taken or skipped time, Tags, Color and icon]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
---

# Refill from the stock settings

## Trigger

The User has bought more of the medicine.

## Outcome

The stock is higher by the refill size and the refill appears in the Overview.
