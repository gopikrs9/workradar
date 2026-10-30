# WorkRadar — Google Stitch Prompts
Gopi Krishna · AI Product Management, AIR Tribe · Cohort 40

## How to use
1. Open Google Stitch → choose **Web** (desktop) → start a new project called "WorkRadar".
2. Paste **Prompt 0 (style)** together with **Prompt 1 (Dashboard)** as your first message.
3. For each next screen, paste only that screen's prompt in the same project. Each prompt repeats a one-line style reminder so screens stay consistent.
4. If Stitch drifts in colour or layout, reply: "Keep the same sidebar, colours and fonts as the Dashboard screen."
5. Generate the dark theme last (Prompt 10).

---

## Prompt 0 — Global style (paste with Prompt 1)

Design a desktop web app called **WorkRadar**, an AI work radar for a startup product manager. It collects asks, blockers, approvals, meeting requests and escalations from Slack, Jira, GitHub, Gmail and Google Calendar into one ranked list, and every item links back to the original message.

Visual style:
- Font Inter. Body 14px, headings semibold. Numbers use tabular figures.
- Left sidebar 248px wide, dark navy #0B1B3F. Logo "WorkRadar" with a small radar icon at the top. Navigation items with line icons: Dashboard, Radar (badge 12), Calendar, Team, Activity Log, What Happened, Integrations, Settings. Inactive text #AEBBD6. Active item has a filled #2454E6 rounded background with white text. At the bottom of the sidebar: "Connected sources" with Slack, Jira, GitHub, Gmail, Calendar each showing a green dot and "2m".
- Top bar 64px: page title on the left, search field with "Search people, items, tools" and a ⌘K hint, text "All sources synced 2 min ago", notification bell with a red count, light/dark theme toggle, user avatar "Priya Sharma, Product Manager".
- Page background #F5F7FB. White cards, 12px radius, 1px border #E3E8EF, very soft shadow.
- Accent blue #2454E6 for links, primary buttons and selected states.
- Priority chips (rounded rectangle): P1 Critical red text #B42318 on #FEE4E2; P2 High orange text #C4320A on #FFE6D5; P3 Normal grey text #475467 on #F2F4F7.
- Status pills (pill shape with a coloured dot): Not started grey #98A2B3, In progress blue #2E90FA, Pending yellow #EAAA08, Blocked magenta #DD2590, Assigned teal #15B79E, Scheduled indigo #6172F3, Snoozed violet #7A5AF8, Done green #17B26A.
- Use real-looking profile photos with name and job title. Lucide-style line icons. No emoji. Clean, calm, lots of white space.

---

## Prompt 1 — Dashboard

Screen: **Dashboard**.

Header: "Good morning, Priya" and below it "Tuesday, 27 Oct · Product · 50 people".

