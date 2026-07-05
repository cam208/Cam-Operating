# 09.03 — Crisis Management

The triage framework for when a portfolio company hits trouble. Portfolio crises are
**inevitable** in early-stage investing — at a ≥20% bear-case fail floor across 15–20
companies, we will face multiple over the fund life. The job is not to avoid them; it
is to respond fast, correctly, and within our actual authority.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). We write $100K/$250K
> checks and hold **information rights and usually an observer seat — not a board
> seat and never control**. Every protocol below is written for an investor who has
> influence, not a vote. Governance mechanics live in
> [`../05-portfolio-services/03-board-governance.md`](../05-portfolio-services/03-board-governance.md).

---

## The one-screen version

- **Influence, not control.** We cannot fire a CEO, block a round, or force a sale.
  Our tools are the relationship, the truth spoken plainly, warm intros, and — at the
  extreme — our reputation and our willingness to withhold future support.
- **Speed beats perfection.** Crises compound. A same-day honest conversation beats a
  perfect memo next week. Triage within 24–48 hours of the signal.
- **Protect the fund AND the founder — in that order under fraud, reversed otherwise.**
  For operational crises we lean all the way in for the founder. For integrity
  crises, the fund and the LPs' trust come first.
- **Everything is logged against the memo of record.** A crisis is a calibration
  event: what did the bear case in [doc 01](./01-first-90-days.md) get right or miss?

---

## Crisis-type triage table

| Crisis type | Early signal | Severity | Immediate response | Who leads |
|---|---|---|---|---|
| **Running out of runway** | Burn up, no term sheet, <4 mo cash | 🔴 Critical | Runway tree (below); get the real number today | Cam |
| **Co-founder split** | Comms breakdown, equity dispute | 🔴 Critical | Separate calls each founder; protect the cap table | Cam |
| **Key customer loss** | Top logo churns / LOI dies | 🟠 High | Re-underwrite concentration; GTM help | Cam + Shane |
| **Down round / recap** | New money only at lower price | 🟠 High | Mark down; assess dilution/wipeout; [markups](./02-markups.md) | Cam |
| **Fraud / integrity issue** | Misstated metrics, misused funds | 🔴 Critical | Preserve record; legal counsel; notify LPAC | Cam + counsel |
| **Pivot** | Thesis/product materially changing | 🟡 Watch→High | Re-run thesis fit; still on-vector? | Cam |
| **Acquihire pressure** | Early low offer, team-only interest | 🟠 High | Model liq-pref waterfall; [exits](./04-exits.md) | Cam |
| **Legal / regulatory** | Enforcement, IP suit, compliance gap | 🟠 High | Contain; counsel; assess existential vs. cost | Cam + counsel |

Severity legend: 🔴 Critical = existential / act today · 🟠 High = act this week ·
🟡 Watch = monitor with a defined trip-wire.

---

## Universal first 48 hours (any crisis)

1. **Get the real facts.** One direct call with the founder. What is actually true,
   what is the timeline, what have they already done? Separate fact from fear.
2. **Assess our authority honestly.** We influence; we do not control. Name what we
   can actually do (intros, advice, a hard conversation, our own follow-on) versus
   what we cannot (fire, block, force).
