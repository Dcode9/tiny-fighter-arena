# Tiny Fighter Arena

Describe a fighter in one line — the AI designs it (look, abilities, quirks, fighting style), paints its portrait, and commentates a turn-by-turn battle against a ladder of challengers.

**Play:** https://dcode9.github.io/tiny-fighter-arena/

Built for Pollinations quest [#17250](https://github.com/pollinations/pollinations/issues/17250).

## How it works

- **Bring Your Own Pollen.** Click "Connect Pollen" and sign in with GitHub. The app gets a scoped `sk_...` key via the [BYOP](https://github.com/pollinations/pollinations/blob/main/BRING_YOUR_OWN_POLLEN.md) fragment flow and spends *your* Pollen on the AI text — the key never leaves your browser, and you can revoke it any time from your Pollinations dashboard.
- **Fighter design + commentary** run on the text API (`/v1/chat/completions`, `openai/gpt-5.4-nano`) as JSON: the fighter sheet from your one line, then one exchange of damage + funny narration per turn. Clever, specific descriptions genuinely make stronger fighters.
- **Portraits** come from the public image endpoint (`image.pollinations.ai`), so they load even before you connect.

A single fight spends only a few hundred tokens of your Pollen on the AI text. The page shows a running token estimate.

## Run locally

It's one static file — no build:

```bash
python3 -m http.server 8000
# open http://localhost:8000/
```

(GitHub Pages serves `index.html` from the repo root.)

## Files

- `index.html` — the whole game (markup, styles, logic).

[![Made with pollinations.ai](https://raw.githubusercontent.com/pollinations/pollinations/main/packages/ui/src/brand/badge-made-with.svg)](https://pollinations.ai/?ref=badge)
