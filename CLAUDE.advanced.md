<!-- ADVANCED MENU — not auto-loaded. Only CLAUDE.md / AGENTS.md is. As the project grows and you want
     more structure, copy a block from here into the lean CLAUDE.md (replace the matching stub — one
     fact, one place). Shared conventions that already live in the global ~/.claude/CLAUDE.md (devlog
     format, three-part semver, communication style, review protocol) are NOT duplicated here — that
     file owns them. -->

# AI展 (aitian) — governance menu

## Locked decisions (already in CLAUDE.md)

The lean root already carries the Locked-decisions block. The discipline:

- **Implementing/planning → obey.** If the work seems to require breaking a locked decision, **stop and
  surface it** — don't improvise past it.
- **Brainstorming / spec'ing / explicit human decision → challenge freely.** Name the conflict, ask
  whether to keep or unlock.
- **Unlock in the open, never silently:** update the canonical section (kickstart / a maintained doc)
  and log the change + reason in `docs/devlog.md` (or an ADR under `docs/decisions/`). The superseded
  decision stays in the historical record.

## Workflow — the dev cycle

1. **Brainstorm → spec** before building; **plan** once the spec is agreed. Spec + plan land in the
   historical tier (`docs/specs/`, `docs/plans/`) — allowed to go stale later.
2. **Implement** against the plan.
3. **Fold lasting decisions into the maintained docs** (CLAUDE.md Locked decisions, the relevant
   `docs/*.md`) — those, not the spec, are the source of truth afterward.
4. **Close the loop at end of session** (below).
5. The next round starts from these docs, so the agent can spot where a new idea diverges from a past
   decision and surface it.

## End-of-session checklist — close the loop

A **gate, not a nicety** — do it before the work counts as done (e.g. before a PR opens), and commit
the doc changes **in the same PR** as the code:

1. **Update every maintained `docs/*.md`** the session touched. ("No docs needed" is a claim to
   justify, not a default.)
2. **Append a newest-on-top entry to `docs/devlog.md`** (global CLAUDE.md owns the format) and link it
   to this milestone's spec/plan.
3. **Update `todo.md`** — clear done items, add next steps.

When the user says **"ship it" / "raise a PR,"** run this, commit, open the PR — then **stop** (don't
merge; that's the user's call).

## Conventions (project-specific)

- **Staging: explicit paths only — never `git add -A` / `git add .`.** Stage the exact files you
  changed; confirm with `git diff --name-only main...HEAD` before a PR.
- **Public-repo hygiene:** never commit speaker contact info or secrets (see kickstart §4d). Scan every
  commit before pushing.
- **Deploy only the built site:** the GitHub Pages artifact must contain **only** the website output
  (e.g. `dist/`) — never `CLAUDE.md`, `todo.md`, or `docs/`. See kickstart §4c.
- (Shared: three-part semver, devlog format, "not-A-but-B" avoidance, etc. → global `~/.claude/CLAUDE.md`.)
