# agent-identity-lab

**Agent Identity Lab™ by RevCentric Marketing** — and the home of **GRIOT**,
RevCentric's Claude Code operating assistant.

This repo is set up as your own "Griot": Claude Code plugged into the apps the
business already uses, one connector at a time. It runs marketing operations
(inbox, ads, calendar, content, scheduling) and can also handle the client-facing
**BrandEdge™** brand-architecture process.

## Quick start

1. Open this repo in **Claude Code**.
2. It reads `CLAUDE.md` automatically and becomes GRIOT.
3. Authorize the connectors you want (see `docs/GRIOT-SETUP.md`).
4. Talk to it: *"Triage my inbox," "How did ads do yesterday?," "Run my morning
   briefing."*

## What's here

| Path | What it is |
|------|-----------|
| `CLAUDE.md` | GRIOT's identity and operating rules |
| `.claude/agents/` | The subagent team (inbox, ads, content, GHL scheduler, BrandEdge, KB) |
| `knowledge-base/` | Business knowledge — lets GRIOT answer customers in your voice |
| `routines/` | Scheduled work, e.g. the morning briefing |
| `clients/` | Saved BrandEdge™ reports |
| `.mcp.json` | Connector config |
| `docs/GRIOT-SETUP.md` | Full setup + status of every capability |
| `RCM_AgentIDLab_AI HTML.html` | The original Agent Identity Lab™ dashboard |

## Capabilities at a glance

Inbox triage · Meta Ads + Instagram analytics · GoHighLevel schedule + appointment
prep · on-brand content + Canva design · a markdown knowledge base · a team of
subagents · scheduled routines · the client-facing BrandEdge™ interview.

See **[docs/GRIOT-SETUP.md](docs/GRIOT-SETUP.md)** for setup and what still needs
your keys (voice, RevenueCat, Buffer/Postiz, browser).
