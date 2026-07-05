# SKILL — Deal Triage (Live Instructions)

> **This is the live skill file for the Redstick deal-triage process.** Olli reads it
> at the start of every triage. To change the process, edit this file, bump the
> changelog, then mirror the summary to the Notion "SKILL — Deal Triage" page.

**Changelog**
- **2026-04-20** — Converted Fund II → Fund I. Check sizes set to $100K / $250K.
  No target ownership (check-size-driven only). EV reported as MOIC for
  cross-deal comparability. Fund I size confirmed $5M; fund-returner thresholds
  calibrated. IRR removed — Fund I evaluates on MOIC only.

---

## Pipeline: Read all docs → Triage → Market stress → PDF → Notion log → Cam message

Every triage produces four outputs, in this order:

1. **`[CompanyName]-Triage.pdf`** — saved to `/mnt/user-data/outputs/`
2. **Notion entry** — logged to 🔍 Deal Pipeline — Fund I (data source ID `77829e04-0a0c-4ee6-94d5-1807b9ea0241`)
3. **Draft message to Cam** — copy/send ready, includes a doc-gaps section
4. **Olli reminder** — upload PDF to Drive → paste link into the Notion `Triage Doc` field

---

## ⚠️ MANDATORY — read every uploaded file before starting

Before any analysis, read **all** files provided. Non-negotiable — missing a file
changes the scores and the recommendation.

- **PDFs/images already in context:** read directly.
- **Uploaded files not in context:** check `/mnt/user-data/uploads/`, extract every
  file with `pdftotext`, `pandoc`, or `cat`.
- **Google Drive link:** fetch by document ID from the URL.
- **Cannot access a file:** tell Olli, ask to re-upload / fix sharing. Do not proceed.

Log every file read at the top of the triage under **Documents Reviewed**.

---

## Redstick investment framework

**Thesis:** AI and robotics that make food systems more productive. Pre-seed to
Series A. North America.

**Four technology vectors:** Labour Productivity (Robotics) · Optimization
(CV/Sensing) · Decision Automation (AI/Ops) · Input Efficiency (Bio/Materials).

### Fund I parameters — HARD-CODED, never use the founder's ask

- **Check size: $100K or $250K only.** Always model **both** side by side. Never use
  the founder's round size. **Never $500K or $1M** — that is future-fund territory.
- **No target ownership.** Fund I is check-size-driven. Never recommend against a deal
  on ownership grounds. Entry ownership is informational context, never a gate.
- **Report EV as MOIC** (e.g. "2.93x @ $8M cap"). MOIC is check-size-agnostic.
- **Fund I size: $5M.** Fund-returner bar: a single deal must return $5M. TVPI drag
  if a deal fails: 2% per $100K check, 5% per $250K check.

---

## Step 0 — Identify diligence stage

| Stage | Documents present |
|---|---|
| **Deck** | Pitch deck or one-pager only |
| **Light Data Room** | Deck + cap table + deal terms + founder profiles + market sizing (each a standalone doc) |
| **References Started** | Any of the above + 1–2 back-channel reference checks |
| **3/4 Data Room** | Light Data Room + IP/tech docs + customer evidence + competitor analysis |
| **Full DD** | Complete data room + 3–5 reference checks + technical DD |

Information inside deck slides does **not** upgrade a stage — each item must be a
standalone substantive document. Reference checks can happen at any stage; count them
separately from stage.

---

## Critical red flags — any one = immediate PASS

- No founder/team, or zero domain experience in food/ag/robotics
- Cannot articulate the problem from the customer's perspective
- Valuation > $25M at seed with no revenue or deployed product
- Cap table > 30% to non-operating parties
- Me-too product, well-funded competitors, no differentiation
- Requires a follow-on commitment (closing conditioned on a future-round commitment, or mandatory pro-rata exceeding Fund I reserves)
- "Platform for everything" — no focus

