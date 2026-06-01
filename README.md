# Tableau Cloud — Agent Concept

An interactive UI concept showing a future-state Tableau Cloud where an AI agent is the primary interface. Built as a product concept demo for Tableau's product team.

## Live demo

**[https://vbandarupalli-oss.github.io/tableau-agent/](https://vbandarupalli-oss.github.io/tableau-agent/)**

## What it demonstrates

A conversation-as-canvas experience inside Tableau Cloud where the agent removes data-to-insight friction for every user type — from a new hire discovering what they have access to, to a power analyst prepping a QBR.

### The full Vik workflow (end to end)

1. **Login** — agent greets with project resume, QBR context surfaced immediately
2. **Asset discovery** — new user asks what they have access to, locked content triggers access request
3. **Forecast dashboard** — live viz renders in thread via Embed API, agent proactively notices key signals
4. **EMEA analysis** — Pulse-grade reasoning, causal narrative, role-aware recommendations with urgency tiers
5. **Contextual nudge** — agent surfaces APAC pipeline drop, access-verified before showing
6. **Slack share** — static snapshot via REST API, no live data leaves Tableau
7. **Salesforce update** — forecast record written via Salesforce MCP, audit logged
8. **QBR deck** — 3 slides assembled from REST API image exports
9. **Session summary** — everything saved to project, next actions surfaced

### Superstore datasource flow

- Agent recognises context switch and suggests new project
- Connects to Superstore via VizQL Data Service
- Real data analysis: top products, category margins, loss-makers, region comparison
- Pulse-grade reasoning: Furniture margin crisis, Canon copier opportunity, South region gap

### Analyst mode

Click the **Analyst mode** badge in the subnav to unlock:
- **Connect to data** — 8 connectors (Snowflake, Google Sheets, Salesforce, Excel, Azure SQL, PostgreSQL, S3, Oracle)
- **Prep your data** — agent-guided Tableau Prep flow builder
- **Create an agent** — 2-step builder, publishes to Tableau Cloud + Slack

## Design principles

- **Agent is summoned, not ambient** — one click unlocks the canvas
- **Every response is a typed object** — viz cards, insight lists, Slack previews, SF records
- **Projects give sessions memory** — workstreams persist, accumulate, and resume
- **Trust bar is permanent** — all queries execute under the user's own OAuth token
- **Access foundation** — agent never operates with elevated privileges, RLS enforced by Tableau Server

## API grounding

| Feature | Tableau API |
|---|---|
| Live dashboard in thread | Embedding API v3 |
| Data reasoning | VizQL Data Service |
| Content discovery | REST API |
| Image export (Slack/deck) | REST API `/views/{id}/image` |
| Pulse metrics | Tableau Pulse API |
| Auth | Connected Apps + OAuth |
| Slack share | Slack MCP |
| Salesforce write | Salesforce MCP |

## How to run locally

```bash
git clone https://github.com/vbandarupalli-oss/tableau-agent.git
cd tableau-agent
open index.html
```

Or just visit the GitHub Pages URL above — no setup needed.

## How to present it

Open the live URL, click **"Open my forecast dashboard"** or type anything in the search box. The full Vik journey takes about 3 minutes end to end. Use the capability buttons at the bottom of the thread to jump to specific parts of the workflow.

**Keyboard shortcut:** press Enter after typing in the input box.

## Project switching

Click **QBR prep · Q3** or any project in the sidebar to switch between sessions. Each project maintains its own thread, context, and artifact history.

## Built with

- Vanilla HTML / CSS / JS — no framework dependencies
- Tableau design language (Enterprise Blue `#1473E6`, navy `#003666`)
- Real Superstore data (Sample Superstore dataset)
- Scripted workflow with fuzzy intent matching

---

*This is a product concept demo, not a production application. Built to show Tableau's product team what a unified agent experience could look like inside Tableau Cloud.*
