---
name: inbox
description: Capture items into inbox.md and process them to empty. Use when the user says "capture" followed by anything, or asks to process, triage, empty, or clear their inbox. Capture is append-only and instant; processing routes each item through delete / do / defer / delegate / file.
---

# Inbox

Two modes that must never bleed into each other. Capture is a write. Processing
is a decision. Mixing them is what kills capture systems — if capturing costs a
conversation, the user stops capturing, and the system is dead.

## Capture

Triggered by `capture <item>`.

Append one line to `inbox.md`:

```
- [YYYY-MM-DD HH:MM] <item, verbatim>
```

Use the system clock (UTC unless a timezone is configured). Append to the end,
below the `---`. Never rewrite the file's existing contents.

Then confirm in one short line. Nothing more.

**During capture, do not:**

- Reword, clean up, expand, or interpret the item — verbatim means verbatim
- Ask a clarifying question, even when the item is genuinely ambiguous
- Categorize, tag, prioritize, or estimate it
- Suggest what to do about it, or note that it relates to something else
- Start doing it, even if it's trivial and obvious

A vague or duplicate entry is correct behavior, not a problem to fix. Ambiguity
gets resolved at processing time, when there's a decision to attach it to.

## Processing

Triggered by a request to process, triage, empty, or clear the inbox.

Work **one item at a time, oldest first.** Do not dump the whole list with
proposed dispositions — that's a wall of text nobody reads, and it turns a
sequence of small decisions into one big one.

For each item, propose a disposition and a concrete next action, then wait:

| | Meaning | Where it goes |
|---|---|---|
| **Delete** | No longer matters, or never did | Removed, gone |
| **Do** | Takes ~2 minutes | Done now, in this turn |
| **Defer** | Real action, needs a slot | `tasks.md` |
| **Delegate** | Someone else's to do | `waiting.md`, with who and since when |
| **File** | Reference, not action | `notes/` |

Recommend one rather than offering all five. The user picks or overrides.

Remove each item from `inbox.md` as it's dispositioned — the file should shrink
in real time, not at the end. Create `tasks.md`, `waiting.md`, or `notes/` on
first use; don't pre-create them empty.

**Defer needs a when.** "Later" is how items get recaptured next month. Attach a
date or a trigger condition.

**Delegate needs a who.** Record the person and the date it started waiting.

### Hard stops still apply

From `CLAUDE.md`. Processing is where they most often come up:

- **Do** that turns out to be outbound (send, reply, post) or spending — stop
  and ask before acting.
- **Delegate** records the intent to hand something off. Actually messaging the
  person is outbound: ask first.
- **Delete** removes a line from `inbox.md`, which is fine and reversible via
  git. Deleting anything else is a hard stop.

### Ending a session

Stopping early is normal. Don't push to finish the list. Say how many items
remain and leave them in place, untouched and in order.