**Never valid PASS reasons for Fund I:** "ownership too low," "round too small,"
"check size doesn't fit" (if the founder's minimum check is ≤ $100K, we can participate).

## Warning flags — 3 or more = likely PASS

No revenue AND no LOIs/pilots AND no demo · top-down-only TAM · missing technical
co-founder for deep tech · hockey-stick projections with no inflection driver · "no
competitors" claim · unaddressed regulatory risk · hardware with no prototype/mfg
plan · unclear business model after full read · deck > 25 or < 8 slides · raise
mismatched to milestones · **platform dependency** (100% reliant on one third-party
API where a pricing/policy change alters unit economics overnight — counts once; do
not double-count in the stress test).

---

## Step 1 — Read all files
List every file under **Documents Reviewed**. Note any that could not be read.

## Step 2 — Extract company data
Write `Not disclosed` if missing. Mark inferences `[Assumed]`, conversation-sourced
data `[to confirm on call]`.

**⚠️ Data provenance rule:** every financial figure cites its source — document +
page/section. Example: "$1.8M contracted ARR — Deck, slide 9."

Required snapshot fields: Company · Short description · Founder(s) + background ·
Founder commitment (self-funded amount, full-time status, ownership split) · Traction
signal (best single, cited) · Technology vector · Business model · Location + currency
(USD/CAD, label all figures) · Funding round (amount, instrument, cap, discount, MFN,
pro-rata, info rights, board observer) · Round timing (days to close, lead status,
committed co-investors) · Cap table (founder % / non-operating %) · Diligence stage ·
References done · Source · Documents reviewed · Top 3 conviction signals from
supplementary docs · Platform dependency · Strategic LP fit · Portfolio concentration ·
Follow-on reserve assumed.

---

## Step 3 — Write the triage

Use only facts from the documents. The output has six sections:

### Section 1 — On-thesis fit
Yes / No / Partial + vector reference · thesis tag · critical red flags triggered ·
warning flags + count.

### Section 2 — Deal structure

| Field | Value |
|---|---|
| Instrument | SAFE / Convertible Note / Priced Round |
| Valuation Cap | $__M [USD/CAD] |
| Discount | % |
| MFN Clause | Yes / No |
| Pro-rata Rights | Yes / No — through which round |
| Information Rights | Yes / No |
| Board Observer | Yes / No |
| Prior SAFEs / Notes Outstanding | $__M total [USD/CAD] |
| Deal Currency | USD / CAD |

**Entry ownership (informational only — NOT a gate):**
- SAFE / note: `check_size ÷ cap`
- Priced round: `check_size ÷ post-money cap` (note pre-money option-pool refresh dilutes before close)
- Discounted SAFE: model at cap-only and discount price; use the more dilutive
- If prior SAFEs exist: mark all EV dilution figures `[provisional — cap table required]`
- **If Redstick's cap is TBD:** recommendation defaults to **WATCH**.

**Fund I entry-ownership reference (informational):**

| Cap | @ $100K | @ $250K |
|---|---|---|
| $4M | 2.50% | 6.25% |
| $6M | 1.67% | 4.17% |
| $8M | 1.25% | 3.13% |
| $10M | 1.00% | 2.50% |
| $15M | 0.67% | 1.67% |

### Section 3 — Framework scorecard
`(Founder×0.40) + (Market×0.25) + (Tech×0.15) + (UnitEcon×0.15) + (Terms×0.05)` = **X.X / 5.0**

Anchors: 0 = red flag/no info · 1–2 = weak · 3 = adequate · 4 = strong · 5 = exceptional.
Minimum evidence — Founder 4: domain experience + track record or references · Market 4:
third-party analyst data or bottoms-up model with named segments · Tech 4: demo/patent/
technical doc · Unit Econ 4: actual or piloted unit data · Terms 4: Redstick cap
confirmed, MFN or pro-rata secured.

**ADVANCE floor rule:** no lens below 2.0 for an ADVANCE. Sub-2.0 caps at WATCH.

### Section 4 — Expected-value analysis
- **Model $100K and $250K side by side.** Never any other check size.
- **Two cap scenarios:** (a) founder's terms (reference), (b) Redstick's proposed cap.
  If TBD → "Redstick cap TBD — defaults to WATCH," leave (b) blank.
- **Report EV as MOIC @ cap.**
- **Bear-case floor: ≥ 20% fail probability** regardless of traction.

| Traction | Fail prob |
|---|---|
| Pre-revenue, no pilots/product | 45–55% |
| Pre-revenue + LOIs/pilots | 35–45% |
| Revenue < $500K, product live | 25–35% |
| Revenue > $500K, multiple customers, commercial hardware | 20–30% |

Dilution: base = entry × 0.80 × 0.80 (64% retention, 36% dilution). Strong/
fund-returner = × 0.85 more (54.4% retention, 45.6% dilution). Exit valuations tie to
ARR × multiple; state which ARR (contracted vs recognized).

**Compute MOIC in Python before writing the PDF:**
```python
entry_own  = check_size / cap            # 250000 / 8000000 = 0.03125
diluted    = entry_own * 0.64            # base case
moic       = (diluted * exit_val) / check_size
ev_contrib = prob * moic
```

Present four EV tables (Fail / Acqui-hire / Base / Strong / Fund-returner) + a blended
EV row, plus a sensitivity table for WATCH/ADVANCE deals. Fund-returner = single deal
returns $5M (e.g. ~$221M exit at $6M cap + $250K; ~$551M at $6M cap + $100K).

**Hurdle check at Redstick's terms:** EV ≥ 2.0x? · Base MOIC ≥ 5x? · TVPI drag noted ·
fund-returner exit cited.

### Section 5 — Conviction gaps
3–5 questions that most increase conviction, focused on the highest-uncertainty EV
inputs. If prior SAFEs exist, cap table is mandatory.

### Section 6 — Recommendation
- **ADVANCE** — thesis fit, no red flags, no lens < 2.0, EV ≥ 2.0x, base MOIC ≥ 5x at Redstick's terms → schedule intro call
- **WATCH** — on-thesis but marginal EV / missing data / lens < 2.0 / cap TBD → state the exact flip condition
- **PASS** — off-thesis / red flag / hurdles fail → one sentence. Never cite "ownership too low" or "round too small."

Always note if the recommendation differs between founder's terms and Redstick's terms.

---

## Step 3B — Market stress test (web research required)

Run before producing the document. Five searches, always:
1. Deadline / regulatory enforcement — holding or slipping?
2. TAM — software-only third-party data; flag if founder's TAM bundles consulting/labor
3. Competitive landscape — ≥ 3 searches (funded competitors, incumbent challengers, each named competitor)
4. ICP / customer demand — independent evidence of active spend
5. Company / founder news — history, press, prior exits/failures

Output a table: Stress area · Founder's claim · What research found · Verdict
(✅ Holds / ⚠️ Risk / ❌ Contradicted). One-sentence stress verdict. Recalculate EV
if research materially changes it.

---

## Step 4 — Produce the PDF
Read `/mnt/skills/public/pdf/SKILL.md` first. Format: reportlab Platypus.
Filename `[CompanyName]-Triage.pdf` → `/mnt/user-data/outputs/`. Redstick green
`#1C3A2E` headers, alternating `#F2F8F5` rows, 9–10pt table fonts, header says **Fund I**.
Tables: `repeatRows=1`, `splitByRow=True`, explicit `colWidths`.

## Step 5 — Log to Notion (never skip, never duplicate)
Search first (company name + data source ID `77829e04-0a0c-4ee6-94d5-1807b9ea0241`).
Update if found, create only if not. Populate: Company · Decision (✅ Advance / 👀 Watch /
❌ Pass, at Redstick's terms) · Diligence Stage · Thesis Tag · Weighted Score · EV by
stage (MOIC) · EV Hurdles Pass? · Round · Check Size · Entry Ownership (informational) ·
Founder(s) · Location + currency · Traction Signal · Strategic LP Fit · Portfolio
Concentration · Follow-on Reserve · Round Timing · Key Pass Reason / Watch Condition ·
Source · Date Triaged. Leave `Triage Doc` blank (Olli fills after Drive upload).

## Step 6 — Draft message to Cam
5–7 sentences, direct, written as Olli:
```
[Company] — Triage Complete

Ran the full [Company] package through triage — [docs read]. Short answer:
[Pass / Advance / Watch] at [$100K or $250K at $_M cap].

[What the company does + strongest signal.]
[Decisive reason for the decision; note founder-cap vs Redstick-cap difference.]
[What's missing — no signed pilots, cap TBD, closes in X days, etc.]

Full triage doc is attached.
```

---

## Output checklist
- [ ] All uploaded files read before starting
- [ ] Every financial figure cites source doc + page
- [ ] Deal structure captured; all figures labeled USD/CAD
- [ ] Check sizes $100K and $250K only — never $500K/$1M
- [ ] EV reported as MOIC @ cap; entry ownership informational only
- [ ] Four EV tables + sensitivity (WATCH/ADVANCE); MOIC computed in Python, non-zero
- [ ] Bear case ≥ 20%; exits tied to ARR × multiple; fund-returner calibrated to $5M
- [ ] No ADVANCE if any lens < 2.0
- [ ] Recommendation at Redstick's terms; defaults to WATCH if cap TBD
- [ ] PDF saved, header says Fund I; Notion searched first (no dupes)
- [ ] Key Pass Reason does NOT cite "ownership too low" / "round too small"
- [ ] Olli reminded: upload PDF to Drive → paste link into Notion Triage Doc
