# Case Study 01 — SEC MGMT Measurement Report

**Working brief.** This document drives the build of `case-studies/case_study_01.html`. It's planning prose, not the page itself.

**Linked from:** `portfolio_v11.html` → §02 Problem 01 CTA + §04 Case 01 footer.
**Image asset:** `img/SEC_MGMT_Measurement_Report_redacted.png` (same as the index card centerpiece — reused larger at the bottom of this page).

---

## 1. Positioning

- **Card label on the index:** *Case 01 · Executive surface — SEC MGMT Measurement Report (Centralized Security Reporting).*
- **Problem it answers:** Problem 01 — *"Coverage tracked, posture invisible."* Coverage existed inside individual source systems; history, trend, anomaly and recognition did not.
- **Tags:** Power BI · DAX · Snapshot model · Editorial design.
- **Voice:** engineer-analyst. Italic emphasis used sparingly on one or two key words per heading. No self-deprecation, no future-tense aspiration — the report exists.

## 2. Hard constraints (carried from `portfolio_description.md`)

- **NO mention of Tooljet anywhere.** Operator surface is Case 02; this page does not need to reference it by product name.
- External role framing only: Security Engineer / Security Automation Engineer / Security Data Analyst. Never "GRC Engineering."
- Public site — no bank-internal table or system names.
- Redacted image only (`_redacted` suffix).
- Design language preserved from `portfolio_v11.html`: Fraunces / Inter / JetBrains Mono · slate-indigo `#2f4b7c` · teal `#1d6a5b` · bronze `#8a6a2e` · warn-red `#c63b54` · paper `#f3f4f7` · `.narr` panels with corner ticks + faint `.bg-deco` SVG decoration.

## 3. Narrative arc

Single-column, four numbered panels + a centerpiece coda. Each panel is its own `.narr` block with a section digit, mono label, fading rule line, and one accent color.

### Panel 01 · How it *started* — the Excel loop

**Accent:** warn-red (mirrors `.s-problem`).

**Lede.**
When I joined IT Security, vulnerability remediation ran on email and spreadsheets. We scanned a known inventory, exported results to Excel, split the file per team, password-protected each one per the bank's regulations, and sent them out. Teams fixed what they could, told us by hand, we rescanned, diffed, and started the loop again. Per asset. Per quarter. Per team.

**The insight.**
The painful part of the loop wasn't the work — it was that the loop didn't know what it was. **Circular 09** requires a quarterly scan-and-fix cycle, and a vulnerability is considered fixed if it does not reappear in a rescan compared to the start-of-quarter snapshot. Once you name it that way, the workflow isn't a workflow — it's a **snapshot diff**. It belongs in a data model, not a mailbox.

**The first build.**
I worked with my data engineer to land the tables. Power BI Report Server became the surface teams self-served from. Teams could now see their own latest vulnerabilities and status without waiting for a file.

**Pull-quote (highlight):**
> The painful loop wasn't a workflow problem — it was a measurement problem in disguise.

### Panel 02 · How it *evolved* — from one program to a central surface

**Accent:** indigo (mirrors `.s-intro` / `.s-background`).

**Lede.**
With the first report live, the data engineer kept integrating. Tenable agents joined first; then SIEM, antivirus, EDR, and an asset inventory that grew to roughly **30,000 production assets** — on-prem, cloud (S3 buckets, RDS, EC2), network devices, physical infrastructure, staff endpoints, ATM/CDM units, container images.

**My role widened.**
- **Data quality** — the unglamorous coordination work that decides whether a number is trustworthy.
- **Centralized visualization** — a single big report, the Security Management Dashboard, where any team could find their assets and their findings.
- **Workflow onboarding** — standardizing program after program into the same surface: Card Data Scan, Security Agent Coverage, Configuration Hardening, Privileged User Account Review, Firewall Review.

**Honest framing.**
I don't do it all. I sit at the intersection of data quality, visualization, and guiding system owners through their own program. The dashboard is the meeting point.

**Mono pill row (highlight strip):**
`30,000 assets  ·  5 source systems  ·  6 onboarded programs`

### Panel 03 · How it *matured* — the 90%+ problems

**Accent:** bronze (capabilities color from v8 palette).

