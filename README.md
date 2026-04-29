# ExpertFlow

> AI-powered expert network platform — match clients to domain experts, manage consultation requests, track SLAs, and close deals faster.

![HTML5](https://img.shields.io/badge/HTML5-Single--File_SPA-E34F26)
![CSS3](https://img.shields.io/badge/CSS3-Custom_Design_System-1572B6)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla_ES6-F7DF1E)
![Chart.js](https://img.shields.io/badge/Chart.js-4.4.0-FF6384)
![License](https://img.shields.io/badge/License-MIT-purple)
![Version](https://img.shields.io/badge/Version-v3-brightgreen)

---

## What Is ExpertFlow?

ExpertFlow is a **zero-dependency, single-file expert network CRM**. It gives research and investment teams a unified workspace to receive consultation requests from clients (hedge funds, PE firms, VCs), intelligently match those requests to the right domain experts, track SLAs, manage the call pipeline, and analyze performance — all from one dark-themed, high-density interface.

No backend. No build step. No dependencies to install. Open `index.html` and you're live.

The AI matching engine scores each expert against each request and surfaces the highest-fit candidates first. A live dialer, AI call summarizer, and Kanban pipeline keep deal flow moving. Role-based access (Admin / Manager / Associate) controls what each team member sees and can do.

---

## File Structure

```
ExpertFlow/
├── index.html          # Complete SPA — all CSS, JS, and UI in one file
└── assets/             # Optional: logos, screenshots, favicons
```

ExpertFlow is intentionally a single-file deployment. The entire application — styles, state, rendering logic, mock data, and UI components — lives inside `index.html`. This makes it trivially deployable to any static host: GitHub Pages, Vercel, Netlify, or a plain S3 bucket.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styles | CSS3 — custom design system (CSS variables, no framework) |
| Logic | Vanilla JavaScript ES6 (no React, no Vue, no bundler) |
| Charts | Chart.js 4.4.0 (CDN) |
| Fonts | Inter (Google Fonts) |
| Deployment | Any static host — GitHub Pages, Vercel, Netlify, S3 |

---

## Feature Overview

### Dashboard
- KPI grid: active requests, experts matched, calls completed, revenue generated
- AI Suggestions panel — proactive recommendations powered by request context
- Action Queue sorted by urgency (urgent / today / soon / low) with SLA countdown
- Activity Feed: real-time log of team actions and expert responses

### Request Inbox
- Full request table with client, topic, sector, priority, SLA bar, status, and assignee
- Filter by status: All / Pending / Active / Completed
- Create new requests via modal form
- Color-coded urgency left-borders (red → amber → blue → grey)
- SLA progress bar shows percentage consumed at a glance

### Expert Matching
- Expert roster with AI match score (0–100) visualized as dot matrix
- Filter by availability: All / Available / Busy
- Click any expert to open a side drawer with full profile:
  - Match score breakdown
  - Sectors covered
  - Star rating
  - Call stats and last contact date
  - Duplicate contact warning (flags if contacted within recent window)
- One-click "Schedule Call" from the drawer

### Pipeline (Kanban)
- Kanban board: New → Matched → Scheduled → Completed
- Drag-free card view with client, topic, sector tag, and urgency badge
- Count badges per column update dynamically

### Calls
- Built-in dialer with keypad and pulsing active-call state
- AI Call Summary (GPT-4o) — bullet-point summary of last call: key findings, action items, follow-up recommendations
- Call Log table: expert, client, duration, date, status
- No-show tracking

### Clients
- Client roster with tier (Platinum / Gold / Silver), total requests, calls, revenue, CSM owner, and status
- Revenue visible per account for quick prioritization

### Analytics
- Revenue by Month (bar chart)
- Requests by Sector (doughnut chart)
- Expert Utilization (line chart)
- SLA Compliance Rate (bar chart)
- Team Performance table: requests handled, calls made, revenue generated, avg SLA, rating

### Team Management *(Admin only)*
- Team member cards with avatar, role, email, and stats (requests, calls, revenue)
- Add new member via modal
- Remove member with confirmation
- Role-based visibility: Admin sees full team panel; non-admins do not

### Settings
- **Profile** — name, email, job title, role switcher (Admin / Manager / Associate)
- **Workspace** — workspace name, default SLA hours, timezone, currency
- **Notifications** — granular toggles: new request, SLA warning at 80%, SLA breach, expert response, weekly digest, AI suggestions
- **Billing** — plan selector (Starter $99 / Professional $299 / Enterprise $999), payment method management
- **Integrations** — connect/disconnect: Salesforce CRM, Slack, Google Calendar, Zoom, HubSpot, Stripe

---

## Expert Sectors

| Sector | Example Experts |
|---|---|
| Technology | Semiconductor design leads, GenAI strategists, VP Supply Chain |
| Energy | EU climate policy directors, energy policy researchers |
| Finance | Fintech regulatory counsel, options market specialists |
| Healthcare | FDA policy consultants, digital health advisors |
| Logistics | LatAm logistics experts, Southeast Asia corridor specialists |
| Agriculture | AgriTech founders, precision agriculture technologists |
| Defense | Defense procurement advisors, government relations specialists |

---

## Client Tiers

| Tier | Revenue Range | Perks |
|---|---|---|
| Platinum | $400k+ | Dedicated CSM, priority matching, SLA guarantees |
| Gold | $250k–$400k | Named CSM, advanced analytics |
| Silver | <$250k | Shared CSM, standard SLA |

Representative clients: Bridgewater Associates, KKR, Blackrock, Vanguard, TPG Capital, Sequoia Capital, Andreessen Horowitz, Citadel, Tiger Global, Coatue Management.

---

## SLA & Urgency System

| Level | Colour | Trigger |
|---|---|---|
| Urgent | Red | SLA ≥ 90% consumed or deadline < 2h |
| Today | Amber | Deadline within same business day |
| Soon | Blue | Deadline within 24–36h |
| Low | Grey | Comfortable runway remaining |

SLA bars render inline in the request table so associates can triage without opening each record.

---

## AI Features

### Match Scoring
Every expert is scored 0–100 against the request topic and sector. Scores are displayed as a dot matrix (filled dots = score, up to 10 dots). The algorithm weighs sector overlap, past call volume, recency of contact, and star rating.

### AI Call Summary (GPT-4o)
After each call, an AI-generated bullet-point summary covers:
- Expert knowledge confirmation
- Client's key questions and answers provided
- Recommended follow-up actions
- Suggested next stakeholders to loop in

### AI Suggestions Panel
The dashboard surfaces 3–5 proactive suggestions each session, such as flagging requests with no matched experts, recommending re-engagement for dormant clients, or highlighting SLA risk before it becomes a breach.

---

## Integrations

| Integration | Purpose | Status |
|---|---|---|
| Salesforce CRM | Sync contacts and opportunities | Connected |
| Slack | Get notifications in workspace | Connected |
| Zoom | One-click video calls with experts | Connected |
| Google Calendar | Sync call schedules and reminders | Available |
| HubSpot | Export pipeline data to deals | Available |
| Stripe | Automated invoicing and payments | Available |

---

## Role-Based Access

| Feature | Admin | Manager | Associate |
|---|---|---|---|
| View all requests | ✓ | ✓ | ✓ (own only) |
| Create requests | ✓ | ✓ | ✓ |
| Expert Matching | ✓ | ✓ | ✓ |
| Client revenue data | ✓ | ✓ | — |
| Team management | ✓ | — | — |
| Add / remove members | ✓ | — | — |
| Workspace settings | ✓ | ✓ | — |
| Billing | ✓ | — | — |

---

## Getting Started

### Option 1 — Open Directly

```bash
# Clone the repo
git clone https://github.com/Noctilucenty/ExpertFlow.git
cd ExpertFlow

# Open in browser (no server needed)
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

### Option 2 — Serve Locally

```bash
# Python (built-in)
python -m http.server 8080

# Node.js (npx, no install required)
npx serve .

# Then open http://localhost:8080
```

### Option 3 — Deploy to GitHub Pages

1. Push the repo to GitHub
2. Go to **Settings → Pages → Source → main / root**
3. Your app is live at `https://Noctilucenty.github.io/ExpertFlow`

### Option 4 — Deploy to Vercel

```bash
npx vercel --prod
```

No `vercel.json` config needed — Vercel detects the static HTML automatically.

---

## Core Data Models (Client-Side State)

| Model | Key Fields |
|---|---|
| `User` | `name`, `initials`, `email`, `title`, `color`, `role` |
| `TeamMember` | `id`, `name`, `role`, `email`, `status`, `requests`, `calls`, `revenue` |
| `Request` | `id`, `client`, `topic`, `sector`, `priority`, `status`, `assignee`, `deadline`, `sla`, `experts` |
| `Expert` | `id`, `name`, `title`, `sectors[]`, `status`, `calls`, `rating`, `lastContact`, `match` |
| `Client` | `id`, `name`, `tier`, `requests`, `calls`, `revenue`, `csm`, `status` |
| `CallLog` | `expert`, `client`, `duration`, `date`, `status` |
| `Integration` | `name`, `icon`, `connected`, `sub` |

All state lives in a single `STATE` object — no external store, no local storage (by default). Extending persistence is as simple as serializing `STATE` to `localStorage` on mutation.

---

## UI System

ExpertFlow uses a bespoke CSS design system defined entirely in CSS custom properties:

```css
--bg: #09090b          /* Page background — near-black */
--surface: #111114     /* Card / sidebar surface */
--elevated: #17171b    /* Modals, drawers, inputs */
--accent: #6366f1      /* Indigo — primary CTA, active nav */
--green: #22c55e       /* Success, available status */
--amber: #f59e0b       /* Warning, SLA at risk */
--red: #ef4444         /* Urgent, SLA breach, danger */
--blue: #3b82f6        /* Soon / informational */
--purple: #a78bfa      /* Secondary accent */
```

Components: KPI cards, action queue, Kanban cards, data tables, side drawer, modal, toast notifications, toggle switches, dialer keypad, analytics charts (Chart.js), team cards, settings panels, plan selector cards.

---

## Changelog

### v3 — AI Matching + Full Analytics
- AI match scoring engine (0–100) with dot-matrix visualization
- GPT-4o call summary panel
- Full analytics suite: revenue, sectors, utilization, SLA compliance charts
- Team performance table
- Integrations panel (Salesforce, Slack, Zoom, Google Calendar, HubSpot, Stripe)
- Billing plan selector with current plan highlighting
- Role-based access control (Admin / Manager / Associate)
- Duplicate contact warning in expert drawer

### v2 — Pipeline + Calls
- Kanban pipeline board (New → Matched → Scheduled → Completed)
- Built-in dialer with active-call pulse animation
- Call log with no-show tracking
- Client tier system (Platinum / Gold / Silver)
- SLA progress bars in request table

### v1 — Foundation
- Request inbox with urgency queue
- Expert roster with availability status
- Dashboard KPI grid
- Activity feed
- Dark design system

---

## Roadmap

- [ ] `localStorage` persistence — survive page refresh without a backend
- [ ] Real AI matching via OpenAI Embeddings (cosine similarity on expert bios vs request topics)
- [ ] Actual GPT-4o call summary integration via Whisper → GPT pipeline
- [ ] CSV export for requests and call logs
- [ ] Drag-and-drop Kanban cards
- [ ] Email notifications via EmailJS (no backend required)
- [ ] Multi-workspace support with URL-based routing
- [ ] Mobile-responsive layout

---

## Contributing

Pull requests are welcome. Since ExpertFlow is a single-file app, keep all changes inside `index.html` and maintain the existing CSS variable system for consistency. For major feature additions, open an issue first.

---

## License

MIT © ExpertFlow 2026
