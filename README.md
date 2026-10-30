# WorkRadar

**One ranked radar for everything that needs the product manager.**

WorkRadar is an AI-assisted web app for a product manager in a startup of about 50 people. It brings every ask, blocker, approval, meeting request and escalation from Slack, Jira, GitHub, Gmail and Google Calendar into one prioritised list. Every item links back to the exact source message, so the PM reads less and acts faster.

**Gopi Krishna · Cohort 40 · AIR Tribe · AI Product Management (AIPM)**

▶ **Live app:** https://gopikrs9.github.io/workradar/

---

## Live demo
- **Online:** **[gopikrs9.github.io/workradar](https://gopikrs9.github.io/workradar/)**
- **On your computer:** download `index.html` and open it in any browser. No install or server is needed.

## Submission documents
| Deliverable | File |
| --- | --- |
| Product Requirements Document | [docs/WorkRadar_PRD.pdf](docs/WorkRadar_PRD.pdf) |
| AI Workflow Document | [docs/WorkRadar_AI_Workflow.pdf](docs/WorkRadar_AI_Workflow.pdf) |
| UI/UX Design Specification | [docs/WorkRadar_UIUX_Spec.pdf](docs/WorkRadar_UIUX_Spec.pdf) |
| Google Stitch prompts | [docs/Google_Stitch_Prompts.md](docs/Google_Stitch_Prompts.md) |
| Presentation | [docs/WorkRadar_Presentation.pptx](docs/WorkRadar_Presentation.pptx) |

## The problem
A startup PM coordinates with 5 to 50 people a day across five tools. A typical worker receives about 117 emails and 153 chat messages a day and is interrupted about 275 times. The few items that need the PM are buried, unranked and found late. WorkRadar answers four questions every morning:
1. What is my top work today?
2. What happened?
3. What needs my attention now?
4. Who is blocked?

## What the MVP does
| Screen | What it does |
| --- | --- |
| Dashboard | AI daily brief with a rule-based fallback, KPI tiles, done-for-the-day ring, status bar, top priorities, calendar with meeting dots and hover details, who is blocked, team pulse |
| Radar | Ranked feed with type tabs, search, filters by source, priority, status and person, five sort orders, collapsed P3 items, bulk actions, and keyboard shortcuts (J/K to move, E to mark done, O to open) |
| Item detail | AI notes, original extract, score breakdown, people, timeline, and "Open in source" |
| Calendar | Month view with event colours, free slots, and meeting requests with Copy slot and Schedule |
| Team | 50 members with health states: on track, at risk, blocked, overloaded, away |
| Activity Log | Every action with Undo and Restore. Nothing is ever deleted. |
| What Happened | The last 24 hours of team updates, grouped by team |
| Integrations | Connection status, read-only permissions, and demo controls to simulate a Jira or AI outage |
| Settings | Light, dark and system themes; AI brief options; priority rules; team tags; notifications |

Assign, Mark Done and Snooze all work, each with Undo.

## How ranking works
```
Score = min(100, Type + Urgency + Sender + Waiting + Impact)
P1 ≥ 70   ·   P2 40–69   ·   P3 below 40
```
- **Type:** escalation 35, blocker 32, approval 25, ask 18, meeting 15.
- **Why text:** the two biggest score parts appear as the "why" on every row.
- **Low confidence:** items the AI classified with low confidence are capped at P2.
- **Team tags:** `@pm blocker`, `@pm decision` and `@pm sync` override all other rules.

## Product principles
- **Radar, not reader.** Each item is one line, with a link to the original message.
- **Aggregate, never replace.** Teams keep using Slack, Jira, GitHub and Gmail.
- **Privacy by design.** WorkRadar reads only items addressed to the PM and never stores message bodies.
- **Nothing is lost.** Every action can be undone or restored.

## Tech
- **App:** a single self-contained `index.html` file: HTML, CSS and plain JavaScript, with no build step.
- **Data:** mock data for a 50-person startup, shaped like real Slack, Jira, GitHub, Gmail and Calendar events.
- **State:** your actions are saved in the browser's local storage. "Reset demo data" on the Integrations page restores the starting state.
- **AI brief:** runs as a live AI call when the app is hosted as a Claude artifact. Anywhere else, including GitHub Pages, it uses the rule-based brief.

## Roadmap
| Release | Scope | Exit criteria |
| --- | --- | --- |
| MVP (this repo) | One PM, mock data, radar, brief, actions | SUS ≥ 75; task success ≥ 90% |
| V2 pilot | Live read-only connectors; write-back to Jira and GitHub; slot suggestions | Time to clarity < 5 min; missed P1 < 5% |
| V3 scale | 50–250-person teams; multi-PM and founder views; Microsoft Teams and Outlook | Paying teams retained for 3 months |

## Built with AI
- **Research, documents and code:** Claude, used as guide and builder.
- **Screen designs:** Google Stitch.

The AI Workflow document in `docs/` explains the prompts used, what AI generated, what I changed and the key trade-offs.