**Lede.**
As the programs rolled out, compliance lifted from the low-60s toward 90%+. The headline number was no longer the story. As we approached 100%, a second class of issue surfaced — one that low-coverage reporting could never have seen.

**The new class of finding.**
- **Flapping.** Security agents switching between online and offline continuously, looking healthy at any single point and unhealthy across time.
- **Ownership churn.** Vulnerabilities that bounced between assignees, never long enough with one team to be fixed.

These aren't visible on a point-in-time bar chart. They're only visible when the report holds **memory**.

**The shift.**
The report stops being a coverage tracker and becomes a **measurement instrument**: progress over time, stability over time, anomaly against baseline. The snapshot model that began as a regulatory accounting trick becomes the load-bearing piece of the architecture.

**Reporting itself industrializes.**
The most laborious legs — frontend design, data transforms — move into a pipeline I run with Claude Code. I keep judgment and review.

**Pull-quote (highlight):**
> At low coverage the work is plumbing. At high coverage the work is measurement.

### Panel 04 · What it *is* now — SEC MGMT Measurement Report

**Accent:** teal (mirrors `.s-cases`).

**Lede.**
The SEC MGMT Measurement Report is the executive surface for everything above.

**Four lenses** (callouts that match the index card):

- **Progress Tracking.** Every program has a story over time, not just a number today. Teams see their own line move.
- **Anomaly Detection.** Flapping agents, churning ownership, and other stability signals get their own views — the kind of finding you only see when you hold memory.
- **Achievement Recognition.** When a team closes the gap, the report shows it. The number on the wall becomes a fact about *who*, not just *what*.
- **Executive Reporting.** Leadership reads posture, not just coverage. Security work that used to be invisible becomes legible.

**Pull-quote (closing line):**
> Coverage tells you where you are. Measurement tells you whether you're moving — and who's moving.

## 4. Centerpiece treatment

After Panel 04, drop into a single full-width exhibit block — same `.exhibit` layout family as the index, but here it's the climax of the page rather than a card preview.

- **Image:** `img/SEC_MGMT_Measurement_Report_redacted.png`
- **Layout:** centered, no left/right callouts (those four lenses already lived in Panel 04). The image carries itself.
- **Caption beneath:** small mono line, e.g. `Fig. 01 — SEC MGMT Measurement Report · executive surface · redacted for public portfolio`.

## 5. Footer

- **Back link:** `← Back to portfolio` (returns to `index.html` / `portfolio_v11.html` anchor `#cases`).
- **Forward link:** `Case 02 · Operator surface →` (placeholder until `audit-trail.html` exists).
- Same colophon line as the index: *Lê Quý Sang · 2026 · System Thinking. Tangible Outcomes.*

## 6. Design notes for the build

- **Panel template:** `.narr` block + `.num` digit (40px Fraunces, accent color) + mono uppercase label + fading rule line. Same `::before` / `::after` corner ticks. Same `.bg-deco` absolute SVG (different symbol per panel — magnifying glass, layered cards, line chart, gauge, in that order).
- **Type scale:** H2 panel titles 28–32px Fraunces; lede 17px Inter; body 16px Inter; pull-quote 22px Fraunces italic with a left rule in the accent color; mono pill row 12px JetBrains Mono `letter-spacing: 0.08em`.
- **Width:** same single-column max-width as `portfolio_v11.html`. No multi-column body inside panels.
- **Highlight discipline:** at most one italic word per heading, at most one pull-quote per panel, no exclamation marks anywhere.

## 7. Open items / decisions made

| Decision | Choice |
|---|---|
| Regulatory mention | **Circular 09** named explicitly in Panel 01. |
| AI naming in Panel 03 | **Claude Code** named explicitly (carry-forward of user's own phrasing — confirm once when reviewing). |
| Centerpiece images | Single existing redacted screenshot, no additional gallery. |
| Firewall Journey HTML reference | Not embedded. Mentioned only as color in this brief; the page does not link to it. |
| Page format | Boxes + text driven by this brief; HTML in the next pass. |

## 8. Next step

When you give the go-ahead, build `case-studies/case_study_01.html` from this brief using the same head/css block as `portfolio_v11.html` (so accent colors, fonts, panels, corner ticks and decoration come through unchanged).
