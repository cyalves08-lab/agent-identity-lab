# Routine — Morning Briefing

> "Run it before you wake up." A short, one-screen brief waiting every morning.
> Web: set it up at claude.ai/code/routines. CLI: `/schedule`.

## Trigger
Recommended: **weekdays at 8:00 AM** (owner's time zone).

- **Web (Claude Code on the web):** create a routine at **claude.ai/code/routines**,
  daily/weekday 8:00 AM, repo `agent-identity-lab`, with the prompt below.
- **CLI:** `/schedule run routines/morning-briefing.md every weekday at 8am`

## What JARVIS does

Run these in order and deliver ONE consolidated, one-screen brief. Lead with the
single most important thing. Report and prepare — don't send, post, or change
anything outward without the owner (drafting is fine).

1. **Inbox** — the RevCentric business inbox (`revcentricmkt@gmail.com`).
   - Triage overnight mail: what needs a reply today, grouped (Leads · Clients ·
     Ops · Noise).
   - Flag new qualified leads. Draft replies for the owner to approve (the
     connector can send, but JARVIS holds for a yes).

2. **Schedule & pipeline** — GoHighLevel, **direct** (not read-only).
   - Locations: **RevCentric Marketing** and **Wealth4Us**.
   - Today's appointments, conflicts, gaps; one-line prep each.
   - New opportunities / stage changes worth noting. JARVIS can update GHL, but
     confirms before writing.

3. **Instagram** — via Windsor.ai.
   - `nspired_connections` snapshot: reach, new followers, any post popping.
   - Note: Meta Ads + the other IG accounts aren't connected in Windsor right now,
     so say "ads data unavailable — reconnect in Windsor" rather than guessing.

4. **Content** — what's scheduled to post today (if anything) + one on-brand idea
   for tomorrow.

## Output format

```
☀️ RevCentric Morning Briefing — {date}

PRIORITY
  • The single most important thing to handle today.

INBOX     — {n} need replies · {m} new leads   (drafts ready: {…})
SCHEDULE  — {n} appts today · {conflicts} · pipeline: {…}
INSTAGRAM — nspired: reach {x} · new followers {y} · {anything popping}
CONTENT   — posting today: {…} · idea for tomorrow: {…}
```

## Delivery
Draft the finished brief into the RevCentric inbox (`revcentricmkt@gmail.com`) so
it's waiting, and leave it in the run output. Nothing is sent, posted, or changed
without the owner — this routine reports and prepares.
