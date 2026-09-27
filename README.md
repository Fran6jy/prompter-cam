# Telebuonta

A browser-based teleprompter that records at the same time. The script scrolls in a panel near the top of the screen, right beside the lens, while the camera runs underneath — so your eyes stay on camera instead of drifting to a second device.

Built because the iOS teleprompter apps paywall anything over 750 characters.

**Live:** https://telebuonta.vercel.app

## Features

- **Live camera preview** with the script overlaid, recorded together in one take
- **Resizable, movable panel** — drag the arrows to change its height, the cross to move it up or down
- **Set the speed from a target time** — say the take should run 75 seconds and it works out the scroll rate for you
- **Timing against a target** — counts up and compares against the script's estimated spoken length at 140 words per minute, turning amber if you overrun
- **Progress bar** along the panel so you can see how much script is left
- **Multiple named scripts**, with word count and spoken-time estimate shown while editing
- **Pause and resume** mid-recording without losing the take
- **Microphone level meter**, so you find out the mic is dead before the take rather than after
- **Screen wake lock** — the display stays on while you record
- **Quality selector** — 720p, 1080p or 4K where the device supports it
- **Take history** — every recording in the session stays available to review and save
- **Text alignment** and **mirror** modes (horizontal and vertical, for beam-splitter rigs)
- **Countdown** before recording starts
- **Front and rear camera** switching
- Everything persists in `localStorage` — scripts, speed, size, panel position

## Running it

It's a single static file. Any HTTPS host will do; camera access requires a secure context, so `file://` won't work.

```bash
npx vercel --prod
```

Or open `index.html` through any local HTTPS dev server.

## Browser support

Needs `getUserMedia` and `MediaRecorder`. Works in Safari on iOS 14.5+ and Chrome on Android. Output is MP4 where the browser supports it, WebM otherwise.

Recording quality is bounded by what the browser exposes, which is below what the native camera app produces. The trade is having the script and the camera in one device.

## Stack

Vanilla HTML, CSS and JavaScript. No build step, no dependencies, no framework.

## Licence

MIT
