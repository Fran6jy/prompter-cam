# Prompter Cam

A browser-based teleprompter that records at the same time. The script scrolls in a panel near the top of the screen, right beside the lens, while the camera runs underneath — so your eyes stay on camera instead of drifting to a second device.

Built because the iOS teleprompter apps paywall anything over 750 characters.

**Live:** https://fran6-prompter.vercel.app

## Features

- **Live camera preview** with the script overlaid, recorded together in one take
- **Resizable, movable panel** — drag the arrows to change its height, the cross to move it up or down
- **Timing against a target** — counts up and compares against the script's estimated spoken length at 140 words per minute, turning amber if you overrun
- **Word count and spoken-time estimate** shown live while editing, so scripts can be trimmed before recording
- **Adjustable scroll speed**, font size and panel opacity
- **Text alignment** and **mirror** modes (horizontal and vertical, for beam-splitter rigs)
- **Countdown** before recording starts
- **Front and rear camera** switching
- Everything persists in `localStorage` — script, speed, size, panel position

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
