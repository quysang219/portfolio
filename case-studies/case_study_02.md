# Case Study 02 — SEC MGMT Self-Service Security Platform

**Working brief.** Drives the build of `case-studies/case_study_02.html`.

**Linked from:** `portfolio_v11.html` → §02 Problem 02 CTA + §04 Case 02 footer.
**Image asset:** `img/SEC_MGMT_redacted.png` (same as the index card centerpiece — reused larger at the bottom of this page).

---

## 1. Positioning

- **Card label on the index:** *Case 02 · Operator surface — SEC MGMT Self-Service Security Platform.*
- **Problem it answers:** Problem 02 — *"Owners can read, but can't act."* The interaction surface that pairs with Case 01's executive surface.
- **Tags:** JavaScript · PostgreSQL · Workflow · RBAC.
- **Bridge line (sets up the hero):** *Case 01 fixed the read. This case fixes the write.*

## 2. Hard constraints (carried over)

- **NO mention of Tooljet anywhere.** Refer to the operator surface only as *internal web app / in-house platform / JavaScript*.
- External role framing only.
- Public site — no bank-internal table or system names.
- Redacted image only.
- Same design language as `portfolio_v11.html` and `case-studies/centralized-reporting.html`.

## 3. Narrative arc

### Panel 01 · How it *started* — the Interaction gap (warn-red)

**Hook.** Even after Case 01 landed, the workflows were still overloading — just at a different stage. Coverage and findings showed up cleanly; the *interaction around them* did not.

**Vignettes.**
- **Vulnerabilities** — the report shows an unremediated, overdue vulnerability. Hardly any context. Did we ever attempt to fix it? Are we waiting for a vendor release or a test date? Are we going to file an exception or an extension?
- **Firewall Review** — after findings and recommendations are sent to system owners, they need to log justifications. *Why is this unsafe port open?* *What does this rule actually serve?*
- **User Account Review** — sometimes an account needs to be kept because it is actually a **service account**, not a person. There was no in-platform way to mark that.

**The cost.** Security experts handled the back-and-forth on their own agility. Each workflow had a different format of collaboration — email, Teams, spreadsheets. The dashboard told you *where* the gap was, not *what was happening with it*.

**Pull-quote:**
> A finding without context is just a number.

### Panel 02 · How it *evolved* — the Power BI ceiling (indigo)

**Lede.** We tried writeback inside Power BI first. Power BI — especially Power BI Report Server — is a packaged Microsoft product. Self-service cell-level writeback isn't part of its surface.

**The custom-visual route.** Third-party writeback visuals exist on the market. They didn't pencil out at our population.

**The economics line (the punchline).** We serve **~200 users per quarter** — system owners and administrators. That's a small population by license-count, but a large one by role. Per-seat custom-visual pricing models are built for very different distributions; the math didn't land.

**Conclusion.** The writeback layer had to step outside the BI tool. We built an internal web app for it.

**Highlight strip:**
`Power BI Report Server (read)  ·  internal web app (write)`

**Pull-quote:**
> Small in count, large in role.

### Panel 03 · How it *matured* — building in-house (bronze)

**Lede.** We developed an in-house web application with simple writeback capabilities, sized for the actual population: a few hundred owners and admins who needed a structured way to talk back to the report.

**What it gave us.**
The same three things over and over, no matter which security program we onboarded next:
- **A place to write** — owners record comments, plans, queries, exceptions against the actual finding they're looking at.
- **A place to review** — security reviews and approves or responds, in-platform, with the finding still in context.
- **A place to automate** — routine clarifications and follow-ups don't need a human first-touch.

That three-step shape became the canonical workflow template — onboard a new program by mapping it to *write → review → automate*.

**Pull-quote:**
> The same three motions, once each per finding — write, review, automate.

### Panel 04 · What it *is* now — three pillars (teal)

**Three pillars** (3-card grid):

- **Workflow engineering.** End-to-end onboarded: SO comments → SEC reviews → approve or respond. The dashboard's finding now has a thread on it.
- **Workflow automation.** SECAI sits behind the platform and auto-replies to system owners — clarifies routine queries, follows up on stalled threads, frees the security team for the cases that need judgment.
- **Finding depth.** Findings stopped appearing blank. Every one has a story behind it — *plans, exception requests, queries, notes* — captured next to the data, not in an inbox. The four real examples you'd see in production: *waiting for vendor release · test date pending · exception requested · service account, retain.*

**Closing pull-quote:**
> The platform doesn't replace judgment. It moves the judgment into the platform.

## 4. Centerpiece treatment

After Panel 04, drop into the same `Fig. NN` centerpiece block as Case 01:

- **Image:** `img/SEC_MGMT_redacted.png`
- **Label:** `Fig. 01 · The platform`
- **Caption:** `SEC MGMT Self-Service Security Platform · operator surface · redacted for public portfolio`

## 5. Footer

- **Card 1:** ← Back to portfolio (active link to `../index.html#cases`)
- **Card 2:** Case Study 01 — *Executive surface — centralized security reporting* (active link to `centralized-reporting.html`)
- Same colophon row.

## 6. Decisions made

| Decision | Choice |
|---|---|
| Filename | `case_study_02.html` (renamed from `audit-trail.html` for easy tracking) |
| In-house app naming | *Internal web app / in-house platform* — no Tooljet. |
| Pillar count | **Three**, per user's narrative. Audit trail not split out as a 4th. Easy swap if user prefers 4. |
| SECAI naming | Used explicitly. Already public-facing in `Firewall Journey.html`. |
| Power BI framing | Neutral — packaged product, not broken; writeback simply lives outside its surface. |

## 7. Open items / nice-to-have

- **Audit trail as a 4th pillar** — could be added cleanly (append-only writeback log, every comment/decision/automation step preserved). Would also better justify the page filename. Flagged in chat.
- **Concrete numbers for Panel 04** — `200 owners/quarter`, `N programs onboarded`, etc. Currently only the user-count is given.
