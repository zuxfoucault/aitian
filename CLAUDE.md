# AI展 (aitian) — Project Context

Static portal website for our AI-application meetup community (members = "aitians"). It gives the
community a branded front door, gives moderators/speakers a **citable webpage** for LinkedIn/résumé,
and records past meetups. Content is authored as Markdown, contributed via PR, and built to a static
GitHub Pages site. Full requirements/brainstorm: [`docs/kickstart.md`](docs/kickstart.md).

This file is auto-loaded every session — it's a small **index**, not an encyclopedia. Stable facts +
links out. Shared conventions (devlog format, semver, communication style) live in the global
`~/.claude/CLAUDE.md`; don't restate them here.

## Who's working on this

- **SansWord** (Wen-Kai) — building it. **pinku** — co-organizer, design/product input.
- How I like you to work: give **clear options with a recommendation**, not open-ended menus.
  **Surface decisions that are mine** (scope, naming, copy, product framing) — don't silently assume
  them. Keep the doc tree current.

## Current status

> Not restated here, to avoid drift: **what's shipped** → top row of [`docs/devlog.md`](docs/devlog.md);
> **what's next** → [`todo.md`](todo.md).

Stable facts:
- **Repo:** `sansword/aitian` (public) · **Hosting:** GitHub Pages, static site.
- **URL:** `sansword.github.io/aitian` initially; custom domain (`aitian.dev` or similar) later.
- **Stack:** static site (framework TBD — leaning vanilla HTML/CSS/JS). Data authored as Markdown +
  YAML frontmatter, built to JSON at deploy.

## Locked decisions

> Settled calls. **Implementing/planning → obey them.** **Brainstorming or explicit human decision →
> challenge freely.** If a new idea conflicts with one, name the conflict and ask align-or-unlock; to
> change one, update the canonical section + log it in [`docs/devlog.md`](docs/devlog.md). Detail and
> rationale live in [`docs/kickstart.md`](docs/kickstart.md).

- **Name:** AI展 (aitian) — Taiwanese pun (愛展 "want to demo") + "-ian" demonym → members are
  "aitians". → kickstart §0
- **Hosting:** GitHub Pages, repo `sansword/aitian`; custom domain later. → kickstart §2
- **Data format:** author in Markdown + YAML frontmatter; build to JSON at deploy (page consumes JSON,
  no runtime parser). → kickstart §4b
- **Data layout:** one file per meetup/moderator under `data/`; discovery + ordering via a deploy-time
  generated `index.json` (never committed to the repo). → kickstart §4c
- **A meetup is a multi-segment session** (Talk 1 / Talk 2 / Chat), not a single talk. → kickstart §4
- **Privacy:** speaker contact info (email/thread) **never** enters the public repo — logistics stay
  in the private sign-up sheet; only topic, speaker name, and materials link are public. → kickstart §4d
- **Contribution:** speakers/moderators add or edit **their own** Markdown file via PR (conflict-free).
  → kickstart §4

## Docs — two tiers

- **Maintained `docs/*.md`** (source of truth; must match the code) — *none yet.* Add each here with a
  one-line description **and its update trigger** as the site is built (candidates: `docs/wording.md`
  for name/bilingual copy, `docs/architecture.md` for the build pipeline).
- **Historical** (how we got here; allowed to go stale; kept forever):
  - [`docs/kickstart.md`](docs/kickstart.md) — the founding brainstorm/spec: goals, name, data model,
    MVP scope, privacy, open questions. **Read before any planning.**
  - `docs/specs/`, `docs/plans/`, `docs/decisions/` — per-milestone specs / plans / ADRs (scaffolds).
  - [`docs/devlog.md`](docs/devlog.md) — newest-first history; the top row is the current state.

## Before you plan — read first

Before planning or building, **read [`docs/kickstart.md`](docs/kickstart.md)** (plus any relevant
maintained docs and the Locked decisions above), then plan against them — and **name the files you
consulted**, so it's visible which docs informed the work.

## End of session — close the loop

Before work counts as done: update any maintained `docs/*.md` it touched, append a newest-on-top entry
to [`docs/devlog.md`](docs/devlog.md) (linking its spec/plan), and update [`todo.md`](todo.md).

> Want more governance blocks (dev cycle, PR gate, ADR flow)? See [`CLAUDE.advanced.md`](CLAUDE.advanced.md) —
> a menu to copy from as the project grows.
