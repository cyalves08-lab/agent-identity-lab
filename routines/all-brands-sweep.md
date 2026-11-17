# Routine — All-Brands Morning Sweep

> One consolidated read across every brand, every morning. Monitors what's
> actually connected and **honestly labels what isn't** — never guesses.
> Web: set it up at claude.ai/code/routines. CLI: `/schedule`.

## Trigger
Recommended: **weekdays at 8:00 AM** (owner's timezone).

## Connected sources (update as connectors change)
- **Email:** `revcentricmkt@gmail.com`, `rev31holdings@gmail.com`,
  `collette@revcentricmarketing.com`*, `collette@wealth4us.org`*,
  `1tim58life@gmail.com`*  (`*` = authorize in Settings → Connectors; skip any not
  yet live)
- **GHL locations:** RevCentric Marketing (`dsLoLWTch6tbcWJWvyYh`),
  Wealth4Us (`bZSt4nGQmWpvMYSVrVrc`)
- **Instagram (Windsor):** `nspired_connections` (`17841463225967378`);
  `revcentricmarketing` + `wealth4us_withcollette` once reconnected

## What JARVIS does — per brand, then one dashboard
For each brand pull only what's connected. If a source isn't live, print
`(not connected)` — never fabricate data for it.

1. **RevCentric Marketing** (+ Revenue Blueprint, Obvious Choice)
   - Inbox triage: `revcentricmkt@gmail.com` + `collette@revcentricmarketing.com`.
   - GHL (RevCentric Marketing): new leads since yesterday, stage changes, warm
     hand-raisers to work today, today's appointments (once a calendar is set).
2. **Wealth4Us**
   - Inbox: `collette@wealth4us.org` + `1tim58life@gmail.com`.
   - GHL (Wealth4Us): pipeline + appointments.
   - Instagram `wealth4us_withcollette` (once connected).
3. **NspiredConnections**
   - Instagram `nspired_connections`: reach, new followers, engagement, any post
     popping. Flag the week's best-performing post.
4. **Rev31 Holdings**
   - Inbox `rev31holdings@gmail.com`: anything needing a reply.

## Output — one screen, lead with the cross-brand PRIORITY

```
☀️ All-Brands Sweep — {date}

PRIORITY  • The single most important thing across every brand today.

REVCENTRIC   — inbox: {n} need replies · pipeline: {new} new · {warm} warm to work
WEALTH4US    — inbox: {n} · GHL: {appts/opps} · IG: {snapshot or (not connected)}
NSPIRED      — IG: reach {x} · +{y} followers · best post: {…}
REV31 HOLD.  — inbox: {n} need replies

DRAFTS READY — {replies drafted for approval}
GAPS         — {sources not connected right now, so coverage stays honest}
```

## Rules
Read and prepare only. Draft replies for approval; **never send, post, or change
anything without the owner.** Confirm before any GHL write. Never invent data for a
disconnected source — label it `(not connected)` instead.
