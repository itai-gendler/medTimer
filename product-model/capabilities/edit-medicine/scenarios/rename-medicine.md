---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens the medicine and changes its name, picks an icon or edits its notes
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name, Icon, Notes]}
  contexts:
    app:
      place: android-app::medicine
- text: The User leaves the medicine
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The Product keeps the changed name, icon and notes
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: changes, facts: [Name, Icon, Notes]}
  contexts:
    app:
      place: android-app::medicine
---

# Rename a medicine, change its icon or notes

## Trigger

The User wants to correct how a medicine is named or recognised.

## Outcome

The medicine carries its new name, icon and notes; events already in the history keep the name they were raised with.
