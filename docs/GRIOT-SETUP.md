# Building Your Own GRIOT — Setup & Status

This repo is configured as **GRIOT**, RevCentric Marketing's Claude Code
operator. The idea (straight from the "Build Your Own Griot" guide): it's mostly
**Claude Code plugged into the apps you already use, one connector at a time**. An
MCP is just a direct line between Claude and one app.

Below is every capability from the guide, mapped to what's already built here and
what still needs your key.

## Status map

| What you're building | Tool | Status in this repo |
|----------------------|------|---------------------|
| The GRIOT dashboard | Drop a screenshot into Claude Code | ✅ Your `RCM_AgentIDLab_AI HTML.html` dashboard is the source; brand pulled into the KB |
| Talk to it + voice | `/voice` (talk to it) + ElevenLabs (talk back) | ⚙️ Needs your ElevenLabs key — see below |
| Let it use your browser | Claude for Chrome / Playwright MCP | ⚙️ Optional — add when needed |
| Track revenue | RevenueCat MCP | ⚙️ Needs your RevenueCat key |
| Auto-post content | Buffer / Postiz MCP | ⚙️ `content-studio` drafts + designs; connect Buffer/Postiz to publish |
| Instagram analytics | Meta dev app + token | ✅ Via Windsor.ai (`instagram_public`) — `ads-analyst` |
| Read + run ads | Meta Ads connector | ✅ Via Windsor.ai (`facebook`) — `ads-analyst` |
| Scheduling / calendar | GoHighLevel (via Windsor.ai) | ⚙️ Read-only — connect GHL once at Windsor (see below) — `scheduler` |
| Read your inbox | Gmail MCP / Google Workspace CLI | ✅ Gmail wired — `inbox-manager` |
| Answer customers in your voice | Business knowledge base in markdown | ✅ `knowledge-base/` + `knowledge-keeper` |
| A team of specialized agents | Subagents | ✅ Six agents in `.claude/agents/` |
| Run it before you wake up | Routines via `/schedule` | ✅ `routines/morning-briefing.md` |

Legend: ✅ built & ready to use · ⚙️ scaffolded, needs your credential or choice.

## What's in the repo

```
CLAUDE.md                 GRIOT's identity + operating rules (read on every session)
.mcp.json                 Connector config (fill in placeholders)
.claude/agents/           The subagent team
knowledge-base/           Business knowledge — answers customers in your voice
routines/                 Scheduled work (morning briefing)
clients/                  Saved BrandEdge™ reports per client
docs/GRIOT-SETUP.md      This file
RCM_AgentIDLab_AI HTML.html   The original Agent Identity Lab™ dashboard
```

## Wiring the connectors

You have two paths for most apps:

- **One-click connectors** in the Claude desktop/web apps (Gmail, Google
  Calendar, Google Drive, Canva, Windsor.ai, etc.) — easiest; just authorize.
- **`.mcp.json` in this repo** for the Claude Code CLI — edit the file, set the
  env vars, then `claude mcp list` to confirm. Claude Code skips servers it can't
  reach, so partial setup is fine.

### Already available / wired
- **Gmail** → `inbox-manager`. Authorize Gmail, then ask GRIOT to triage your inbox.
- **Windsor.ai** (Meta Ads + Instagram) → `ads-analyst`. Set `WINDSOR_API_KEY`.
  Connector slugs: `facebook` (ads), `instagram_public` (IG organic).
- **Google Drive** → `scheduler` (meeting docs). Authorize for document lookups.
- **Canva** → `content-studio`. Authorize for design generation.

### Scheduling — GoHighLevel (read-only)
The `scheduler` agent and morning briefing read your schedule from **GoHighLevel**
through Windsor.ai (slug `gohighlevel`).

1. Connect GHL once at **https://onboard.windsor.ai?datasource=gohighlevel** (this
   links your GHL account to the same Windsor key GRIOT already uses).
2. After that, ask GRIOT *"what's on my schedule today?"* or run the morning briefing.

**Limitation:** Windsor's GHL connector is **read-only** — GRIOT can read
appointments, contacts, and pipeline, but **cannot book or move appointments**.
It will recommend the change and you make it in GHL. (To let GRIOT write to GHL
directly, add a GoHighLevel API/MCP connector later — noted under "needs your key".)

### Needs your key (do these when ready)
- **Voice** — add `/voice` for talking to GRIOT; add an **ElevenLabs** MCP/API
  key for it to talk back. Pick a **deep male voice with a British or African
  accent** to match the GRIOT persona (`knowledge-base/05-griot-persona.md`):
  the sharp, worldly, dry-witted confidant — the "Black GRIOT." This also powers
  the **spoken morning briefing** — the daily routine writes the briefing in that
  persona, narrates it to an MP3, and attaches it to the email draft, so it's read
  to you when you log in. Until a voice key is added, the routine still delivers
  the written briefing; add the key (and allow the voice provider's domain on the
  routine's environment) to turn on the audio. A no-key option: enable a TTS
  connector already on your account and the routine will use it instead — voice
  selection there is more limited, so the accent may not match.
- **RevenueCat** — add the RevenueCat MCP + key to track revenue.
- **Buffer or Postiz** — add one to let `content-studio` actually publish, not
  just draft.
- **Browser** — add Claude for Chrome (simple) or a Playwright MCP (advanced) if
  you want GRIOT to drive a browser.

## Using GRIOT

Open Claude Code in this repo and just talk to it. Examples:

- "Triage my inbox and draft replies." → `inbox-manager`
- "How did Meta Ads do yesterday? Anything I should pause?" → `ads-analyst`
- "Draft three posts for this week and make the graphics." → `content-studio`
- "What's my day look like?" → `scheduler`
- "Run a BrandEdge interview for {client}." → `brandedge-strategist`
- "How would we answer: 'do you guarantee more sales?'" → `knowledge-keeper`
- "Run my morning briefing." → `routines/morning-briefing.md`

Schedule the briefing so it's ready before you wake up:

```
/schedule run routines/morning-briefing.md every weekday at 6:30am
```

## Security notes
- Never commit real keys. `.gitignore` excludes `.env`. Put secrets in env vars,
  not in `.mcp.json`.
- GRIOT drafts and reports freely but **confirms before anything outward-facing**
  — sending mail, publishing posts, changing ad budgets, or editing calendars.
