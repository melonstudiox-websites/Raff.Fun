# raff.fun

A tiny arcade of games about Raff. Pure static site — HTML, CSS and vanilla JS, no build step.

## deploying (Render)

This repo ships with a `render.yaml`. On [Render](https://render.com):

1. **New → Static Site**, connect this repo (Render auto-detects `render.yaml`).
2. Publish directory is `.` (repo root); there's no build command.
3. Deploy. `index.html` is served at the root and reads `games/manifest.json`.

Works on any static host (Netlify, GitHub Pages, Cloudflare Pages) too — there's no server code.

---

# how to add games

## folder structure

```
raff-fun/
├── index.html          ← the homepage (don't touch)
├── games/
│   ├── manifest.json   ← THE LIST OF GAMES
│   ├── would-raff.html ← demo game
│   └── your-game.html  ← your new games go here
```

---

## to add a new game

### step 1 — make the html file
Put it in the `games/` folder.
Name it something short with dashes: `raff-trivia.html`, `guess-the-raff.html`, etc.

Include a back button at the top:
```html
<a href="../index.html">← Raff.fun</a>
```

### step 2 — add it to manifest.json

Open `games/manifest.json` and add an entry:

```json
[
  {
    "id":          "your-game",
    "title":       "Your Game Title",
    "description": "One line about what it is",
    "emoji":       "🎮",
    "color":       ["#ff6b35", "#f7c59f"]
  }
]
```

- `id` → filename without `.html`
- `color` → two hex colors for the card gradient

### that's it. refresh the page, your game appears.

---

## color ideas

| vibe       | from      | to        |
|------------|-----------|-----------|
| fire       | `#ff6b35` | `#ffd275` |
| ocean      | `#00c9ff` | `#92fe9d` |
| gold       | `#f7971e` | `#ffd200` |
| hot pink   | `#ee0979` | `#ff6a00` |
| purple     | `#12c2e9` | `#c471ed` |
| mint       | `#43e97b` | `#38f9d7` |
| candy      | `#fa709a` | `#fee140` |
| lavender   | `#a18cd1` | `#fbc2eb` |
| dark space | `#141e30` | `#243b55` |
| neon cyan  | `#30cfd0` | `#667eea` |
