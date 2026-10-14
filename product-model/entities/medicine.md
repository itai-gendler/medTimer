---
domain: medicine
relations:
- entity: time-based-reminder
  verb: has
  cardinality: one-to-many
- entity: linked-reminder
  verb: has
  cardinality: one-to-many
- entity: interval-reminder
  verb: has
  cardinality: one-to-many
- entity: windowed-interval-reminder
  verb: has
  cardinality: one-to-many
- entity: out-of-stock-reminder
  verb: has
  cardinality: one-to-many
- entity: expiration-reminder
  verb: has
  cardinality: one-to-many
- entity: tag
  verb: is tagged with
  cardinality: many-to-many
references:
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/Medicine.kt#Medicine
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/MedicineEntity.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/medicineSettings/MedicineDataStore.kt#MedicineDataStore
---

# Medicine

A medicine or pill the person takes, with its reminders and, when they track it, its stock.

## Information kept

- **Name** — what the medicine is called
- **Icon** — an optional icon shown with the medicine
- **Notes** — free notes about the medicine
- **Color** — an optional color shown with the medicine and the events it raises
- **Notification priority** — Default, High or High + Alarm; it chooses the notification settings its reminders use and whether they show as alarms
- **Cannot be skipped** — whether its doses can only be answered by taking them
- **Stock amount** — how much of the medicine is left; zero together with no out-of-stock reminder means stock is not tracked
- **Unit** — the unit the stock is counted in
- **Refill size** — how much one refill adds to the stock
- **Production date** — when the medicine was produced, if entered
- **Expiration date** — when the medicine expires, if entered
- **Half-life** — hours for its level to halve, used for the level estimate
- **Time to peak** — hours from taking a dose to its highest level, used for the level estimate
- **Position** — its place in the medicine list
- **Estimated run out date** — the day its stock is expected to reach zero, derived from its scheduled doses
