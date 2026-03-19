# IdeaForge

**AI-powered idea generation and ranking engine, operated by SureThing.**

Modeled on Google's Idea Generation agent — but ownable, extensible, and wired into your existing pipelines.

---

## How It Works

1. **Define a goal** — what you're trying to figure out or build
2. **Generate ideas** — 20–50 distinct ideas per session using AI
3. **Tournament ranking** — ELO-style pairwise battles on user-defined criteria
4. **Deep analysis** (optional) — market research, market sizing, execution workflow, timeline
5. **Branch-per-idea** — each idea lives on its own Git branch with a full idea card

---

## Workflow Types

| Type | What it does | When to use |
|------|-------------|-------------|
| `standard` | Generate → rank → publish | Quick brainstorm, content angles, feature lists |
| `deep` | Standard + per-idea deep dive | Strategic decisions, new projects, investment choices |

### Deep workflow options
- `market_research` — target audience, competitors, trends, risks
- `market_sizing` — TAM / SAM / SOM estimates
- `workflow` — phased execution plan with tools + success metrics
- `content_plan` — format, channels, cadence, sample angles (for content ideas)
- `timeline` — research → MVP → release date estimates

---

## Repository Structure

```
main branch
├── sessions/
│   └── <session-id>/
│       ├── README.md       ← session index (ranked ideas table, context, resources)
│       └── data.json       ← raw session data (all ideas, ELO scores, matchup history)

idea/<session-id>/<idea-slug> branch (one per idea)
└── sessions/<session-id>/ideas/<slug>/
    └── IDEA.md             ← full idea card (rank, ELO, matchup history, deep analysis)
```

---

## Sessions

| Session | Date | Goal | Workflow | Ideas |
|---------|------|------|----------|-------|

---

## Running a Session

Sessions are operated by SureThing automatically. To request a session:
1. Tell SureThing your goal in chat
2. Choose workflow type (standard / deep)
3. Configure deep options if needed
4. SureThing generates ideas, runs the tournament, and commits everything here

---

*Powered by SureThing — operated for Martin Rončka*
