# Routine — Morning Briefing

> "Run it before you wake up." Schedule this with `/schedule` so the briefing is
> waiting when the owner starts the day.

## Trigger
Recommended: every weekday at **6:30 AM** (owner's time zone).

```
/schedule run routines/morning-briefing.md every weekday at 6:30am
```

## What JARVIS does

Run these in order and deliver one consolidated briefing. Delegate each block to
the matching subagent.

1. **Inbox** (`inbox-manager`)
   - Triage overnight mail. List anything needing a reply today.
   - Note any new qualified leads (financial pros asking about BrandEdge™).

2. **Calendar** (`scheduler`)
   - Today's schedule, conflicts, gaps.
   - One-line prep per meeting, with the relevant Drive doc if there is one.

3. **Ads & Instagram** (`ads-analyst`)
   - Yesterday's Meta Ads spend + results vs. the prior day.
   - Instagram growth snapshot.
   - Flag (do not execute) any campaign that needs a pause or budget change.

4. **Content** (`content-studio`)
   - What's scheduled to post today, if anything.
   - One suggested post idea for tomorrow, in-voice.

## Output format

```
☀️ RevCentric Morning Briefing — {date}

PRIORITY
  • The single most important thing to handle today.

INBOX        — {n} need replies · {m} new leads
CALENDAR     — {n} meetings · {conflicts}
ADS / IG     — spend {x} · results {y} · {flag}
CONTENT      — posting today: {…} · idea for tomorrow: {…}

DRAFTS READY — {list of drafts created for review}
```

Keep it to one screen. Lead with PRIORITY. Nothing gets sent, posted, or changed
without the owner — this routine reports and prepares, it doesn't act outward.
