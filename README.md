CYCLE COMPANION
A private, offline-first PWA to help you show up for your partner every day.
-------------------------------------------------------------------------------

WHAT IT IS

Cycle Companion is a personal tool built for husbands and partners who want to
understand the menstrual cycle and know how to act at each stage. It tracks
where your partner is in her cycle, explains what she's likely feeling, and
gives you practical daily tips — not clinical information, but genuinely useful
guidance on how to be present and supportive.

All data lives on your device. Nothing is sent anywhere. No account, no server,
no ads, no tracking.


HOW TO USE IT

The app is a single HTML file hosted on GitHub Pages and installable as a
Progressive Web App (PWA) on Android.

To install:
1. Open the link in Chrome on your Android phone
2. Tap the three-dot menu → "Add to Home Screen"
3. It will appear as an app icon on your home screen
4. Open it once on WiFi — after that it works fully offline

On first launch, enter the date her last period started, how long her period
typically lasts, and an estimated cycle length (28 days is a safe default). 
Everything refines automatically as you log more cycles over time.


PRIVACY

This app was deliberately built without any backend, account system, or data
transmission. All data is stored in your browser's localStorage — it never
leaves your phone. The GitHub repository contains only the app code, not any
personal data. If you want to take the app fully offline and remove it from
GitHub entirely, download the HTML file and open it directly from your phone
via Google Drive or a file manager.


DATA & BACKUP

Your cycle history is valuable and irreplaceable. Use the Export function in
the side drawer regularly. Exports are saved as a dated JSON file
(e.g. cycle-companion-2025-04-29.json) — each export is a full snapshot,
replacing the previous. Store backups in Google Drive or similar.

To restore data on a new phone or after clearing your browser, use the Import
function in the drawer and select your latest backup file.


-------------------------------------------------------------------------------
RELEASE HISTORY
-------------------------------------------------------------------------------

V1 — Core Dashboard

The foundation. Everything needed to be useful from day one.

- Daily dashboard showing current cycle phase, cycle day, and what to expect
- Four phase system: Menstrual, Follicular, Ovulation, Luteal
- Phase-specific colour theming that shifts with the cycle
- Practical daily tips for how to show up at each phase
- Cycle progress bar
- Countdown cards to next period and ovulation
- One-time setup: last period date, cycle length, period duration
- Settings panel to update details at any time
- PWA setup — installable to home screen, works offline
- All data stored locally, nothing leaves the device
- Inline SVG icon (no external image files needed)
- Home screen and browser tab icon


V2 — Cycle Logging & Smarter Predictions

The app learns her actual cycle over time rather than relying on a fixed
assumption.

- Side drawer (hamburger menu) replacing the bottom sheet settings
- Log a new period start — today, or any past date you missed
- Sanity check when logging: warns if the gap looks shorter or longer than
  her usual cycle, so you can catch mistakes before saving
- Cycle history list — view all logged entries, delete incorrect ones
- Rolling average calculation: once 2+ cycles are logged, cycle length is
  calculated from real data rather than your initial estimate
- Variance tracking: shows how regular her cycle is (e.g. ±2 days)
- Dashboard shows data confidence ("Based on 4 cycles · ±1.5d variation")
  and falls back gracefully to your estimate while history is still thin
- Export: full JSON snapshot, date-stamped filename, always replaces previous
- Import: restores from backup with overwrite confirmation
- Last export date shown in drawer
- Late cycle banner: flags if cycle exceeds 40 days, with day count
- Export reminder banner: shown when 3+ cycles logged and 60+ days since
  last export or dismissal — protects against data loss
- Data migration: automatically upgrades data from v1 format


V3 — In-App Notifications

Timely banners shown when the app is opened, covering the moments that matter
most. All banners are dismissible and won't re-appear for 24 hours.

- Period just ended: energy is returning, good time to reconnect
- Ovulation in 1–2 days: approach peak, plan something together
- Ovulation day: her highest energy day, be present and attentive
- PMS window starting: ~7 days before period, patience mode begins
- Period in 1–2 days: reminder to check supplies and prep comfort items
- Period a few days late (gentle): 3+ days over expected, under clinical
  threshold — reassuring tone, encourages patience
- Late cycle (clinical): 40+ days since last period, suggests gentle check-in
- All notifications use colour coding: green (positive/peak), purple
  (winding down), red (period incoming), yellow (late/overdue)


-------------------------------------------------------------------------------
FUTURE PROSPECTS
-------------------------------------------------------------------------------

The following are planned or being considered for future versions. None are
committed — they'll be built when they make sense.


V4 — Personalisation

- Symptom notes: log how she actually felt each day to spot her personal
  patterns, not just textbook ones
- Custom tips per phase: add your own notes based on what you've learned
  about her specifically
- Relationship prompts: small randomised thoughtful gestures suggested per
  phase (e.g. "run her a bath", "let her pick the film tonight")
- Relationship prompts can optionally be personalised to her preferences


V5 — Quality of Life

- Export/backup to Google Drive directly from the app
- Optional PIN or biometric lock for privacy
- Dark mode
- Cycle calendar view: month-view showing past and predicted phases at a
  glance, useful for trip and event planning beyond the look-ahead tool


Longer-Term Considerations

- Native Android wrapper (via Capacitor): would unlock true background
  push notifications without needing to open the app. Low priority while
  the in-app banner approach is sufficient, but a clean upgrade path exists
  when needed.
- Wearable companion: a minimal Wear OS tile showing today's phase and a
  single tip, for a quick glance without opening the phone.
- Multi-device sync: if ever needed, a lightweight encrypted sync option
  (no plaintext data, user-controlled key). Not needed while the app is
  single-user single-device.


-------------------------------------------------------------------------------
TECHNICAL NOTES
-------------------------------------------------------------------------------

Built as a single self-contained HTML file. No build tools, no dependencies,
no frameworks. Vanilla HTML, CSS, and JavaScript only.

Storage: browser localStorage, keyed as cycle_companion_v2
Offline: PWA service worker caches the app on first load
Hosting: GitHub Pages (public repo, free tier)
Fonts: Google Fonts (Cormorant Garamond + DM Sans) — loaded on first visit
       and cached offline thereafter
Icon: inline base64-encoded SVG — no external image files required
Manifest: generated and injected at runtime from inline JavaScript

The app is fully functional from a locally-saved HTML file with no hosting
required. If removed from GitHub, download the file and open via Chrome on
Android using Google Drive or a file manager.

-------------------------------------------------------------------------------
