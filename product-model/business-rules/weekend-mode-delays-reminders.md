---
appliesTo:
- {type: capability, id: raise-reminder}
- {type: entity, id: settings, facts: [Weekend mode, Weekend days, Weekend start time, Weekend end time]}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/WeekendModeSchedulingDecorator.kt#WeekendModeSchedulingDecorator
---

# Weekend mode delays reminders to the end of its range

While weekend mode is on, a reminder due on a weekend day between the weekend start and end time notifies at the end time instead.
