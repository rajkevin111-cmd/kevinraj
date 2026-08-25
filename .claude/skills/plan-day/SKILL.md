---
name: plan-day
description: Build a realistic plan for today from tasks.md, waiting.md, and yesterday's carryover, and write it to days/YYYY-MM-DD.md. Use when the user asks to plan the day, start the day, or asks what they should work on today.
---

# Plan day

Produce a plan the user can actually finish. An over-full day is not ambition,
it's a plan that reports failure at 6pm regardless of how much got done — and a
plan that always reports failure stops being read.

## Inputs

Read before proposing anything:

- `tasks.md` — deferred actions. Anything dated today or earlier is live.
- `waiting.md` — delegated items. Flag anything waiting more than a week.
- `days/` — yesterday's file, for carryover.

**There is no calendar integration.** Do not invent meetings, infer a schedule,
or assume a workday shape. Ask what's already committed today and take the
answer at face value. If the user has recorded commitments in a file, read it.

**Do not read or triage `inbox.md`.** That belongs to the `inbox` skill. If the
inbox is visibly long, say so in one line and suggest processing first — then
plan with or without it, as the user prefers. Planning around unprocessed
capture is planning around noise.

## The plan

1. **Subtract first.** Start from committed hours — meetings, appointments,
   fixed obligations — and plan only the remainder. Meetings cost more than
   their duration; the half hour on either side is rarely usable for deep work.
2. **One must-do.** A single item that makes the day a success if it's the only
   thing that happens. Not three. One.
3. **Two or three secondary items**, sized to the hours that actually remain.
4. **Anything past that is a wish list.** Label it as such, below a divider, or
   leave it out.

Assume **three to four hours** of genuine focused work in an unusually good
day. Less on a meeting-heavy one. Plan to that number, not to the number of
hours the user is technically awake.

## Carryover

Anything unfinished from yesterday gets **re-decided, not auto-rolled.** Ask:
still today, back to `tasks.md` with a new date, or dead? An item that silently
rides from day to day is invisible — it looks like a plan while functioning as
a quiet accumulating debt. Name it on the third consecutive appearance: it's
usually too big, badly defined, or something the user doesn't actually intend
to do.

## Output

Write `days/YYYY-MM-DD.md`:

```markdown
# YYYY-MM-DD

**Must:** <the one thing>

## Committed
- HH:MM <fixed obligation>

## Planned
- [ ] <item>
- [ ] <item>

## Waiting on
- <who> — <what>, since <date>

---
Wish list: <anything that didn't fit>
```

Keep it short enough to hold in view. If the plan doesn't fit on a screen, it
isn't a plan.

## Closing out

When the user wraps the day, resolve every open box: done, back to `tasks.md`
with a date, or deleted. Nothing stays checked-out in a past day's file —
that's how work goes missing. Then say what actually got done, plainly, without
inflating a thin day or moralizing about it.

## Hard stops

From `CLAUDE.md`. Planning itself is local and needs no approval, but:

- Declining, moving, or scheduling anything with another person is outbound —
  propose the wording, let the user send it.
- Deleting a task during carryover means removing a line from a tracked
  markdown file, which is fine. Deleting anything else is a hard stop.
