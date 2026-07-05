# 09.02 — Markups & Follow-on

The playbook for when a portfolio company raises its **next** round. This is where a
small fund either compounds its winners or quietly signals doubt into them. It is the
most consequential recurring decision in the fund after the initial invest.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Fund I is $5M, checks
> are $100K or $250K, and we evaluate on **MOIC**. A follow-on that would require a
> $500K or $1M check is **not a Fund I decision** — it is future-fund or SPV
> territory. Never let a founder's ask override that.

---

## The one-screen version

- **A markup is not a distribution.** A higher next-round cap raises our *unrealized*
  mark (RVPI/TVPI), not our cash. We report it conservatively and never confuse paper
  gains with returns. Marks matter for LP reporting, not for our bank balance.
- **Small funds carry signaling risk.** If we visibly decline to follow on, later
  investors read it as inside information. We manage that signal deliberately.
- **Reserves are finite and pre-decided.** Follow-on comes from the reserve pool sized
  in [`../04-portfolio-construction/`](../04-portfolio-construction/), not from wishful
  reallocation. When conviction exceeds reserves, the tool is an **SPV**, not a bigger
  fund check.
- **We only chase the winners.** Follow-on dollars concentrate on companies tracking
  toward the fund-returner path. We do not average down into strugglers to "protect"
  a position.

---

## Step 1 — Classify the round

| Signal | What it means | First move |
|---|---|---|
| **Up round** (higher cap/price) | Market agrees; mark rises | Confirm terms; run follow-on decision |
| **Flat round** | Traction stalled or market cooled | Diligence *why*; treat with caution |
| **Down round / recap** | Value impaired; likely restructuring | Route to [crisis playbook](./03-crisis-management.md) |
| **Insider bridge / extension** | Runway gap, no new lead | Diligence runway math before deciding |
| **Party round, no lead** | Weak conviction in market | Higher bar to follow; watch signaling |

Only an **up round with a credible lead** is a clean markup. Everything else is
diligence before it is celebration.

---

## Step 2 — The signaling problem (small-fund specific)

A $5M fund cannot maintain full pro-rata across 15–20 companies — the reserve math
forbids it. That is normal and known. But *how* we decline matters:

| Our action | How the market may read it | Mitigation |
|---|---|---|
| Follow on at/above pro-rata | Strong conviction | Say so — it is a positive signal, use it |
| Take partial pro-rata | Neutral / capital-constrained | Frame explicitly as fund-size math, not doubt |
| Pass entirely, quietly | "Insiders know something" | Get ahead of it — tell the founder *why* in writing |
| Pass and go silent to the founder | Worst case — reads as abandonment | Never do this; always give the real reason |

