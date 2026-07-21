# ♥ 3-Hearts Chess

A chess.com-style chess variant where **every piece has 3 hearts**. Pieces don't die the
instant they're attacked — they lose one heart per attacker at the end of each move, and
only vanish at 0 hearts. Even the king has hearts: **check it three times and you win.**

Play against a ~1000-rated bot that understands the mechanic.

👉 **[Read the full rules](./RULES.md)**

## Features

- ♟ **Full legal chess engine** — verified against standard perft positions (startpos,
  Kiwipete, en passant, promotions, pins all match known node counts).
- ♥ **The 3-hearts mechanic** — one heart lost per attacker each move; kings lose a heart
  per check; win by checkmate *or* 3 checks.
- 🤖 **~1000-rated bot** — heart-aware evaluation (fragile pieces valued lower, king-heart
  safety, check-hunting) with human-like imperfection. Moves in a fraction of a second.
- 🎨 **chess.com-style UI** — the real "neo" piece set, green/cream board, drag-and-drop or
  click-to-move, legal-move dots, last-move + check highlights.
- 🏹 **Full controls** — right-click-drag arrows, right-click square highlights, **premoves**,
  promotion picker, move list with SAN + click-to-review, board flip, resign, sounds.

## Running it

It's a single self-contained HTML file — **no build step, no dependencies, no network**
(the piece images are embedded). Just open it:

```bash
open index.html      # macOS
# or serve it
npx serve .
```

## Deployment

Deployed on Vercel as a static site (see `vercel.json`). Any static host works — the whole
game is `index.html`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire game (engine + bot + UI, self-contained) |
| `RULES.md` | Full rules of the variant |
| `vercel.json` | Static-deploy config |
