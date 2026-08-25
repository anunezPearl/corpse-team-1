# Team 1: Word Chain

Type a word. The app should eventually build a chain where each new word
starts with the last letter of the previous word (cat → tiger → rabbit → ...).

## Status
Workshop round 1 (`round-1-abba`). Added:
- English/Spanish toggle (EN/ES buttons, top right)
- A theatrical 15-second "urgent" countdown per turn, with a dramatic game-over state
- A "Summon a Lisa Frank Guardian" button that generates a neon '90s-style image via the
  internal LiteLLM proxy (DALL-E-compatible endpoint)

## Game rules

- Every word after the first must start with the last letter of the preceding word.
- A word can only appear once in a chain. Matching is case-insensitive.
- When LiteLLM settings are configured, the app asks the selected chat model to verify
  that an entry is a real English or Spanish word, matching the selected language.
- After the Lisa Frank guardian image is generated, the same LiteLLM chat model receives
  the current word chain and image and recommends one matching song with a short rationale.
- If the LLM endpoint is unavailable, slow, or returns an error, the app accepts the
  entry so the game remains playable offline.

## Appearance

Use the selector beside the language buttons to choose from the Midnight, Aurora, and
Candy themes. The selected theme is saved in browser `localStorage`.

### Local setup for image generation
The LiteLLM base URL/API key are entered client-side via the ⚙ button (bottom right) and
stored only in your browser's `localStorage` — nothing is committed to the repo. Use the
values from your local `.env` (copy `.env.example` to `.env` if you haven't already).
The settings panel also accepts an optional chat model name, defaulting to `gpt-4o-mini`.
