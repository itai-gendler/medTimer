---
id: medtimer
summary: An open-source Android medication reminder that keeps medicines, flexible reminders, a taken/skipped dose history and medicine stock on the device, fully offline.
category: health
tags:
- medication-reminder
- health
- android
- offline
- privacy
authors:
- name: Florian Fetz
  url: https://github.com/Futsch1
license: MIT
languages:
- en
- ar
- bg
- cs
- da
- de
- el
- es
- et
- fi
- fr
- he
- hu
- is
- it
- nb-NO
- nl
- pl
- pt
- pt-BR
- ru
- sv
- ta
- tr
- uk
- zh-CN
- zh-TW
limitations:
- 'All data stays on the device: there is no account or sign-in, nothing needs an internet connection, and data moves to another device only through a backup file the person saves or shares.'
- Snooze until home needs Google Play Services, so the variant without them (the FOSS build) has no location-based snooze; otherwise both variants are the same.
- 'Reminders reach the person as Android notifications: without the notification permission doses are still recorded as raised, but no notification appears.'
- A medicine's stock is counted from the first number in a dose's dosage; a dosage without a number changes no stock.
- Level estimates come from a simple one-compartment model of taken doses and are not medical advice.
references:
- kind: doc
  role: intent
  target: README.md
  title: README
- kind: doc
  role: intent
  target: docs/UseCases.md
  title: Use cases
- kind: doc
  role: context
  target: docs/reminder_flow.md
  title: Flow of reminders
- kind: doc
  role: context
  target: CONTEXT.md
  title: Glossary
- kind: doc
  role: intent
  target: fastlane/metadata/android/en-US/full_description.txt
  title: Store description
---

# MedTimer

MedTimer reminds a person to take their medicines and keeps the history of every dose on their Android
phone or tablet. They keep a list of medicines, each with its dosage reminders: at set times of day, on
chosen weekdays, days of the month or in cycles of active and pause days, at a fixed interval, at intervals
within a daily window, or a set delay after the previous dose. When a reminder is due, a notification (or
a full-screen alarm) lets them mark the dose taken, skip it or snooze it, also until they get home. Every
reminder becomes an event in the history, which the Overview shows day by day beside the doses still
scheduled, and which can be corrected, deleted, analysed in charts, a table, a calendar and estimated
levels, and exported as CSV or PDF. Medicines can carry a stock that each taken dose reduces, with
out-of-stock and expiration reminders, and tags that let one phone keep the medicines of several people
apart. Settings shape notifications, snoozing, repeats, a weekend mode and privacy, and medicines, history
and settings are backed up to and restored from a JSON file.

## Intent

"MedTimer is an open-source medication reminder app designed to help you manage your medications and
pills effectively and with full control of your sensitive data." The README promises "Flexible &
Personalized Reminders" (breaks and specific days, weekend mode, snoozing and repeated reminders,
location-based snooze, extra doses, interval and windowed interval reminders, alarm reminders, stock and
expiration reminders), "Simple & Secure Data Management" (confirm or dismiss reminders "to record
medication adherence accurately", chart, table and calendar views, CSV export, JSON backup, stock tracking,
tags) and "Privacy & Offline Accessibility": "All data is stored securely on your device" and "No internet
connection required".