**The rule:** when we decline pro-rata for reserve reasons, we tell the founder
plainly and, if useful, give them a line they can share with the new lead ("Redstick
is a $5M fund at reserve capacity — not a signal on the company"). Honesty defuses the
signal; silence amplifies it.

---

## Step 3 — Follow-on decision framework

Three gates, in order. All three must pass to deploy fund reserves.

1. **Conviction gate** — Is this company on the fund-returner path? Re-read the [memo
   of record](./01-first-90-days.md). Has the thesis held or strengthened? A follow-on
   is a *new* investment decision at the *new* price, not loyalty to the old one.
2. **Reserve gate** — Is the capital available in the pre-allocated reserve pool
   ([`../04-portfolio-construction/`](../04-portfolio-construction/)) without starving
   other reserved positions? Follow-on checks are still $100K or $250K from the fund.
3. **Marginal-MOIC gate** — Does the *new dollar* clear the bar at the *new cap*? A
   follow-on at a $30M cap is a different underwrite than the entry at $6M. Model the
   incremental MOIC on the follow-on check alone.

### Follow-on decision tree

```
Next round announced
        │
        ▼
Is it an up round with a credible lead? ──No──► Diligence why (flat/down/bridge).
        │ Yes                                    Down round? ──► 03-crisis-management.md
        ▼
Is the company on the fund-returner path?
(memo of record still holds / strengthened)
        │
   No ──┴── Yes
   │          │
   ▼          ▼
Decline    Reserves available in the pre-allocated pool?
pro-rata;      │
tell the    No ─┴─ Yes
founder      │        │
the real     ▼        ▼
reason.   Conviction  Does the NEW dollar clear MOIC at the NEW cap?
          high enough      │
          to raise an   No ─┴─ Yes
          SPV?             │       │
            │              ▼       ▼
       Yes ─┴─ No       Decline   FOLLOW ON with a $100K/$250K
        │        │      pro-rata  fund check (up to reserve limit)
        ▼        ▼      (signal
   Raise SPV  Decline;  mgmt)
   (Step 5)   manage
              the signal
```

### Follow-on checklist

- [ ] New round terms confirmed (cap, lead, amount, instrument), each figure sourced
- [ ] Memo of record re-read; thesis held/strengthened documented
- [ ] Fund-returner path still credible at the new valuation
- [ ] Reserve availability confirmed against the construction model (no starving)
- [ ] Follow-on check sized at $100K or $250K — **not** $500K/$1M
- [ ] Marginal MOIC on the follow-on dollar modeled at the new cap, ≥ hurdle
- [ ] Pro-rata rights checked in the original side letter — do we even have the right?
- [ ] If declining: founder told the real reason; signaling line offered
- [ ] If conviction > reserves: SPV path evaluated (Step 5)
- [ ] Decision + rationale appended to the memo of record (calibration)

---

## Step 4 — How to mark the position

Marks follow the valuation policy in
[`../06-lp-relations-fund-ops/02-fund-reporting.md`](../06-lp-relations-fund-ops/02-fund-reporting.md).
The short version for this playbook:

| Event | Mark |
|---|---|
| Priced up round with a new lead | Mark to the new round price (a real, arms-length event) |
| SAFE/note at a higher cap, no priced lead | Hold at cost or mark cautiously — a cap is not a price |
| Flat round | Hold at cost |
| Down round / recap | Mark **down** promptly to the new reality — no delay on bad news |
| Insider-only bridge | Hold at cost; a bridge is not a validation event |

Principles: **cost until a priced round or material event**; a higher SAFE cap alone
is not a markup; and mark-downs are taken as promptly as mark-ups — faster, if
anything. Normalize CAD deals to USD at the stated FX rate. Never present an
unrealized mark as a return.

---

## Step 5 — SPV mechanics (follow-on beyond reserves)

When conviction in a breakout genuinely exceeds the fund's reserve capacity, the tool
is a **special-purpose vehicle**, not a bigger fund check. See the SPV/follow-on
material in
[`../04-portfolio-construction/`](../04-portfolio-construction/).

| Question | Consideration |
|---|---|
| Why an SPV, not a fund check? | Fund checks are capped at $100K/$250K and reserve capacity; the SPV lets high-conviction LPs concentrate without breaching Fund I discipline |
| Who invests? | Existing LPs and vetted co-investors — offered fairly, per the conflicts policy in [`../07-governance-compliance/`](../07-governance-compliance/) |
| How is it structured? | Separate vehicle, its own docs, carries its own economics; kept legally and financially distinct from Fund I |
| Conflict management | Allocation between fund and SPV must be fair and documented — disclose to the LPAC; never advantage the SPV over the fund |
| Reporting | SPV marks reported to SPV participants; **not** blended into Fund I MOIC/TVPI |

The SPV is how a small fund still "shows up big" for its winners without violating the
check-size discipline that defines Fund I.

---

## Step 6 — Communicating markups to LPs

- **Frame markups as unrealized and provisional.** "Company X raised at a higher cap;
  our position is marked up accordingly. This is paper, not cash — it converts to
  return only on exit." Set expectations every single time.
- **Report the mark, the basis, and the policy** in the quarterly letter (see
  [`../06-lp-relations-fund-ops/01-lp-comms.md`](../06-lp-relations-fund-ops/01-lp-comms.md)).
  Note whether we followed on, and if not, that it was reserve math, not doubt.
- **Never lead the story with a markup.** A concentrated seed fund lives on realized
  MOIC over a long hold; interim marks are proxies, and LPs who anchor on them are set
  up for disappointment. Under-promise; let exits speak.
- **Surface strategic-LP relevance** (FCC/CFIN) where the round advances a policy
  outcome — a Canadian company scaling, jobs created, clean-tech milestone hit.

---

## Illustrative example (framed as illustrative)

*Illustrative only — not a real portfolio outcome.* Suppose a company we entered on a
$250K check at a $6M cap raises a Series A at a $30M pre. Our position marks up ~5x on
paper. The follow-on question is **not** "we love this company"; it is: does a *fresh*
$250K at the $30M cap still clear our MOIC hurdle on its own, and is that $250K in the
reserve pool without starving another reserved position? If yes, we follow on to our
reserve limit. If conviction runs past the reserve, we raise an SPV. If the fresh
dollar does not clear the hurdle at the new cap, we decline pro-rata and tell the
founder plainly that it is fund-size math — then let the winner keep running.