Row 1 — a light blue card (#EAF0FE) titled "Your day in 30 seconds" with an AI sparkle icon, a "Regenerate" button and a thumbs-up icon. Four short columns inside:
- TOP WORK TODAY: "Approve pricing page copy for Arun (founder) and review PR #1842 before Thursday's release."
- WHAT HAPPENED: "9 items closed. Meera merged search indexing; Ananya cleared 6 bugs."
- NEEDS YOU NOW: "Payment webhook errors at 3% in production; Acme Corp escalation email."
- WHO IS BLOCKED: "Rahul (SSO keys, 2 days) and Sneha (design sign-off, 1 day)."

Row 2 — four KPI tiles:
- "Needs you" 7, small grey text "+2 since yesterday"
- "Blocked" 2 in magenta, "longest 2d 4h"
- "In progress" 14 in blue, "across 6 teams"
- "Done for the day" with a circular progress ring at 62% in amber and text "5 of 8 closed"

Row 3 — a full-width horizontal stacked bar titled "Today's work by status" with segments and legend: Done 9 (green), In progress 14 (blue), Pending 6 (yellow), Blocked 2 (magenta), Snoozed 1 (violet).

Row 4 — two columns:
Left (wide) card "Top priorities" with link "Open Radar →" and 5 rows. Each row: rank number, priority chip, type chip with icon, one-line title, grey reason line, source logo with reference, owner avatar, status pill, age.
1. P1 Critical · Escalation · "Payment webhook failing — 3% checkout errors" · why: release at risk, rising for 40 min · JIRA PAY-412 + SLACK #incidents · Karan Rao · In progress · 40m
2. P1 Critical · Blocker · "Rahul waiting on SSO API keys from Platform Security" · why: waiting 2 days, sprint goal at risk · JIRA AUTH-221 · Rahul Mehta · Blocked · 2d
3. P2 High · Approval · "Arun: approve pricing page copy today" · why: founder, due today · GMAIL · Arun Kapoor · Pending · 3h
4. P2 High · Approval · "Review PR #1842 — billing schema migration" · why: gates Thursday release · GITHUB api-core · Meera Nair · Pending · 1d
5. P2 High · Meeting request · "Sneha wants to sync on onboarding flow" · why: blocks design sign-off · SLACK #design · Sneha Iyer · Not started · 5h

Right column, two stacked cards:
- "Calendar" card: month view October 2026, Monday first. Small coloured dots under dates (blue = team meeting, teal = 1:1, orange = customer, violet = review). 27 Oct is today with a blue ring. Show a hover popover open on 28 Oct listing: "10:00 Stand-up (blue)", "13:30 Acme Corp call (orange)", "16:00 Sprint review (violet)", each with 2–3 attendee avatars. Under the month: "Today" list — 10:00 Stand-up, 11:30 Free · 60 min (green outline), 14:00 1:1 with Rahul, 16:00 Free · 30 min.
- "Who is blocked" card: two rows with photo, name, title, blocker, days waiting in magenta:
  - Rahul Mehta, Backend Engineer — "SSO API keys from Platform Security" — 2d 4h
  - Sneha Iyer, Product Designer — "Onboarding design sign-off" — 1d 2h

Row 5 — full-width "Team pulse" card: groups of overlapping avatars with labels: On track 38 (green pill), At risk 6 (yellow), Blocked 2 (magenta), Overloaded 3 (orange), Away 1 (grey). Link "View team →".

---

## Prompt 2 — Radar (priority list)

Same WorkRadar sidebar, colours and fonts as the Dashboard. Active nav item: Radar.

Screen: **Radar**. Title "Radar" with grey subtitle "32 open · ranked by priority · updated 2 min ago". Right side buttons: "Bulk actions" and a blue "Export".

Tabs with counts: All 32 (selected), Blockers 2, Escalations 1, Approvals 6, Asks 9, Meetings 4.

Filter bar: search "Search items, people, references…", dropdowns Source, Priority, Status, Person, Team, Date, and a "Sort: Priority score" dropdown. Active filter chips row below: "Priority: P1, P2 ×" and "Clear all".

Table with columns: checkbox · # · Priority & item · Source · People · Status · Age · Actions.
Each "Priority & item" cell: priority chip + type chip, bold one-line title, grey "why:" line. Actions: icon buttons "Open ↗", "Done", "Snooze", "Assign". P1 rows have a thin red left border.

Rows:
1. P1 Critical · Escalation · Payment webhook failing — 3% checkout errors · why: release at risk · JIRA PAY-412 / SLACK #incidents · Karan Rao · In progress · 40m
2. P1 Critical · Blocker · Rahul waiting on SSO API keys · why: waiting 2 days · JIRA AUTH-221 · Rahul Mehta + Platform Security · Blocked · 2d
3. P2 High · Approval · Approve pricing page copy · why: founder, due today · GMAIL · Arun Kapoor · Pending · 3h
4. P2 High · Approval · Review PR #1842 — billing migration · why: gates Thursday release · GITHUB api-core · Meera Nair · Pending · 1d
5. P2 High · Escalation · Acme Corp: CSV export broken · why: top customer, renewal in 3 weeks · GMAIL · unassigned (dashed avatar) · Not started · 3h
6. P2 High · Meeting request · Sneha: sync on onboarding flow · why: blocks sign-off · SLACK #design · Sneha Iyer · Not started · 5h
7. P2 High · Ask · Vikram: confirm scope for search filters · why: sprint planning tomorrow · JIRA SRCH-88 · Vikram Singh · Pending · 6h
8. P3 Normal · Ask · Karthik requests on-call swap for Saturday · why: needs answer by Friday · SLACK DM · Karthik Rao · Not started · 6h

Below the table: a collapsed row "Show 18 P3 items ⌄" and pagination "1 2 3 →".

Bottom-left toast: green check "Marked done · Saved in WorkRadar only" with an "Undo" link.

---

## Prompt 3 — Item detail drawer

Same WorkRadar style. Show the Radar screen dimmed in the background with a **480px drawer** sliding in from the right.

Drawer content for "Rahul waiting on SSO API keys from Platform Security":
- Header: P1 Critical chip, Blocked pill, Blocker type chip with lock icon. References "JIRA · AUTH-221" and "SLACK · DM" in monospace. "Opened 2 days ago". Close (×) icon.
- Section "AI notes" (small sparkle icon, light blue background), 3 bullets:
  - "Rahul asked Platform Security for SSO keys twice; no reply since Sunday."
  - "AUTH-221 is part of this sprint's goal; 2 other stories depend on it."
  - "Suggested: message Priya's counterpart in Platform Security, Daniel Reed."
- Section "Why ranked · score 73": five horizontal bars with labels and points — Type 32, Urgency 6, Sender 5, Waiting 20, Impact 10.
- Section "People": Rahul Mehta, Backend Engineer (requester); Daniel Reed, Platform Security Lead (blocked by); Priya Sharma, Product Manager (you). Each with photo.
- Section "Timeline": "Sun 10:12 · Rahul asked in #platform-security", "Mon 16:40 · Rahul followed up", "Tue 09:05 · AUTH-221 moved to Blocked".
- Section "Linked items": "Also in Slack #backend".
- Footer buttons: primary blue "Open in Jira ↗", secondary "Done", "Snooze", "Assign".

---

## Prompt 4 — Calendar

Same WorkRadar style. Active nav: Calendar.

Screen: **Calendar**. Title "Calendar". Segmented control Month (selected) / Week / Day. Legend row: Team meeting (blue dot #2454E6), 1:1 (teal #15B79E), Customer (orange #F79009), Review (violet #7A5AF8), Pending request (dashed yellow outline), Free slot (green outline).

Main area: large month grid for October 2026. Up to three small coloured dots under each date, "+2" where more. Today, 27 Oct, ringed in blue. A hover popover open on Thursday 29 Oct showing:
- "09:30 Stand-up" (blue bar) with 4 avatars
- "12:00 Globex onboarding call" (orange bar) with 2 avatars and "Google Meet"
- "15:00 Design review" (violet bar) with 3 avatars
- Pending (dashed yellow): "Design sync requested by Sneha" with button "Copy free slot 11:30"
- Link "Open in Google Calendar ↗"

Right panel (320px) "Meeting requests · 4": each row has requester photo, name, source logo, requested time, next free slot chip in green, and "Open request ↗":
- Sneha Iyer · Slack #design · "This week" · Free: Thu 11:30
- Arun Kapoor · Gmail · "Pricing review, Wed" · Free: Wed 16:00
- Vikram Singh · Jira SRCH-88 · "Before planning" · Free: Wed 11:00
- Lisa Wong (Acme Corp) · Gmail · "Escalation call" · Free: Thu 14:00

---

## Prompt 5 — Team

Same WorkRadar style. Active nav: Team.

Screen: **Team**. Title "Team" with subtitle "50 people · 6 teams". Summary tiles: Members 50, On track 38 (green), At risk 6 (yellow), Blocked 2 (magenta), Overloaded 3 (orange). Toggle Cards / Table (Cards selected). Filters: Team, Health, Role. Sort: Health.

Grid of 12 member cards (4 per row). Each card: profile photo 40px with presence dot, name, job title, team, health pill, label "Sprint progress" with a progress bar and %, "Open 5 · Blocked 1", "Last active 12m", Slack and email icon buttons, and a ⋮ menu. Cards with Blocked health have a soft magenta background #FDF2FA; At risk cards a soft yellow #FEFBE8.
Members:
1. Rahul Mehta · Backend Engineer · Backend · Blocked · 60%
2. Sneha Iyer · Product Designer · Design · Blocked · 55%
3. Karan Rao · DevOps Engineer · Platform · At risk · 70%
4. Vikram Singh · Frontend Engineer · Frontend · Overloaded · 66%
5. Meera Nair · Backend Engineer · Backend · On track · 82%
6. Ananya Das · QA Engineer · QA · On track · 90%
7. Arjun Patel · Mobile Engineer · Mobile · On track · 78%
8. Riya Patel · Product Designer · Design · On track · 74%
9. Karthik Rao · Backend Engineer · Backend · At risk · 61%
10. Neha Gupta · Associate PM · Product · On track · 85%
11. Daniel Reed · Platform Security Lead · Platform · On track · 80%
12. Lisa Chen · Customer Success · Support · Away (grey) · 70%

---

## Prompt 6 — Activity Log

Same WorkRadar style. Active nav: Activity Log.

Screen: **Activity Log**. Title "Activity Log" with subtitle "Everything you did in WorkRadar. Nothing is deleted — restore any item for 30 days."

Summary row of 4 small tiles: Done 9 (green), Assigned 4 (teal), Snoozed 3 (violet), Sources opened 12 (blue).

Tabs: Today (selected), This week, Done archive, Snoozed, Assigned by me. Filter dropdown "Action type".

Vertical timeline, newest first. Each entry: time, action icon in a coloured circle, sentence, person avatar, status pill, source chip, and a link on the right ("Undo" for today's actions, "Restore" for done items):
- 11:42 · Assigned "Payment webhook failing" to Karan Rao · Assigned (teal) · JIRA PAY-412 · Undo
- 11:30 · Opened "Review PR #1842" in GitHub · source opened (blue) · GITHUB · —
- 11:05 · Marked done "Approve Q4 roadmap deck" · Done (green) · GMAIL · Restore
- 10:48 · Snoozed "Karthik on-call swap" until tomorrow 9:00 · Snoozed (violet) · SLACK · Undo
- 10:20 · Scheduled "Design sync with Sneha" for Thu 11:30 · Scheduled (indigo) · CALENDAR · Undo
- 09:55 · Marked done "Reply to Globex security questionnaire" · Done · GMAIL · Restore
- 09:31 · Assigned "CSV export bug" to Vikram Singh · Assigned · JIRA SRCH-91 · Undo

---

## Prompt 7 — What Happened

Same WorkRadar style. Active nav: What Happened.

Screen: **What Happened**. Title with subtitle "Last 24 hours across your team". Filters: Team, Source, Time window "24 hours".
Updates grouped by team headers (Backend, Frontend, Design, QA, Platform). Each update row: person photo, name, action sentence, source logo + reference, time:
- Backend: Meera Nair merged PR #1830 "Search indexing" · GITHUB · 09:12
- QA: Ananya Das closed 6 bugs in Mobile-Web · JIRA · 08:47
- Platform: Incident #inc-88 opened · SLACK #incidents · 08:30
- Frontend: Vikram Singh moved AUTH-219 to In Review · JIRA · 08:05
- Design: Riya Patel shared onboarding v3 in #design · SLACK · 07:40
- Backend: Release 4.1.2 tagged · GITHUB · Yesterday 19:10

---

## Prompt 8 — Integrations & Settings

Same WorkRadar style. Active nav: Integrations.

Screen: **Integrations & Settings**. Tabs: Integrations (selected), Appearance, AI brief, Priority rules, Team tags, Notifications.

Integrations tab: a 3-column grid of cards. Each card: tool logo, name, one-line description, status badge, "Last sync", toggle, and "Manage" link:
- Slack — "Mentions, DMs and @pm tags" — Connected (green) — 2 min ago — toggle on
- Jira — "Assigned, blocked and P1 issues" — Connected — 2 min ago — on
- GitHub — "Review requests and failing release checks" — Connected — 3 min ago — on
- Gmail — "Mail sent to you from founders, customers, leads" — Connected — 5 min ago — on
- Google Calendar — "Meetings and free/busy only" — Needs attention (amber) with "Reconnect" button — 1 h ago — on
- Card "Request an integration" with a plus icon (Linear, Notion, Microsoft Teams)

Under the grid: a small panel "Permissions" stating "Read-only access · message bodies are never stored · disconnect anytime".

Also show, on the right side, a compact "Appearance" preview: three selectable tiles Light (selected), Dark, System, and density options Comfortable / Compact.

---

## Prompt 9 — Empty and error states

Same WorkRadar style.

One screen with four example panels in a 2×2 grid, each labelled with a small overline:
1. "Radar · all caught up": large green check circle, "You're all caught up", "9 items closed today · about 1 h 20 min saved", button "View done items".
2. "Search · no results": magnifier icon, "No results for 'kubernets upgrade'", "Did you mean kubernetes upgrade?", button "Clear filters".
3. "Sync failure banner": an amber banner "Jira couldn't sync · showing data from 47 min ago" with buttons "Retry" and "Reconnect", shown on top of a faded list.
4. "AI brief unavailable": the brief card in grey with text "Summary couldn't be generated. 4 need you · 2 blocked · 9 done" and a "Try again" button.

---

## Prompt 10 — Dark theme

Recreate the **Dashboard** screen in dark theme. Page background #0B1220, cards #111A2E, borders #24314D, primary text #E6EAF2, secondary text #9AA6BD, sidebar #080F1F, accent #4C7DFF. Keep all priority and status colours, with backgrounds at 16% opacity and lighter text. Keep layout and content identical.

---

## Prompt 11 (optional) — First-run onboarding

Same WorkRadar style. A centred 3-step onboarding modal over a blurred dashboard. Step indicator 1 · 2 · 3.
- Step 1 "Connect your tools": logos of Slack, Jira, GitHub, Gmail, Google Calendar with "Connect" buttons.
- Step 2 "Share three tags with your team": code-style chips "@pm blocker", "@pm decision", "@pm sync" with one-line meanings and a "Copy team guide" button.
- Step 3 "How priority works": P1 Critical, P2 High, P3 Normal chips with one-line explanations.
Buttons: "Back", primary "Next".

---

## Checklist after generating
- Same sidebar, colours and font on every screen
- P1 is the only red; Blocked is magenta
- Every item shows a source logo and reference
- People have photos, names and titles
- Calendar dots and the hover popover are visible
- Undo/Restore visible in toast and Activity Log
- Export each screen (PNG) and share the Stitch project link for the submission
