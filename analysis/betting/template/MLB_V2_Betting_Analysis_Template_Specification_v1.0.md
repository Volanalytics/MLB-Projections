# MLB V2 Betting Analysis Template Specification v1.0

## Purpose
This is the locked presentation and analytical contract for the experimental MLB V2 Betting Analysis report. It is separate from, but sourced from, the Daily Intelligence report/package.

## Publication paths
- Template: analysis/betting/template/canonical_betting_template.html
- Schema: analysis/betting/template/mlb_v2_betting_analysis_schema_v1.0.json
- Current: analysis/betting/current/index.html
- Current manifest: analysis/betting/current/manifest.json
- Archive: analysis/betting/archive/YYYY-MM-DD-rN.html

## Checkpoints
9:45 AM establishes the baseline. 12:45 PM, 3:45 PM and 6:45 PM are deltas from the prior checkpoint. Never rewrite earlier snapshots. Freeze a game at its last valid pregame state once it starts.

## Required analytical separation
1. Projection = quantitative prior.
2. Market comparison = discrepancy/price layer.
3. Intelligence = validation/risk layer.
4. Betting state = conclusion from the first three, never a substitute for them.
5. Results/live information are prohibited from revising pregame decisions.

## Lifecycle
DISCOVERED → AUDIT → CONDITIONAL → SUPPORTED → ACTIONABLE → FROZEN.
Backward transitions are valid, including SUPPORTED → CONFLICTED → PASS and CONDITIONAL → INVALIDATED.

## Prices
Always preserve discovery price and checkpoint price history. Report existing-position assessment separately from new-entry assessment.

## Moneylines
When model win probability and verified market price exist, calculate fair ML, break-even probability and theoretical EV. Very large apparent EV (~15–20%+) triggers mandatory model/input audit before promotion.

## Totals
Do not infer a betting probability from the projected mean total alone. If a calibrated simulation probability is available, it may be used and identified. Otherwise report projected total, market total, run gap and intelligence confidence.

## Mandatory extreme-discrepancy audit
Re-check starter identity; starter/opener/bulk role; recent workload and model BF leash; confirmed lineup; injuries/rest; bullpen availability/leverage; park/weather/roof; market freshness; and projection inputs.

## Evidence discipline
Keep structured market, computed bullpen, raw workload/Reliever DB, and attributable media declarations separate. Preserve unresolved/null states. Reliever appearance is a role-conflict flag, not proof of an incorrect starter assignment.

## Locked report sections
01 Provenance
02 Executive Betting Summary
03 Actionable/Supported Board
04 Conditional & Audit Board
05 Full-Slate Betting Board
06 Game-by-Game Betting Analysis
07 Projection vs Market Discrepancies
08 Extreme-Discrepancy Audit
09 Starter/Workload Validation
10 Lineup/Injury/Defense Validation
11 Bullpen/Leverage Validation
12 Weather/Park/Roof/Umpire
13 Market Movement & Price History
14 Checkpoint Delta
15 Frozen Pregame Decisions
16 Remaining Research/Next Checkpoint
17 Methodology & Audit Rules
18 Post-Slate Grading

## Post-slate grading
After the slate is complete, grade raw projection performance, raw model betting-edge performance, intelligence-filtered performance, final pregame decision performance, CLV where available, and attribution for promotions/downgrades/passes. Do not use postgame grading to rewrite the frozen record.

## Validation before/after publication
Fail closed if the canonical template/schema cannot be fetched. Validate section count/order, game count, required game fields, no undefined placeholders, checkpoint/slate date, discovery/current price separation, and current/archive consistency. Re-fetch published artifacts and validate again.
