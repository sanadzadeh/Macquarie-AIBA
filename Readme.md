# Khaled Sanad — AI Strategy Portfolio

Synthetic demonstration of a COO **AI, Data and Analytics** strategy working book.

Live path: [sanadzadeh.github.io/ManagerAI](https://sanadzadeh.github.io/ManagerAI)

This is **not** a Commonwealth Bank system of record, a production dashboard, or a claim of employment at CBA. Every number, owner, initiative and measure is synthetic. The artefact exists to show a method: problem → options → control gates → adoption measures → park-or-progress.

---

## What this is

A single-page HTML application that behaves like an internal strategy office product for a COO mandate covering operations, customer operations, fraud and scams, and enablement.

It is designed to be opened in an interview and walked in three minutes:

1. Land on **Mandate & thesis**.
2. Open one initiative (S-04 or S-09).
3. Jump to that initiative’s value measure and the EGM pack extract.

If a screen does not help a senior leader decide, it should not be there.

---

## What this is not

- Not a delivery tracker, PMO wall or Copilot / prompt-pack catalogue.
- Not a forecast model. Scenario tiles are written rules, labelled “rule, not a model.”
- Not a dollar-savings case. Hours and adoption rates are operating hypotheses.
- Not branded as CBA. Navy / paper / teal is an institutional palette, not bank identity.

---

## How to open

Open `index.html` in a current browser, or serve the folder:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

No build step, no backend, no analytics. Fonts load from Google Fonts; the page remains readable if they fail.

---

## How to read it

Header strip on first visit:

> Start on Mandate, open one initiative, then jump to its value measure. Every figure is synthetic.

Two modes sit in the header:

| Mode | Job |
|---|---|
| **Strategy & portfolio** | Problems, pipeline, dossiers, sequencing, controls |
| **Value, adoption & rhythm** | Reviewed use, unit readiness, work-mix, lineage, operating cadence |

Strategy-mode filters: unit, stage.  
Value-mode filters: horizon, unit, book.

Horizon and book are context chips for a conversation about cuts. Where a figure can move with the selected unit, it does (value command and readiness). Treat unused cuts as interview prompts, not as a live data warehouse.

Theme persists in `localStorage` (`portfolioTheme`). The how-to strip dismisses into `portfolioGuideDismissed`.

### Deep links

The URL updates as you move. Useful for sending a panel member to one exhibit:

```
?mode=strategy&view=dossier&id=S-04
?mode=value&view=lineage&m=review-cycle
?mode=value&view=rhythm
```

Supported query keys: `mode` (`strategy` | `value`), `view`, `id` (initiative), `m` (measure).

Print hides chrome and keeps a disclaimer line: name, synthetic status, date.

---

## Information architecture

### Strategy & portfolio

**01 Mandate & thesis**  
Orientation. Three KPIs, a friction × control-intensity map, where value is supposed to appear, and a decision strip. Default recommendation: park live-customer dialogue; only progress work that has a control path.

**02 Opportunity pipeline**  
Stage funnel, scored “recommended focus,” and a problem-led register. Product names do not lead. Click a row to open the dossier.

**03 Initiative dossier**  
ID tabs across the filtered set. Problem, must-not, three options with a data-driven recommendation, gates, variance, hours hypothesis, owners, risks and dependencies. Cross-link to the related value measure.

Recommended option is not the same on every card:

- Assist with a human gate where the control path is credible.
- Do nothing / park where conduct or privacy is unresolved (S-09, S-10).

**04 Investment & sequencing**  
Now / next two quarters / realised / parked. Four scenario rules. Outputs include slip beyond eight weeks. Control breaches stay at zero because the rule is *pause the pilot*, not *bypass the reviewer*.

**05 Assurance & controls**  
Register health (completeness, accuracy, timeliness as percentages), issue ageing, and measure lineage. A demo without a named user group is not adoption.

### Value, adoption & rhythm

**01 Value command**  
Reviewed users, adoption versus intended cohort, reviewed completion. Combination chart with a shaded “reviewers pulled to BAU” band. Decision: treat a spike as initiative evidence, not platform evidence.

**02 Unit readiness**  
Four units side by side: Operations, Fraud & Scams, Enterprise enablement, Customer operations / Contact. Readiness bars: problem clarity, data/access, named reviewers, change capacity. Lower adoption in a high-control domain is treated as a structural fact, not a performance failure.

**03 Work-mix & effect**  
Illustrative before / after effort mix plus four confounders (release week, peak BAU, control tightening, demand spike). No causal claim.

**04 Measure lineage**  
Definition → transform → validation → owner → source, tied back to the originating initiative.

**05 Operating rhythm**  
Illustrative monthly cadence (pipeline freeze → adoption huddle → value pack → EGM lock) and a three-number pack extract with one ask.

---

## Synthetic register

Ten initiatives. Two are owned by K. Sanad (S-01, S-04). Two are deliberately not in delivery.

| ID | Problem (short) | Unit | Stage | Control |
|---|---|---|---|---|
| S-01 | Complaint handling time and missed accessibility flags | Customer operations / Contact | Deliver | Conduct |
| S-02 | Onboarding evidence triage / rework | Operations | Case | Ops |
| S-03 | Teams rebuild AI briefs and control questions | Operations | Adopt | Ops |
| S-04 | Manual evidence assembly before a human decision | Operations | Case | Model risk |
| S-05 | Policy changes reach teams too slowly | Enterprise enablement | Frame | Ops |
| S-06 | Scam investigations repeat evidence assembly | Fraud & Scams | Frame | Conduct |
| S-07 | Incident write-ups slow and inconsistent | Operations | Deliver | Ops |
| S-08 | Policy search delays routine frontline answers | Customer operations / Contact | Deliver | Ops |
| S-09 | Live-customer dialogue, conduct boundaries unresolved | Customer operations / Contact | Parked | Conduct |
| S-10 | Sensitive document access, privacy path unresolved | Enterprise enablement | Scan | Privacy |

Hard rules encoded in the copy:

- An open session without a completed review action is not use.
- A demo is not production.
- Auto-accept is a control break.
- Paused cases are excluded from cycle-time medians.
- Assistants do not dispose, score, close, approve onboarding, waive evidence, replace policy text, or generate unsupervised live-customer advice.

---

## Method the site is arguing for

1. Name the user, the decision and the pain.  
2. Write the must-not before the build.  
3. Put three options on the page, including do nothing.  
4. Require a named reviewer and a bounded cohort before anything leaves Frame.  
5. Measure adopted, reviewed use — not opens and demos.  
6. Park when the control path or operating owner is not credible.  
7. Show confounders next to any “after” number.  
8. Put one ask on the executive extract.

That method is the portfolio. The charts are exhibits.

---

## Technical notes

- One static file: HTML, CSS and vanilla JavaScript.
- Data lives in a single `DATA` object (`initiatives`, `units`, `measures`, `scenarios`). Views are filters over that object.
- Charts are inline SVG generated from the same data. No Chart.js.
- Type: IBM Plex Sans / Serif / Mono.
- Tokens cover light and dark. Motion is limited; `prefers-reduced-motion` disables the rest.
- Sticky header and rail on wide screens; rail becomes a horizontal chip row below ~1120px.
- Keyboard: filters, tabs and dossier IDs are buttons or native selects. Focus styles are visible.

Suggested local checks before publishing:

- 1280×800 interview laptop  
- Dark theme  
- Print preview of Mandate and one dossier  
- `?id=S-09` and `?m=review-cycle`  
- Dismiss guide, confirm rail offset still looks intended  

---

## Suggested interview path

Do not tour every view.

1. Mandate decision strip — park S-09, only advance work with a control path.  
2. Dossier S-04 — evidence assembly, model-risk gate, assistant must not close the decision.  
3. Lineage for `review-cycle` — how the measure is constructed.  
4. Rhythm pack — 68% reviewed adoption, three items at a gate, two held, one ask on reviewer capacity.

If asked about financial crime depth, open S-06 (scam evidence assembly) and stay on the must-not, not the chart.

---

## Disclaimer

All names, volumes, hours, adoption rates, control scores and dates are invented for demonstration. They are not drawn from NAB or CBA systems. Do not screenshot this page as evidence of live bank performance.

© Khaled Sanad. Personal portfolio artefact.
