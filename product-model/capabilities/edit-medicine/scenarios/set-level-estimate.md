---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens Medicine settings and enters the half-life and time to peak in hours
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Half-life, Time to peak]}
  contexts:
    app:
      place: android-app::medicine-settings
- text: The Product keeps both values; an empty entry clears one
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Half-life, Time to peak]}
  contexts:
    app:
      place: android-app::medicine-settings
---

# Set the level estimate of a medicine

## Trigger

The User wants to see the estimated level of a medicine in the analysis.

## Outcome

With both values set, the medicine appears in the estimated levels.
