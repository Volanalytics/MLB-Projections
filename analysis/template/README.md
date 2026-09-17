# MLB V2 Daily Intelligence Report Template v1.0

**Status:** APPROVED / LOCKED PUBLICATION CONTRACT  
**Effective:** 2026-09-17

The MLB V2 Daily Intelligence Manifest is the analytical/research contract. This template is the publication/output contract. Every daily report must conform to the current approved template version, and DOCX + HTML must be rendered from the same validated canonical report object.

## Locked null-state vocabulary

`CONFIRMED`, `PROVISIONAL`, `INFERENCE`, `UNRESOLVED`, `INCONCLUSIVE`, `NOT_YET_AVAILABLE`, `NOT_APPLICABLE`.

Blank mandatory fields are prohibited.

## Locked report order

1. Report Header & Provenance
2. Executive Summary & Decision Readiness
3. Top Board / Research Priorities
4. Data Integrity Flags
5. Full-Slate Intelligence Board
6. Game-by-Game Intelligence Brief
7. Starter-Role & Workload Audit
8. Bullpen Availability Audit
9. Mandatory Media Intelligence
10. Market Consensus & Wager-Family Analysis
11. Weather / Park / Umpire Intelligence
12. Cross-Slate Themes
13. Live-Trading Watchlist
14. What I Could Not Source
15. DB Queries / Pipeline Checks
16. Actionable Summary
17. Provenance / Revision History

## Locked full-slate board columns

Game/start; Phase; Readiness; Projected score; Model total; Model win % / fair ML; Market ML; ML break-even / delta; Market total; Total delta; Away TT; Home TT; Classification; Best expression; Data confidence; Context confidence; Action confidence.

## Mandatory per-game field groups

Identity; Projection; Moneyline; Full-Game Total; Away Team Total; Home Team Total; Starting Pitching; Lineups; Bullpen - Computed; Bullpen - Declared; Weather/Park/Roof; Umpire; Injuries/Rest/Defense; Media Intelligence; Model vs Intelligence; Best Wager Expression; Live Trading Trigger; Unresolved Items; Confidence.

Computed bullpen status and explicit manager/coach declarations must remain separate. Every game must retain Moneyline, Full-Game Total, Away Team Total and Home Team Total fields even when a market is `NOT_YET_AVAILABLE`. Every game must display Data Integrity, Contextual Intelligence and Actionable Conclusion confidence.

## Publication pipeline

Manifest research/analysis -> canonical JSON -> schema validation -> matching DOCX + HTML -> publication validation -> current HTML + immutable archive + `analysis_manifest.json`.

Publication must fail if a required section, game, or mandatory per-game field is absent. Earlier archive revisions must be preserved.

## Visual contract

HTML: Roboto Mono 400/500/700 with system monospace fallback; field `#08161B`; panel `#102A31`; panel 2 `#173A44`; line `#1F5058`; chalk `#EAF0F6`; muted `#8199B0`; accent `#3FD0C9`; gain `#8CC63F`; loss `#E8615C`.

## Canonical schema

`analysis/template/mlb_v2_daily_intelligence_report_schema_v1.0.json`

The approved portable DOCX specification is maintained as `MLB_V2_Daily_Intelligence_Report_Template_Specification_v1.0.docx`. Structural changes require an explicitly approved template revision; ordinary daily content changes do not change the template version.
