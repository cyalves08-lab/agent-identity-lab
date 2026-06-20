# Routines

Recurring work JARVIS runs on a schedule, set up with the `/schedule` command in
Claude Code. Each routine is a markdown file describing exactly what to do.

| Routine | File | Suggested cadence |
|---------|------|-------------------|
| Morning briefing | `morning-briefing.md` | Weekdays 6:30 AM |

## How to schedule one

In a Claude Code session in this repo:

```
/schedule run routines/morning-briefing.md every weekday at 6:30am
```

`/schedule` runs the routine in the background on the cadence you set and can
deliver the result to you. Manage existing schedules from the same command.

## Adding a routine

1. Create `routines/<name>.md` describing the steps (delegate to subagents where
   it makes sense).
2. Keep output to one screen and lead with the priority.
3. Default to **report-and-prepare**, not act-outward. Anything that sends,
   posts, or changes a budget should still wait for the owner unless they've
   explicitly authorized it.
4. Schedule it with `/schedule`.

## Ideas for later
- **Weekly ads review** — Monday roll-up of last week's Meta/IG performance.
- **Lead follow-up sweep** — flag leads with no reply in 48h.
- **Content refill** — draft next week's posts when the queue runs low.
