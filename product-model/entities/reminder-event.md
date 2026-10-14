---
domain: overview
references:
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/ReminderEvent.kt#ReminderEvent
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/ReminderEventEntity.kt
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/ReminderEventFactory.kt#buildReminderEvent
- kind: doc
  role: context
  target: CONTEXT.md
---

# Reminder event

A record in the history that a reminder was raised for a medicine at a time and how it was answered, or
that an additional dose was taken or the stock refilled. It keeps its own copy of the medicine's name,
dosage and tags, so it outlives changes to the medicine and its reminders.

## Information kept

- **Medicine name** — the medicine as named when the event was raised, with the cycle day for a cyclic reminder
- **Dosage** — the dosage of the dose; for an out-of-stock notice the stock left, for an expiration notice the expiration date, for a refill the stock before and after
- **Type** — dose, additional dose, out of stock, expiration or stock refill
- **Reminded time** — when the reminder was raised, or the dose time of an additional dose
- **Taken or skipped time** — when the dose was taken, skipped or acknowledged
- **Notes** — notes added to the event
- **Tags** — the medicine's tags when the event was raised
- **Color and icon** — the medicine's color and icon when the event was raised
- **Stock before** — the medicine's stock before the dose, when stock is tracked
- **Stock after** — the medicine's stock after the dose, when stock is tracked
- **Remaining repeats** — how many more times an unanswered reminder is repeated
- **Cannot be skipped** — whether the dose can only be answered by taking it
- **Asks for dosage** — whether marking it taken asks for the dosage actually taken

## States

### Raised

The reminder notified, or is due to be answered, and the person has not answered it yet. Snoozing keeps
it raised.

### Snoozed until home

The person snoozed it until they arrive at their home location.

### Taken

The dose was taken.

### Skipped

The dose was skipped.

### Acknowledged

An out-of-stock or expiration notice was seen, or the stock was refilled.

### Deleted

The person deleted the event: it no longer appears in the history, analysis or exports, and its reminder
is not raised again for that time.
