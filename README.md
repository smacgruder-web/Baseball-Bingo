# Ballpark Bingo — Stitched Interactive App

A complete, self-contained Progressive Web App (PWA) for live MLB-style bingo.

Open `index.html` in any modern browser. For the best mobile experience, **Add to Home Screen** on iOS or Android.

## Key Features

- **Fully playable 5×5 Bingo** with seeded boards (shareable via URL hash)
- **Live game simulation** — tap SIM PLAY to advance real-feeling plays that can suggest squares
- **Stadium Lobby**, **Chatter** (with AI color commentator "Bleacher Bill"), **League Standings**, and **Player Profile**
- **Beautiful Heritage Ballpark design** (cream paper, Domine + Work Sans, stadium green + clay red)
- **Tactile audio** (real Web Audio API bat crack, organ, crowd)

## PWA & Mobile Capabilities (Completed Build)

This is now a production-feeling, installable Progressive Web App:

**Icons & Branding**
- Real local icons in `/icons/` (192×192, 512×512, 180×180 for iOS) generated in the heritage ballpark style.
- All references updated (no more external CDNs for core assets).

**Core PWA**
- `manifest.json` (standalone, maskable icons, shortcuts to Play/Lobby)
- `sw.js` service worker (precaches shell + icons, network-first for navigations, offline fallback)
- Full iOS Home Screen support (apple-mobile-web-app-* metas, viewport-fit=cover, no Safari chrome when launched from HS)

**Game Resilience Features (as requested)**
- **Screen Wake Lock API**: Auto-requests when entering Play. Re-acquires after visibility changes (phone calls etc.). Visual pill indicator. Graceful fallback.
- **Double-Tap Zoom Protection**: `touch-action: manipulation`, no user-select, explicit JS prevention on the bingo grid → instant square taps, no accidental zoom.
- **State Auto-Save**: Aggressive localStorage of the full board (seed + all marks), game scores/inning, sound pref. On reload the board is exactly where you left it. Shared URL hash takes precedence when present.
- Offline banner appears when network is lost (your stamps are still saved locally).

**Install Experience**
- Smart `beforeinstallprompt` handling.
- Prominent "Install" button appears in the top nav when eligible.
- `triggerPWAInstall()` for one-tap add to Home Screen.
- Respects standalone mode (hides button when already installed).

**Bonus Polish**
- Live simulation can now auto-stamp relevant squares occasionally for a real "watching the game" feel while keeping full manual control.
- Smart load priority: URL hash (share) > LocalStorage (your last session) > fresh board.

## How to Install as App

**iPhone / iPad**
1. Open in Safari
2. Tap the Share button → "Add to Home Screen"
3. It will now launch full-screen without Safari chrome

**Android (Chrome)**
1. Open the site
2. Tap the three-dot menu → "Add to Home screen" or "Install app"

## Development Notes

- Everything is in a single `index.html` (plus `manifest.json` + `sw.js`)
- No build step required — just open the file or serve the folder
- State is intentionally resilient: LocalStorage for "my game", URL hash for "shared specific game"

## Keyboard Shortcuts (Desktop)

- `/` → focus Chatter
- `Cmd/Ctrl + P` → jump to Play screen

## Future / Backend Ideas (from earlier docs)

See `real_time_data_strategy.md` and `database_analytics_strategy.md` for live MLB feed + user accounts direction.

---

Built by stitching together dozens of prototype screens into one cohesive, production-feeling experience.
