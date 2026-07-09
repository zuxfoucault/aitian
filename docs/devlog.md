# Devlog

Running log of decisions and learnings, **newest first**. The top entry is the project's current
state — the root `CLAUDE.md` points here instead of restating the version. This file is *historical*
(append-only) yet *always current*, because "newest on top" is true forever. Each entry references the
spec / plan / design doc from that session so a later session can lazily load the right context.

### Learning tags

| Tag | Meaning |
|-----|---------|
| `[note]` | Useful context, well-documented — good to have written down but you'd find it in the docs |
| `[insight]` | Non-obvious; meaningfully changes how you design or debug something |
| `[gotcha]` | A specific trap that bit you; high risk of biting again — bookmark it |

## TL;DR

| Version | Summary |
|---------|---------|
| [v0.1.0-design](#v010-design--kickstart-and-doc-tree-setup-2026-07-09-0555) | Captured meetup-portal requirements, named the project **AI展 (aitian)**, created the public repo, and set up the document-tree practice. |

---

## v0.1.0-design — Kickstart and doc-tree setup (2026-07-09 05:55)

**Review:** not yet
**Design docs:** Kickstart: [Spec](kickstart.md)
**What was built:** *(design/planning session — no site code yet)*
- Captured the AI-application meetup-portal requirements from the SansWord ↔ pinku discussion into
  [`docs/kickstart.md`](kickstart.md): purpose, name, hosting, data model, MVP page scope, privacy, and
  open questions.
- Named the project **AI展 (aitian)** — a three-layer name (愛展 "want/love to demo" · AI 展 "AI demo" ·
  "-ian" demonym → community members are "aitians"). Rejected `laitian` (reads like "Laotian").
- Settled the data architecture: one Markdown-file-per-entry under `data/`, built to JSON + a manifest
  at deploy via GitHub Actions; a meetup is a multi-segment session (Talk 1 / Talk 2 / Chat).
- Created public repo `sansword/aitian` and pushed the kickstart doc.
- Applied the **document-tree practice** (this `CLAUDE.md` / `CLAUDE.advanced.md`, `todo.md`, this
  devlog, and the `docs/` historical tiers + templates).

**Key learnings:**
- `[insight]` A static GitHub Pages site can't list a directory at runtime — so a deploy-time build
  both parses Markdown → JSON and generates the `index.json` manifest, keeping the runtime
  dependency-free while contributors author friendly Markdown.
- `[insight]` A custom domain decouples the public URL from the (taken) GitHub org name and makes
  hosting movable without breaking cited links — which matters because the site's whole point is a
  stable, citable URL.
- `[gotcha]` The repo is **public** — speaker contact info (sign-up sheet column F) must never be
  committed; only topic, speaker name, and materials link are public.
- `[note]` Meetups run weekly on **Tuesdays**, 2026-07-14 → 2026-09-01, each with Talk 1 / Talk 2 / Chat.
