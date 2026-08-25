# Team 1: Word Chain

Type a word. The app should eventually build a chain where each new word
starts with the last letter of the previous word (cat → tiger → rabbit → ...).

## Status
Workshop round 1 (`round-1-abba`). Added:
- English/Spanish toggle (EN/ES buttons, top right)
- A theatrical 15-second "urgent" countdown per turn, with a dramatic game-over state
- A "Summon a Lisa Frank Guardian" button that generates a neon '90s-style image via the
  internal LiteLLM proxy (DALL-E-compatible endpoint)

The core chain-validation logic (checking that each word starts with the previous word's
last letter) still isn't built — right now it just takes a word and shows it.

### Local setup for image generation
The LiteLLM base URL/API key are entered client-side via the ⚙ button (bottom right) and
stored only in your browser's `localStorage` — nothing is committed to the repo. Use the
values from your local `.env` (copy `.env.example` to `.env` if you haven't already).
