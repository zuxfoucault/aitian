# TODO

The single home for "what's next" — the root `CLAUDE.md` points here instead of restating it. Keep it
current as part of the end-of-session checklist.

## Now

- [ ] **Merge the spec+plan PR** — branch `feat/mvp-scaffold-spec` holds the spec, the
      implementation plan, and doc updates; push, raise PR, squash-merge (branching convention
      in `CLAUDE.md`).
- [ ] **Execute the plan** ([`docs/superpowers/plans/2026-07-10-mvp-scaffold.md`](docs/superpowers/plans/2026-07-10-mvp-scaffold.md))
      in a fresh session on a new `feat/mvp-scaffold` branch off `main` (after the spec+plan PR
      merges). Cutline for **7/14** is marked in the plan: Tasks 0–11 + doc tasks ship alone.
- [x] **Write the implementation plan** from the approved spec — done 2026-07-10:
      [`docs/superpowers/plans/2026-07-10-mvp-scaffold.md`](docs/superpowers/plans/2026-07-10-mvp-scaffold.md).

## Later

- [ ] **Build the MVP** per the spec — pages (landing, hash-routed meetup detail, moderators),
      `data/` Markdown, `scripts/build-data.mjs` (parse + validate + emit JSON/manifests). Deploy
      pipeline already stands up (`.github/workflows/deploy.yml`); swap `path: site` → `path: dist`
      and add the PR-validate job (spec §3.2).
- [ ] **Create `docs/data-schema.md` + `docs/wording.md`** during implementation (spec §5) and
      register both in `CLAUDE.md` "Maintained docs". Wording needs: name lore (AI展 / 愛展 /
      "aitians"), tagline pair (en "Show off your AI work" / zh 「用你的 AI 作品展風神」), CTA copy.
- [ ] **Repo settings (manual, SansWord)** — branch protection on `main` incl. no-bypass + required
      validate check; Actions "Require approval for all outside collaborators" (spec §3.3).
- [ ] **Seed `data/` from the sign-up sheet** (weekly Tuesdays 7/14 → 9/1), excluding private contact
      info (kickstart §4d).
- [ ] **Decide vs. Luma** for RSVP / the "get invite link" CTA (kickstart §2 note).
- [x] **Custom domain** — `aitian.dev` is live (CNAME added 2026-07-10, serving HTTP 200).
- [x] **Enable "Enforce HTTPS"** — done 2026-07-10; verified `http://` 301s to `https://aitian.dev/`.
- [x] **Enable GitHub Pages** (deploy from Actions) — live at `sansword.github.io/aitian` (v0.2.0).
