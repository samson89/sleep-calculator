# Sleep Calculator

A simple, dark-mode web page that helps you time your sleep around 90-minute sleep cycles, so you wake up between cycles instead of in the middle of one.

## Features

- **Go to bed at…** — get wake-up times from the current time, or tap the time to choose a different bedtime (**↺ Now** goes back to the current time); from 6 sleep cycles at the top down to 1 cycle at the bottom (the same order as **Wake up at…**). This is the first tab and the page always opens on it.
- **Wake up at…** — pick the time you want to wake up (8:00 AM to start; the app remembers the last time you set) and get bedtimes from 6 sleep cycles at the top down to 1 cycle at the bottom. The soonest bedtime that hasn't passed yet has a green border and a live countdown (e.g. "in 45 mins").
- **Time to fall asleep** — shown as "🌙 15 min to fall asleep" under the time. Tap it to open − / + buttons that change it 1 minute at a time (default 15 minutes, range 0–120); tap the value to close it again.
- Each result shows the total sleep and number of cycles, e.g. `7h 30m of sleep · 5 cycles`. 5 and 6 cycles are marked **Recommended**.
- Dark mode only, with a warm accent colour and text that meets WCAG AA contrast.
- Uses your device's 12- or 24-hour clock setting.
- Remembers your settings on your device.
- The **Sleep Calculator** title links back to the app's home page, like a site logo.
- **Tap a time to set an alarm** (iPhone, iPad and Mac) — uses an Apple Shortcut; see below.

## How it works

- **Bedtime** = wake-up time − (cycles × 90 min) − time to fall asleep
- **Wake-up time** = now + time to fall asleep + (cycles × 90 min)

Cycle length varies from person to person; treat the results as a guide, not medical advice.

## Tap-to-set-alarm (iPhone, iPad and Mac)

On Apple devices, every time in the results is a link. Tapping it runs the **Set Sleep Alarm** Shortcut, which creates an alarm at that time:

- **Go to bed at…** tab: sets a wake-up alarm.
- **Wake up at…** tab: sets an alarm at the bedtime, as a reminder to go to bed.

On other devices (Android, Windows, Linux) the times are shown as plain text, because the Shortcuts app isn't available there.

### How the link works

Tapping a time opens a link like this:

```
shortcuts://x-callback-url/run-shortcut?name=Set%20Sleep%20Alarm&input=text&text=6:15%20AM&x-success=https%3A%2F%2Fsamson89.github.io%2Fsleep-calculator%2F&x-cancel=…&x-error=…
```

iOS briefly switches to the Shortcuts app to run the Shortcut, then the `x-success` address brings you back to the page (`x-cancel` and `x-error` do the same if the Shortcut is cancelled or fails).

The time is always sent in English 12-hour format (`6:15 AM`, `9:45 PM`), even if your device uses a 24-hour clock or another language, because that's the format the Shortcut reads reliably.

### Set up the Shortcut (one time)

Build it in the Shortcuts app on your iPhone (or Mac):

1. Tap **+** to create a new Shortcut and name it exactly **Set Sleep Alarm** (the name must match).
2. Add the action **Get Dates from Input**, using **Shortcut Input**.
3. Add the action **Create Alarm**, and set its time to the **Dates** from the previous step.
4. Tap **Done**.

The first time you tap a time, iOS may ask for permission to open Shortcuts and to let the Shortcut create alarms. Allow both.

## Add it to your Home Screen

In Safari on iPhone or iPad, open the page, tap **Share → Add to Home Screen**. The icon is `apple-touch-icon.png` (a 🌙 on the app's dark background). iOS saves the icon when you add the page, so after the icon changes, remove the old Home Screen icon and add it again.

## Run it

It's a single `index.html` file with no dependencies. Open it in any browser.

## Put it online with GitHub Pages

1. In this repository on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose the **main** branch and the **/ (root)** folder, then click **Save**.
4. After a minute or two, the site will be live at `https://samson89.github.io/sleep-calculator/`.