3. **Triage severity** using the table. Existential today, or manageable this week?
4. **Decide our role** (see below) and who leads.
5. **Log it** against the memo of record and flag on the Portfolio Snapshot. If
   material to marks or LPs, route to
   [`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/).

---

## Runway-emergency decision tree

The most common crisis. The instinct is to reflexively bridge; the discipline is to
decide whether *this company still deserves fresh capital at all*.

```
Runway alarm (<4 months cash)
        │
        ▼
Get the REAL runway number today (verified burn + cash, not the founder's estimate)
        │
        ▼
Is there a credible path to a new lead / term sheet in the runway window?
        │
   Yes ─┴─ No
   │         │
   ▼         ▼
Help close   Is the company on the fund-returner path? (re-read memo of record)
the round        │
(intros,     No ─┴─ Yes
refs,         │        │
GTM proof)    ▼        ▼
   │       Do NOT     Can an insider bridge realistically reach the next milestone?
   │       bridge.    (not just extend the runway — REACH a value-creating milestone)
   │       Guide to      │
   │       soft landing/ No ─┴─ Yes
   │       wind-down.  │        │
   │       (04-exits)  ▼        ▼
   │                 Do NOT   Is bridge capital within reserves at $100K/$250K,
   │                 throw    and does the new dollar clear MOIC? (02-markups gates)
   │                 good        │
   │                 after   No ─┴─ Yes
   │                 bad.     │        │
   │                          ▼        ▼
   │                     Consider  Participate in the bridge (fund reserves,
   │                     SPV /     or SPV if beyond reserves). Tie money to a
   │                     decline   milestone, not just more time.
   │                     & manage
   │                     signal
   ▼
Round closes → resume standard cadence; log the near-miss in the memo of record
```

**Bridge discipline:** a bridge must reach a *milestone*, not just buy months. "Six
more weeks of the same" is not a plan. If the bridge does not change the company's
trajectory, it is throwing good money after bad — decline and manage the signal
([doc 02](./02-markups.md)).

---

## Redstick's role by crisis type

| Crisis | What we CAN do (influence) | What we CANNOT do (no control) | Fund-first? |
|---|---|---|---|
| Runway | Broker intros, refs, follow-on/bridge, GTM help | Force a round to close | Balanced |
| Co-founder split | Mediate informally, protect cap table advice, counsel intro | Remove a founder, force a buyout | Founder-first |
| Customer loss | GTM playbook (Cam), supply-chain fix (Shane), new intros | Win the account back for them | Founder-first |
| Down round / recap | Advise on terms, decide our own follow-on, mark honestly | Block the round, set the price | Balanced |
| Fraud / integrity | Preserve records, counsel, notify LPAC, exit relationship | Prosecute; unilaterally claw back | **Fund-first** |
| Pivot | Re-underwrite thesis fit, honest go/no-go input | Veto the pivot | Balanced |
| Acquihire | Model the waterfall, advise sell vs. hold | Force or block the sale | Balanced |
| Legal / regulatory | Counsel intro, help scope existential vs. cost | Make the liability disappear | Balanced |

**The fraud exception is absolute.** On a genuine integrity issue — misstated metrics,
misused funds, material misrepresentation — the founder relationship is secondary to
the fund's and the LPs' interests. Preserve the record, get counsel, notify the LPAC,
and do not help paper over it. Our reputation with LPs is the fund's real asset.

---

## Communications guidance

| Audience | What / when | Tone |
|---|---|---|
| **Founder** | Immediately, directly, privately. Truth over comfort. | Candid, on their side (except fraud) |
| **Co-investors / lead** | Coordinate on operational crises; align, don't freelance | Collaborative |
| **LPAC** | On material events, down rounds, and **any** integrity issue | Prompt, factual, no spin |
| **Full LP base** | Material impairments in the quarterly letter — never buried | Honest, no surprises |
| **Public / press** | Default: nothing. Never comment on a portfolio crisis publicly | Silence |

Principles: **bad news travels first and fast** to those who need it; no LP learns of
a material problem from someone other than us; we never spin an impairment; and we
never comment publicly on a company's crisis. Deliver-bad-news mechanics live in
[`../06-lp-relations-fund-ops/01-lp-comms.md`](../06-lp-relations-fund-ops/01-lp-comms.md).

---

## After the crisis — calibration capture

Every resolved crisis (recovery, down round, or write-off) gets logged against the
memo of record:

- **What was the early signal, and did we catch it fast enough?**
- **Was this in the bear case we wrote at close?** If not, why did we miss it?
- **Did influence-not-control constrain us? Would a different term (info rights,
  observer, pro-rata) have helped?**
- **What does this teach the next underwrite?** Feed it into the annual
  lessons-learned review ([`../../operating-cadence.md`](../../operating-cadence.md)).

> *Illustrative only:* a company might churn its anchor customer (40% of ARR),
> triggering a runway alarm within two quarters. The playbook response — verify the
> real runway, decide if the fund-returner path survives the loss, help re-underwrite
> the pipeline with Cam's GTM and Shane's supply-chain help, and bridge only against a
> concrete milestone — is the same regardless of the specific company. This is a
> worked example, not a real portfolio event.
