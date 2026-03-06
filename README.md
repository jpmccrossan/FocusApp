# Focus — Personal Productivity PWA

A lightweight, privacy-first productivity app that lives on your iPhone home screen. No accounts, no backend, no subscriptions. Everything stays on your device.

**Live app → [jpmccrossan.github.io/FocusApp/focus.html](https://jpmccrossan.github.io/FocusApp/focus.html)**

---

## Features

- **Daily dashboard** — morning/afternoon/evening greeting, progress ring, at-a-glance stats
- **Task tracking** — add tasks, link them to long-term goals, mark done
- **Habit streaks** — log daily habits, track 7-day history and current streak
- **Long-term goals** — set goals with deadlines, categories, and a progress slider
- **iPhone Calendar sync** — reads today's events from your iCloud public calendar (ICS)
- **Add tasks to Calendar** — exports any task as a `.ics` file to drop into your iPhone Calendar
- **CSV export** — full data export of tasks, habits, and goals
- **Works offline** — service worker caches the app after first load

---

## Install on iPhone

1. Open **Safari** and navigate to the live app link above
2. Tap the **Share** button → **Add to Home Screen**
3. Tap **Add** — it will appear as a full-screen app icon

> Must use Safari. Chrome and Firefox on iOS do not support PWA installation.

---

## Calendar Setup

The app reads events from your iCloud calendar via a public ICS link.

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
| **Calendar** | iCloud ICS parsing (no OAuth, no API keys) |
| **Offline** | Service Worker with cache-first strategy |
| **Fonts** | Playfair Display + DM Mono via Google Fonts |
| **Hosting** | GitHub Pages |

No frameworks, no build step, no dependencies.

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

GitHub Pages redeploys in ~30 seconds.

---

## Privacy

- No data leaves your device
- No analytics, no tracking, no ads
- Calendar sync fetches your iCloud ICS URL directly — nothing is stored server-side
- The CORS proxy (`allorigins.win`) is only used if the direct ICS fetch fails; it sees the calendar URL but not your app data

---

## License

MIT — do whatever you like with it.
