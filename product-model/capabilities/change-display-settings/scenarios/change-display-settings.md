---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Display settings and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Big notification buttons, Combine same time notifications, Relative date/time, Show taken time in overview, Show reminded time in overview, Show stock changes in overview, Use system setting for date/time format, Theme]}
  contexts:
    app:
      place: android-app::display-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Big notification buttons, Combine same time notifications, Relative date/time, Show taken time in overview, Show reminded time in overview, Show stock changes in overview, Use system setting for date/time format, Theme]}
  contexts:
    app:
      place: android-app::display-settings
---

# Display settings

## Trigger

The User wants the app to look or notify differently.

## Outcome

Notifications and the Overview follow the new display settings.
