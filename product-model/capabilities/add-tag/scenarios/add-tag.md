---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Tags of the medicine, chooses Add tag and enters a name
  kind: actor
  actor: user
  entities:
  - {entity: tag, effect: reads, facts: [Name]}
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine-tags
- text: The Product creates the tag and gives it to the medicine
  kind: product
  actor: user
  entities:
  - {entity: tag, effect: creates, facts: [Name]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine-tags
---

# Add a tag to a medicine

## Trigger

The User wants to group medicines, for example by the person who takes them.

## Outcome

The tag exists and the medicine carries it.
