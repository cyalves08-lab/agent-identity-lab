# Building Your Own JARVIS — Setup & Status

This repo is configured as **JARVIS**, RevCentric Marketing's Claude Code
operator. The idea (straight from the "Build Your Own Jarvis" guide): it's mostly
**Claude Code plugged into the apps you already use, one connector at a time**. An
MCP is just a direct line between Claude and one app.

Below is every capability from the guide, mapped to what's already built here and
what still needs your key.

## Status map

| What you're building | Tool | Status in this repo |
|----------------------|------|---------------------|
| The JARVIS dashboard | Drop a screenshot into Claude Code | ✅ Your `RCM_AgentIDLab_AI HTML.html` dashboard is the source; brand pulled into the KB |
| Talk to it + voice | `/voice` (talk to it) + ElevenLabs (talk back) | ⚙️ Needs your ElevenLabs key — see below |
| Let it use your browser | Claude for Chrome / Playwright MCP | ⚙️ Optional — add when needed |
| Track revenue | RevenueCat MCP | ⚙️ Needs your RevenueCat key |
| Auto-post content | Buffer / Postiz MCP | ⚙️ `content-studio` drafts + designs; connect Buffer/Postiz to publish |
| Instagram analytics | Meta dev app + token | ✅ Via Windsor.ai (`instagram_public`) — `ads-analyst` |
| Read + run ads | Meta Ads connector | ✅ Via Windsor.ai (`facebook`) — `ads-analyst` |
| Read your inbox | Gmail MCP / Google Workspace CLI | ✅ Gmail wired — `inbox-manager` |
| Answer customers in your voice | Business knowledge base in markdown | ✅ `knowledge-base/` + `knowledge-keeper` |
| A team of specialized agents | Subagents | ✅ Six agents in `.claude/agents/` |
| Run it before you wake up | Routines via `/schedule` | ✅ `routines/morning-briefing.md` |

Legend: ✅ built & ready to use · ⚙️ scaffolded, needs your credential or choice.

## What's in the repo

```
CLAUDE.md                 JARVIS's identity + operating rules (read on every session)
.mcp.json                 Connector config (fill in placeholders)
.claude/agents/           The subagent team
knowledge-base/           Business knowledge — answers customers in your voice
routines/                 Scheduled work (morning briefing)
clients/                  Saved BrandEdge™ reports per client
docs/JARVIS-SETUP.md      This file
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
- **Gmail** → `inbox-manager`. Authorize Gmail, then ask JARVIS to triage your inbox.
- **Windsor.ai** (Meta Ads + Instagram) → `ads-analyst`. Set `WINDSOR_API_KEY`.
  Connector slugs: `facebook` (ads), `instagram_public` (IG organic).
- **Google Calendar + Drive** → `scheduler`. Authorize, then run the morning briefing.
- **Canva** → `content-studio`. Authorize for design generation.

### Needs your key (do these when ready)
- **Voice** — add `/voice` for talking to JARVIS; add an **ElevenLabs** MCP/API
  key for it to talk back in a chosen voice.
- **RevenueCat** — add the RevenueCat MCP + key to track revenue.
- **Buffer or Postiz** — add one to let `content-studio` actually publish, not
  just draft.
- **Browser** — add Claude for Chrome (simple) or a Playwright MCP (advanced) if
  you want JARVIS to drive a browser.

## Using JARVIS

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
- JARVIS drafts and reports freely but **confirms before anything outward-facing**
  — sending mail, publishing posts, changing ad budgets, or editing calendars.
