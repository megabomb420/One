# CLAUDE.md

## Project Overview

**SUNO FORGE** — a single-file React web app for generating Suno AI music prompts. Given a creative brief (concept, genre, mood, language, structure) it calls the Anthropic API and returns a complete Suno-ready package: style tags, structured lyrics with section metatags, and a title.

Built around the songwriting rules from [NuNaught/suno-songwriting-skill](https://github.com/NuNaught/suno-songwriting-skill): syllable control, AI-slop avoidance, proper rhyme craft, and dense production briefs.

**Owner style profile:** Polish Rap, Dark R&B, Trap, Miami Bass, Deep Dubstep, Wave/Phonk, Instrumental Hip Hop. Dense metaphors, literary layers, medical/culinary/chemical register. Complex rhyme schemes, anadiplosis, mosaic rhymes.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| UI | React 18 (CDN, no build step) |
| JSX transform | Babel Standalone (CDN) |
| Styling | Custom CSS (dark theme, CSS variables) |
| AI | Anthropic Messages API (`claude-sonnet-4-6` default, `claude-opus-4-7` option) |
| State persistence | `localStorage` (API key only) |
| Deploy | Any static host — single HTML file |

---

## Folder Structure

```
One/
├── CLAUDE.md        # This file
└── index.html       # Complete app (single file)
```

---

## How to Run

No build step. Open `index.html` in any modern browser, or serve it:

```bash
# Any static server works
python3 -m http.server 8080
# or
npx serve .
```

Then open `http://localhost:8080` in a browser. Enter your Anthropic API key in Settings (⚙) — it's stored in localStorage.

**Required:** An [Anthropic API key](https://console.anthropic.com/) with access to Claude Sonnet 4.6 or Opus 4.7.

---

## Coding Conventions

- **Single file:** All app logic stays in `index.html`. No build, no bundler, no node_modules.
- **No comments:** Code is named to be self-explanatory. Comments only for non-obvious invariants.
- **No dead code:** Remove unused constants, components, or styles.
- **No TODOs in code:** Use GitHub Issues instead.
- **Commits:** Conventional Commits format (`feat:`, `fix:`, `chore:`)
- **Branch naming:** `<type>/<short-description>`

---

## Key App Sections

| Section | Description |
|---------|-------------|
| `SYSTEM_PROMPT` | All songwriting rules from the skill, encoded as a Claude system prompt |
| `buildUserMessage()` | Constructs the per-request user message from form state |
| `GENRES / MOODS / STRUCTURES / LANGUAGE_OPTS` | UI option constants |
| `generate()` | Calls `api.anthropic.com/v1/messages` with `anthropic-dangerous-direct-browser-access: true` |
| Output | Title + style (with char counter) + lyrics — separate copy buttons for Suno's two fields |

---

## Testing

No automated tests. Manual testing checklist:
- [ ] API key saves to / loads from localStorage
- [ ] Genre chips toggle correctly (multi-select)
- [ ] Generate button calls API and populates all three output blocks
- [ ] Copy buttons work for style and lyrics independently
- [ ] Char counter turns yellow >780, red >870
- [ ] Error state displayed on API failure
- [ ] Regenerate button works after first generation
- [ ] Mobile layout renders single-column below 900px

---

## Environment Variables

None — the Anthropic API key is entered at runtime in the UI and stored in the browser's localStorage. Never hard-code it in the file.

---

## Notes for Claude Code

- This repo was initialized on 2026-05-15
- The entire app is `index.html` — do not split into multiple files unless explicitly asked
- When updating the system prompt in `index.html`, preserve all lyric-craft rules (AI-slop list, register preferences, rhyme scheme requirements)
- The `anthropic-dangerous-direct-browser-access: true` header is required for direct browser API calls — do not remove it
- All tasks, TODOs, and known issues tracked as GitHub Issues
