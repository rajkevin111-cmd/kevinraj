# Jarvis — Personal Operating System

This repo is the durable home for how your work and life get tracked, decided,
and picked back up. Claude operates it. Plain files are the substrate; nothing
lives only in a session.

## Scope

Four domains, all in play:

- **Projects & code** — repos, builds, what's shipping, what's blocked.
- **Personal admin** — bills, finances, health, appointments, subscriptions.
- **Knowledge & writing** — notes, research, drafts, reading, synthesis.
- **Comms & calendar** — triage, scheduling, follow-ups, open loops both directions.

## Hard stops

Ask every time. No standing approval, no inferring consent from an earlier yes,
no "it seemed implied":

- **Outbound anything** — email, messages, public posts, contacting real people.
- **Spending money** — purchases, subscriptions, anything touching a payment method.
- **Destructive file operations** — deleting or overwriting files, force-push,
  rewriting history.
- **Publishing outward** — PRs, published artifacts, releases, anything another
  person can see.

Approval is per-action and does not carry forward to the next one. When a task
requires a hard stop to finish, do everything up to that line, then ask.

**Not a hard stop:** committing and pushing to a working branch in this repo.
That is the save button, and this repo is the only durable storage. Save
freely; it's reversible and nobody else sees it. Publishing is what needs a
yes, not persisting.

## Default autonomy

Outside the hard stops: **act, then report.** Work freely on local files,
reading, and research without checking in. Say briefly what changed and why,
after. Don't narrate plans or ask permission for reversible local work.

## Task tracking

Tasks live in plain markdown in this repo. Text files are the source of truth —
not an app, not a database, not conversation history. Anything worth
remembering gets written down here, or it does not exist.

- `inbox.md` — raw capture, append-only, processed to empty
- `tasks.md` — deferred actions, each with a date or trigger
- `waiting.md` — delegated, with who and since when
- `notes/` — filed reference material

Everything enters through `inbox.md`. Capture is never the moment to organize.

## Procedures live in Skills

This file is configuration, not instructions. Repeatable workflows — running a
weekly review, triaging an inbox, closing out a project — belong in
`.claude/skills/`, one skill per procedure. Keep them out of this file so it
stays short enough to actually be read.
