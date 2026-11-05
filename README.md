# Sleep Calculator

A simple, dark-mode web page that helps you time your sleep around 90-minute sleep cycles, so you wake up between cycles instead of in the middle of one.

## Features

- **Wake up at…** — pick the time you want to wake up and get bedtimes from 6 sleep cycles at the top down to 1 cycle at the bottom. The soonest bedtime that hasn't passed yet has a green border and a live countdown (e.g. "in 45 mins").
- **Go to bed now** — get wake-up times for 1–6 sleep cycles from the current time, earliest first.
- **Time to fall asleep** — shown as "🌙 15 min to fall asleep" under the time. Tap it to open − / + buttons that change it 1 minute at a time (default 15 minutes, range 0–120); tap the value to close it again.
- Each result shows the total sleep and number of cycles, e.g. `7h 30m of sleep · 5 cycles`. 5 and 6 cycles are marked **Recommended**.
- Dark mode only, with a warm accent colour and text that meets WCAG AA contrast.
- Uses your device's 12- or 24-hour clock setting.
- Remembers your settings on your device.

## How it works

- **Bedtime** = wake-up time − (cycles × 90 min) − time to fall asleep
- **Wake-up time** = now + time to fall asleep + (cycles × 90 min)

Cycle length varies from person to person; treat the results as a guide, not medical advice.

## Run it

It's a single `index.html` file with no dependencies. Open it in any browser.

## Put it online with GitHub Pages

1. In this repository on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose the **main** branch and the **/ (root)** folder, then click **Save**.
4. After a minute or two, the site will be live at `https://samson89.github.io/sleep-calculator/`.
