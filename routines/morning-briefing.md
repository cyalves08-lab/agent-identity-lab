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

2. **Schedule** (`scheduler`)
   - Today's GoHighLevel appointments, conflicts, gaps.
   - One-line prep per appointment, with the relevant Drive doc if there is one.
   - Read-only: note any booking changes to make in GHL; don't claim to make them.

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
SCHEDULE     — {n} appointments (GHL) · {conflicts}
ADS / IG     — spend {x} · results {y} · {flag}
CONTENT      — posting today: {…} · idea for tomorrow: {…}

DRAFTS READY — {list of drafts created for review}
```

Keep it to one screen. Lead with PRIORITY. Nothing gets sent, posted, or changed
without the owner — this routine reports and prepares, it doesn't act outward.

## Delivery — have it waiting for the owner

After the briefing text is ready, deliver it two ways so it's there the moment the
owner logs in:

1. **Email draft to the owner.** Create a Gmail draft addressed to
   `cyalves08@gmail.com`, subject `☀️ Morning Briefing — {date}`, body = the full
   briefing. (The Gmail connector drafts rather than sends, so it lands in Drafts —
   delivering to the owner's own address is not an outward-facing action.)

2. **Voice narration ("read it to me").** Generate an audio (MP3) reading of the
   briefing using the configured voice connector, in the JARVIS voice. Write a
   tight spoken version first — lead with the PRIORITY line, then a sentence each
   for inbox, schedule, ads/IG, and content. Keep it under ~60 seconds. Attach or
   link the audio file in the email draft and in the run output so the owner can
   press play.

   Voice connector: ElevenLabs (preferred — set a British "JARVIS" voice) once a
   key is added; otherwise use whatever TTS connector is enabled on the routine.
   See `docs/JARVIS-SETUP.md` → "Voice".
