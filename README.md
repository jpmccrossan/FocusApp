# Focus — Personal Productivity PWA

A lightweight, privacy-first productivity app that lives on your iPhone home screen. No accounts, no backend, no subscriptions. Everything stays on your device.

**Live app → [jpmccrossan.github.io/FocusApp/focus.html](https://jpmccrossan.github.io/FocusApp/focus.html)**

---

## Features

### Daily Dashboard
- Morning / afternoon / evening greeting
- Progress ring showing % of today's tasks completed
- At-a-glance stats: tasks done, habits logged, active goals
- Today's calendar events pulled from iCloud in a scrollable strip

### Tasks
- Add tasks with an optional deadline and notes
- Link any task to a long-term goal
- Deadline labels: overdue (red), due soon (amber), upcoming (grey)
- Tap to mark done; tap ✎ to edit in place
- 📅 button exports any task as a `.ics` file to add directly to your iPhone Calendar

### Habits
- Custom emoji icon per habit
- Flexible recurrence schedules:
  - **Every day**
  - **Weekly** — tap to select specific days (Mo / Tu / We / Th / Fr / Sa / Su)
  - **Monthly** — pick a day of the month
- 7-day dot history (unscheduled days automatically faded)
- Streak counter that only counts scheduled days — a rest day won't break your streak
- Habits split into **Due today** and **Not scheduled today** sections
- Notes field for motivation or context
- Tap ✎ to edit any habit

### Long-term Goals
- Category tags: Work, Health, Learning, Personal, Finance
- Deadline with days-remaining countdown
- Progress slider (0–100%)
- Linked task counter (x/y tasks done)
- Notes field for strategy or context
- Mark complete; tap ✎ to edit

### iPhone Calendar Sync
- Reads today's events from your iCloud public calendar (ICS format)
- No OAuth, no API keys, no accounts — just a public link
- Auto-syncs on app open; manual re-sync via 📅 button

### Data & Export
- Full CSV export — tasks, habits, and goals in one file including notes, streaks, deadlines, and linked goals
- Clear all data option in Setup

### App
- Installable PWA — runs fullscreen from your iPhone home screen
- Works offline after first load via Service Worker cache

---

## Install on iPhone

1. Open **Safari** and go to the live app link above
2. Tap the **Share** button → **Add to Home Screen**
3. Tap **Add**

> Must use Safari. Chrome and Firefox on iOS do not support PWA installation.

---

## Calendar Setup

1. Open the **Calendar** app on iPhone
2. Tap **ⓘ** next to your calendar → **Share Calendar**
3. Toggle **Public Calendar** ON → tap **Share Link** → Copy
4. In the Focus app → **Setup** tab → **Configure** → paste the `webcal://` link → Save

Events sync automatically each time you open the app.

---

## Tech Stack

| | |
|---|---|
| **Type** | Single-file PWA (HTML + CSS + JS) |
| **Storage** | `localStorage` — all data stays on device |
| **Calendar** | iCloud ICS parsing — no OAuth, no API keys |
| **Offline** | Service Worker with cache-first strategy |
| **Fonts** | Playfair Display + DM Mono via Google Fonts |
| **Hosting** | GitHub Pages |

No frameworks, no build step, no dependencies. The entire app is one `.html` file.

---

## Development

To run locally:

```bash
git clone https://github.com/jpmccrossan/FocusApp.git
cd FocusApp
# Open focus.html directly in a browser, or serve with:
npx serve .
```

To deploy an update:

```bash
git add focus.html
git commit -m "Update app"
git push
```

GitHub Pages redeploys in ~30 seconds. The app on your iPhone picks up the new version on next open with an internet connection.

---

## Privacy

- No data leaves your device
- No analytics, no tracking, no ads
- Calendar sync fetches your iCloud ICS URL directly — nothing stored server-side
- The CORS proxy (`allorigins.win`) is only used if the direct ICS fetch fails; it sees the calendar URL but not your app data

---

## License

MIT — do whatever you like with it.
