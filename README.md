# Spin the Wheel

A fully customizable decision wheel. Add your own options, icons, and messages — then save and share your configuration via a bookmark link.

**Live:** [wheel.neorgon.com](https://wheel.neorgon.com/) · runs entirely in the browser, no build step, no backend.

---

## What it does

Spin a randomized wheel to pick between any set of options you define. Comes pre-loaded with a food picker, but every part is configurable.

---

## Features

- **Customizable options** — add, remove, and reorder segments with any text, emoji, and color
- **Per-option messages** — set a custom message shown when a specific option lands (e.g. "Taco Tuesday! 🌮")
- **Default result template** — global message with `{result}` and `{emoji}` placeholders
- **Wheel title & icon** — name your wheel and set a header emoji
- **Live preview** — the wheel updates as you type in the settings panel
- **Settings saved automatically** — your configuration persists in `localStorage` across visits
- **Shareable link** — "Copy Share Link" encodes your full config into the URL hash; anyone opening it sees your exact wheel
- **Bookmark-friendly** — the URL hash updates whenever you apply settings, so bookmarking saves your wheel
- **Smooth animation** — ease-out quartic spin over 4–5 seconds with a confetti burst on result
- **Mobile-friendly** — settings panel becomes a full-screen drawer on small screens

---

## Settings

Open the **⚙️ Settings** panel in the header to configure:

| Field | Description |
|-------|-------------|
| Wheel Icon | Emoji displayed next to the title |
| Wheel Title | Name shown in the header and on the page |
| Result Message | Template shown after the wheel stops (`{result}`, `{emoji}`) |
| Options | Each has an emoji, label text, color, and optional custom message |

Click **Apply & Save** to persist and update the bookmark URL.

---

## Sharing & bookmarks

Every wheel configuration is encoded into the URL hash:

```
https://wheel.neorgon.com/#c=eyJ0aXRsZSI6...
```

Clicking **Copy Share Link** puts this URL on your clipboard. Anyone who opens it — or who bookmarks it — will see the same wheel with the same options.

---

## Running locally

```bash
cd dynamic-wheel-game
python3 -m http.server 8080
# open http://localhost:8080
```

Or open `index.html` directly — no dependencies, no install.

---

## Tech

Pure HTML + CSS + Canvas API + JavaScript. No external libraries. Wheel rendering uses `CanvasRenderingContext2D` arcs with ease-out quartic animation via `requestAnimationFrame`. Config serialized with `JSON.stringify` → `btoa` → URL hash.
