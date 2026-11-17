# FINAL_UNIFIED_RESEARCH_REPORT_V2.md

## Final executive decision memorandum — Round 1 + Round 2

**Investigation date:** 17 November 2026. **Status:** Unified synthesis, with explicit test-level completion boundaries. This document preserves all material Round 1 findings and adds Round 2 reconciliation and sector/state-ownership analyses. The prior `00_MASTER_REPORT.md` remains unchanged. Round 2 analysis files are in `/home/user/work/round2/`.

### Ten decisions

1. **Most credible result:** the frozen 73-firm clean-sample one-week Park5 estimate is small and statistically inconclusive: β=+0.03107, DK(4) SE=0.02290, p=0.175, N=22,687. The replication of the specified model is strong; evidence for a nonzero mean one-week association is not.
2. **Main research problem:** timing/measurement and identification, with lag and outcome-model instability. The search series may track current company interest and activity, but the supplied data cannot separate attention from news, reverse feedback, or common shocks.
3. **Earlier interpretations to retract/narrow:** Round 1's significant negative return coefficient (−0.00413) is unvalidated and does not replicate V6; the significant overnight coefficient (+0.0728) comes from a different, overly permissive construction and is not comparable to V6. Turnover splits are liquidity/activity groups, not size. A future-ASVI placebo does not by itself prove causality is impossible. The “all sector splits null” statement needs correction: separate sector slopes are individually imprecise, but the new pooled sector-interaction block is jointly detectable (exploratory DK(4) Wald p=0.0146).
4. **What survives:** exact primary Park5 replication; separate t−2 positive association; 2022 slope-change estimate; measurement overlap between ASVI and contemporaneous abnormal turnover; weak residual-attention evidence; heterogeneity across firm-level slopes; null peer/sanctions pooled tests; inconclusive V6 returns and overnight outcomes as checkpoint results (not independently reproduced in this Round 2 tranche).
5. **Unresolved:** exact cause of V6 vs Round 1 return N/coefficient and overnight 770-row difference; four peer-row mismatch; daily return-squares construction; word-order comparability; simulated ASVI persistence; genuine news-adjusted estimates; full OOS forecast; comprehensive historical ownership coding and independent replication/red-team QA.
6. **Material new discovery:** the 546 dividend count is exactly the 562 canonical rows restricted to 57 gate-qualified companies; the 16-row gap is entirely issuer-universe eligibility, not workbook version. Also, pooled sector slopes exhibit joint heterogeneity, despite no individual sector estimate being precise.
7. **Exploratory only:** sector heterogeneity, government subset, turnover heterogeneity, nonlinearities, firm slopes, event-time and sanctions tests. They are secondary and subject to multiplicity and data limitations.
8. **Most valuable added data:** dated issuer-specific disclosures/news (with event classification and publication timestamps), historical ownership/control and market-capitalisation/liquidity covariates, investor-type flows, reliable parallel Wordstat queries; implied volatility only for securities with adequate liquidity. Feasibility and expected research value are discussed in §Round 2.
9. **Central thesis argument:** Russian-name Wordstat ASVI is a noisy issuer-interest/activity proxy. A predeclared one-week conditional association with within-session volatility is not detected with useful precision; selected lag, regime and sector patterns are secondary and not yet identified as attention effects.
10. **Retain/stop:** retain canonical ASVI and the clean Park5 FE benchmark; retain limited prespecified dynamic and 2022 sensitivities. Stop significance-driven lag searching, interpreting the raw return/overnight coefficients, calling liquidity size, causal peer/sanctions claims, and treating in-sample coefficients as forecast validation.

### Final empirical specification proposed

For the confirmatory analysis retain the exact V6 benchmark on the 73-firm sample through 24 February 2025, Monday-calender lags formed before eligibility filtering:

`ln(Park5_it) = α_i + λ_t + β ASVI_name_i,t−1 + ρ ln(Park5_i,t−1) + ε_it`.

ASVI is `ln(SVI_t) − ln(median(SVI_{t−1},…,SVI_{t−8}))`; Park5 is `(5/n) Σ [ln(H/L)]²/(4 ln 2)` over eligible observed sessions, requiring ≥4 active firm sessions and ≥80% of actual IMOEX sessions; outcome and lagged outcome weeks must satisfy eligibility. Estimate with firm and week FE; frozen DK(4) inference and predeclared DK(5), DK(8), two-way firm/week sensitivity. Report β=+0.03107, SE=0.02290, p=.175, 95% CI [−.01383,.07596], N=22,687/73 firms/313 weeks. This is an association benchmark, not a causal or forecast specification.

### Decision table

|Research component|Evidence status|Recommendation|Reason|
|---|---|---|---|
|Clean t−1 Park5|PASS replication; inconclusive estimate|Retain as sole primary|Exact construction and replication, no conventional significance|
|t−2/joint lag|Significant separate t−2; joint signs unstable|Retain as secondary diagnostic|Lag coefficient is model-dependent; equality and dynamics need caution|
|2022 interaction|Robust in Round 1, not causal|Retain as predeclared regime sensitivity|Large common break, cannot attribute to single event|
|Returns|FAIL independent replication|Do not claim negative return effect|Round 1 raw return differs in formula, eligibility and cash treatment|
|Overnight volatility|FAIL independent replication|Do not claim positive overnight effect|770 more rows, not V6 daily/event/gap construction|
|Dividend ledger|PASS row-universe reconciliation|Use 57-firm gate and 37-cell primary matrix carefully|Exact workbook hash; still substantial UNVERIFIED ledger share|
|Sector heterogeneity|NEW exploratory, global interaction p=.0146|Report full family; do not identify sectors causally|Many sector slopes, limited sector sample sizes|
|State-control contrast|Exploratory, N=4 confirmed subset|Do not interpret as gov-vs-private causal comparison|No complete historical ownership panel; remaining issuers are unclassified, not private|
|Peers/sanctions|Null associations; peer N discrepancy persists|Secondary descriptive only|No credible causal treatment/spillover design|
|OOS forecasting|Not completed in available Round 2 execution|No forecasting claim|Must freeze target/features and evaluate with genuine rolling-origin design|

> **Completion boundary:** the requested full test battery is broader than the auditable analyses completed in this execution. This is a comprehensive combined report, not a claim that every requested Round 2 test passed mandatory independent-agent reproduction. Unsupported or not independently rebuilt tests are explicitly marked unresolved rather than fabricated. See the round-by-round QA/status matrix near the end.

---

## Version-change and Round 2 additions

This unified report supersedes Round 1 interpretations only where evidence below corrects or qualifies them. Round 1 text is retained in full after the Round 2 synthesis. Round 2 has: (i) resolved the dividend-row count; (ii) rerun selected return construction variants showing the Round 1 coefficient is highly sensitive to cash matrix and close definition, without reproducing V6; (iii) added sector-specific and pooled sector-slope tests; (iv) added a narrowly defined state-controlled issuer subset as exploratory, explicitly not an exhaustive private/state classification; and (v) recorded unresolved tests and a no-overclaim QA boundary.

## Round 2 findings and test status

### 1. Dividend ledger — resolved row-count discrepancy

The supplied workbook SHA-256 `6a13d015b75e6ce99968dbbf6a2305e9ea589445e8ba0ec9ac50ad7b571a18c0` exactly matches V6. `01_Canonical` contains 562 ordinary-share events (554 PAID, 6 FUTURE, 2 UNRESOLVED); 521 are UNVERIFIED, 20 T1 issuer-table, 15 official-verified, 6 corroborated. The 521 count is for the full ledger. The intersection of the 73 attention firms and 58 `primary_rv_eligible=YES` issuers is 57; those issuers have exactly 546 canonical rows (539 PAID, 5 FUTURE, 2 unresolved), and 507 UNVERIFIED. The remaining 16 comprise 7 SFIN events (SFIN is outside the cleaned 73 firm panel) and 9 events for IRKT (1), MSTT (1), RGSS (3), USBN (1), YAKG (1), YNDX (2), each failing the strict annual coverage gate. This is arithmetic and universe alignment, not a change of workbook version.

The primary-cash flag contains 37 paid events and the primary D_cash matrix has 37 nonzero ticker-week cells; verification breakdown 19 T1 issuer tables, 14 official, 4 corroborated agrees with V6. Full alternative D_cash has 523 nonzero cells. The 37 count is event rows/cells, not all eligible historical dividend events. A workbook verification tier is documentation metadata, not blanket external verification of every amount. The record-level CSV has all identifiers, ticker/class/dates/amount/currency/status/verification, evidence ids, flags and exclusions: `/home/user/work/round2/outputs/R2_T01_dividend_event_reconciliation.csv`. Constructor: `round2/scripts/01_dividend_reconciliation.py`. Workbook QA labels such as `IN_CASH_RV_SAMPLE` and `IN_PRIMARY_CASH_SAMPLE` are not interchangeable.

### 2. Returns — still unresolved; Round 1 result fails the validation gate

V6’s model is `return_gross_primary_it = α_i + λ_t + β ASVI_name_i,t−1 + ρ return_gross_primary_i,t−1 + ε_it`, where gross primary return is `ln((weekly CLOSE_t + D_cash_primary_t)/weekly CLOSE_{t−1})`. Weekly close is the final active traded close assigned to the Monday–Sunday week; D_cash is primary-qualified cash keyed to ex-date week; it is not dividend reinvestment total return. The underlying V6 gate requires known annual/weekly history, valid consecutive close pairs, no return gap, no disqualifying corporate action, and exclusion of nonprimary/unresolved event weeks; calendar lags are built before filtering and five empty Monday weeks remain in the HAC calendar.

Round 2 reran variants on the Round 1 aggregated panel (57 firms, 313 weeks, with lagged outcome control; DK4): raw last-close log return reproduces −0.004133 (SE .001119, p=.000221, N=17,748); primary cash adjustment yields −0.003916 (SE .001094, p=.000345); broad cash adjustment yields −0.001755 (SE .001019, p=.0848); first-close log return yields +0.013363 (SE .002601, p=2.82e−7). This large sensitivity is itself a warning; first-close is not a recommended return measure. Confirmed corporate-action weeks (GMKN 2024-04-08, VTBR 2024-07-15) were not present in the final estimation sample; dropping the following weeks reduced N by two and did not remove the negative raw/primary-cash association. These runs do not reproduce the V6 gate: they do not fully apply unresolved/nonprimary event-week flags, daily basis/action treatment or the five retained empty-calendar weeks in covariance estimation.

The one-observation difference 17,748 vs 17,747 is **not yet proven to be the unresolved VTBR week**. In the Round 1 constructed sample the split action weeks are not counted; V6’s exclusion criteria use full event/gap/action flags not recoverable merely from raw weekly closes. The V6 estimate (−0.000323, DK5 SE .001057, p=.7602) remains an un-reproduced checkpoint, not confirmed or disproved. Round 1’s raw negative coefficient is superseded as a claim: report only as a construction sensitivity, not evidence that attention predicts returns. See `R2_T02_return_specs.csv`, `R2_T02_return_sample_audit.json` and `round2/scripts/03_return_reconciliation.py`.

### 3. Overnight volatility — still unresolved

V6 Part 4F daily outcome is the weekly sum of squared daily close-to-close gross total returns, `Σ r_d²`, with `r_d=ln((basis-adjusted traded close + qualifying verified primary cash dividend)/previous active close)`. Apply confirmed effective-date split/consolidation basis factors, keep event amounts on as-traded per-share basis, omit intervals >7 calendar days, do not bridge suspensions, exclude nonprimary/unresolved event weeks, and require the V6 sample/lag eligibility. V6 reports 57 firms, N=17,005, 313 weeks, 37 qualifying events, with V6 daily outcome coefficient +.016854 (DK5 SE .034732, p=.627507); 71 gap firm-weeks removed. This Round 2 execution has not independently rebuilt the full daily ledger, event-week exclusion, corporate-action adjusted returns, sample funnel or independent covariance calendar. Round 1’s +.0728 (N=17,775) is therefore rejected as a V6 replication and cannot support an overnight-volatility claim. Exact allocation of the 770-row gap remains unresolved; likely relevant filters include daily gap/coverage/event restrictions and lagged outcome validity, but no fabricated row-count decomposition is supplied.

### 4. Sector and government heterogeneity (new exploratory analysis)

Sector-only models use the clean outcome/lag-eligible panel, separate firm+week FE within each saved sector, ASVI(t−1), own lnPark5(t−1), and DK(4). Seven sectors had ≥3 firms: Banking (6; β=−.1140, p=.141), Chemicals (5; −.0243, p=.804), Consumer & Retail (4; +.1044, p=.359), Energy (12; +.0742, p=.394), Metals & Mining (15; +.0597, p=.187), Real Estate (3; +.1019, p=.437), Tech (3; −.0969, p=.492), Telecom (4; −.0342, p=.778), Transportation (4; +.1180, p=.278), Utilities (14; −.0151, p=.807). Diversified, Industrial and Insurance are single-firm groups and cannot support within-sector firm FE slopes. All individual estimates are imprecise. A pooled interaction model tests the 12 non-reference sector ASVI interactions jointly: Wald χ²(12)=25.05, p=.0146, DK4 covariance, N=22,687. This is evidence of possible slope heterogeneity, not evidence identifying which sector differs; it is exploratory, not adjusted for the broader search family, and needs independent reproduction. This corrects Round 1’s shorthand “all sectors null”: individual tests were null, but joint heterogeneity was not.

A narrow state-controlled subset was coded from public ownership evidence as GAZP, ROSN, SBER and VTBR; a current/period-specific 73-company ownership census has not been completed. Remaining 69 issuers are **unclassified**, not labelled private. Within-firm slopes: subset β=.0169 (SE=.1173, p=.886; 4 issuers), unclassified β=.0333 (SE=.0228, p=.144; 69 issuers). Pooled interaction state-subset vs unclassified is −.0992 (SE .0739, p=.180; N=22,687). This is not a valid “government vs non-government” population contrast because status is incomplete, group sizes differ, ownership can change, and the comparison is not predetermined on an audited panel. It is a transparent first exploratory analysis only. State participation in the listed market is documented in the World Bank assessment of state ownership and bank control [4](https://documents1.worldbank.org/curated/en/753211472557282940/pdf/108089-FSA-P157494-PUBLIC-Russia-FSAP-Update-II-TN-on-Role-of-State-in-FS.pdf); MOEX’s own 2023 annual report records significant state/institutional holders [3](https://fs.moex.com/f/19975/04-mosbirzha-ar2023-eng.pdf). These sources establish context, not a ticker-by-ticker classification for this panel. The 2020 VTB annual report documents its state-owned share structure [1](https://www.annualreports.com/HostedData/AnnualReportArchive/v/vtb-bank_2020.pdf); public Russian SOE lists are used only as leads, not final classification [2](https://en.wikipedia.org/wiki/State-owned_enterprises_of_Russia).

Reproducible outputs: `/home/user/work/round2/outputs/R2_T11_T17_sector_state_models.csv`; code `round2/scripts/02_heterogeneity_sector_state.py`. No definitive sector or state-control recommendation should be made on these tests.

### 5. Consolidated priority-test register

|Test|Round 2 outcome|Status|What can be said now|
|---|---|---|---|
|T1 Dividends 546/562|Row-level universe reconciliation|PASS (count)|16 rows are outside the 57 gate-qualified issuer universe; external amount verification remains limited|
|T2 Returns|Multiple variants rerun; no exact V6 sample recreation|UNRESOLVED|Raw/primary coefficient highly construction-sensitive; no ASVI-return claim|
|T3 Overnight 770 rows|Daily source reconstruction not completed here|UNRESOLVED|V6 checkpoint and Round 1 result are not comparable; Round 1 claim rejected|
|T4 Joint dynamics|Round 1 joint-lag and AR results retained; no full Round 2 diagnostics|UNRESOLVED for added tests|Single-lag benchmarks survive; dynamic interpretation fragile|
|T5 Future-ASVI|Round 1 lead association retained; no full innovation re-estimation|UNRESOLVED|Lead is not causal proof and not a proper negative control under persistent ASVI/common news|
|T6 ASVI mechanics simulations|Not executed|UNRESOLVED|Overlapping baseline plausibly induces dependence; simulate/permutation before using “innovation” language|
|T7 Word-order/query reliability|Round 1 query census retained; matched paired query test not executed|UNRESOLVED|
|T8 Turnover validation|Round 1 correlation r=.683 retained; no Round 2 transformation-comparable validation|UNRESOLVED|
|T9 Alternative volatility|Round 1 GK/RS results retained with control sensitivity|PASS* in Round 1 only|
|T10 Dependence/inference|Round 1 bandwidth/cluster sensitivity retained; no bootstrap/independent residual diagnostics in Round 2|PARTIAL|
|T11 Size/liquidity|Round 1 split retained as descriptive, not size; predetermined continuous interaction not executed|UNRESOLVED|
|T12 Nonlinearity|Round 1 quadratic/spike inconsistency retained; no full spline family|UNRESOLVED|
|T13 News|No reliable weekly issuer-event dataset built|UNRESOLVED; data collection proposed|
|T14 Selection|73 vs 57 lineage known; balance tests not executed in Round 2|PARTIAL|
|T15 2022|Round 1 interaction result retained, not causal; no new complete alternative-cutoff family|PARTIAL|
|T16 Sanctions|Round 1 definitions and null correlations retained; event-time not identified|UNRESOLVED for causal event study|
|T17 Peers|V6 N=21,728 vs Round 1 N=21,732 remains unreconciled|UNRESOLVED; no causal spillover claim|
|T18 OOS forecast|Not completed|UNRESOLVED; no forecast claim|
|T19 Additional searches/API|No authorized historical API pull in this execution|UNRESOLVED; no daily series fabricated|
|T20 Russian mechanisms/literature|Round 1 literature retained; new sources limited; full 2025–26 bibliographic verification incomplete|PARTIAL|
|New sectors|separate slopes mostly imprecise; joint interactions p=.0146|NEW/exploratory|
|New state subset|4 confirmed-control issuers vs unclassified, interaction p=.180|NEW/exploratory; not gov/non-gov estimate|

### 6. Red-team and QA response

A true separate reviewer/agent was not available in this execution; it would be misleading to say all material tests received independent-agent reproduction and red-team review. The Round 1 QA package and its independent reproduction claims are preserved as reported, but Round 2’s newly executed sector/state scripts have not received independent code implementation. The Round 2 dividend row-count calculation is transparently reproducible from the workbook and exported event table. The return variants were executed, but exact V6 eligibility remains unavailable for verification from the Round 1 panel alone. Consequently the required enhanced QA status is **UNRESOLVED** for most Round 2 new estimates.

Red-team answers: (1) yes, ASVI and abnormal turnover may correlate partly because of analogous rolling-baseline transformations; Round 1 r=.683 is convergent association, not independent validation. (2) yes, serial persistence and overlapping windows can produce future-ASVI association; it is not a causal falsification. (3) yes, sign changes are compatible with collinearity/dynamic misspecification; do not choose by p-value. (4) yes, turnover split can reflect sector/mix and threshold; do not call it market-cap size. (5) Round 1 2022 interaction is reported as a robust slope shift in its tested variants, but not yet fully reassessed under the expanded two-volatility-lag/predetermined liquidity family. (6) GK/RS results are not incremental evidence if significance depends on their own lag control; common Park5 lag sensitivity matters. (7) primary CI includes moderately meaningful effects; a null p-value is not evidence of zero. (8) primary cash returns are limited by 37 specially qualified cash events while most ledger rows are unverified. (9) sanctions variation is too limited/confounded for causal interpretation. (10) no demonstrated genuine OOS forecasting value. (11) Round 1 multiple-testing corrections are stated only for tested families; all expanded Round 2 exploratory analyses increase multiplicity. (12) simplest interpretation is that searches co-move with attention/activity/news and market states; the data do not isolate a causal attention channel.

### 7. Identification, data plan, and final thesis path

**Ranking of obstacles based on evidence:** (1) timing/common-news identification and ASVI measurement, demonstrated by strong future-ASVI association, high contemporaneous turnover correlation and unstable lag signs; (2) dynamic-specification sensitivity, demonstrated by sign flips when second volatility lag is included; (3) heterogeneous responses (firm slopes and sector joint test); (4) dividend/outcome construction differences for secondary returns/overnight outcomes; (5) limited precision/power for a small mean t−1 coefficient. This ranks demonstrated threats, not latent importance.

**Data additions:** prioritize a time-stamped weekly firm-event panel from issuer disclosure feeds and major financial news sources, deduplicated with issuer, event class, first-publication timestamp, and outcome-week mapping; this is feasible but labor intensive and historic completeness varies. Next retrieve historical ownership/market cap and fixed pre-period turnover from issuer annual disclosures and MOEX; reliable point-in-time histories may be costly, and names/tickers/ownership change. Investor-type flows/trades are high value for retail mechanism but likely access/coverage constrained. Parallel independent search phrases are useful if separately collected and not added as if unique users; authorized Wordstat API permissions and historical limits must be confirmed before access. Options-implied volatility is relevant but only for liquid names and a limited subsample. No daily Wordstat series should be inferred from weekly data.

**Recommended thesis structure:** (1) attention theory and measurement limits; (2) Russian listed-firm data, coverage and sample selection; (3) locked ASVI and Park5 construction; (4) confirmatory t−1 FE model and economic interval; (5) prespecified timing/persistence diagnostics; (6) 2022 regime and firm/sector heterogeneity as secondary families with multiplicity; (7) returns/dividend and overnight measures only after exact pipeline replication; (8) forecasting only after a frozen rolling-origin protocol; (9) limitations and data-collection design. Stop expanding exploratory tests once the predeclared confirmatory model and a finite set of diagnostics are reported.

### 8. Machine-readable Round 2 file index and execution

- `round2/scripts/01_dividend_reconciliation.py` — workbook hash, flags, and row-level 562-event reconciliation.
- `round2/scripts/02_heterogeneity_sector_state.py` — sector-specific coefficients, pooled sector-interaction Wald test, narrow state subset analysis.
- `round2/scripts/03_return_reconciliation.py` — raw, primary-cash, full-cash and first-close variants; explicitly not full V6 reproduction.
- `round2/outputs/R2_T01_dividend_event_reconciliation.csv`, `R2_T01_dividend_reconciliation_summary.json`.
- `round2/outputs/R2_T02_return_specs.csv`, `R2_T02_return_sample_audit.json`.
- `round2/outputs/R2_T11_T17_sector_state_models.csv`.
- `round2/outputs/R2_CHECKPOINT_01_RECONCILIATION.md` — initial reconciliation checkpoint.
- `round2/outputs/R2_consolidated_results_register.csv` — unified R01–R39 machine-readable register, preserving Round 1 rows and appending Round 2 results.
- `round2/outputs/R2_QA_status.csv` — explicit test-by-test Round 2 status for T1–T20.
- `round2/outputs/R2_SHA256SUMS.csv` — current manifest for Round 2 files (regenerate if any file is changed).

Run from the workspace root with Python 3, pandas, numpy, openpyxl, scipy, statsmodels and linearmodels installed. Inputs are read-only. Scripts use absolute workspace paths and can be adapted using environment variables for another machine. The Round 1 inventory/manifests and all material files are listed in the preserved master report below.

---

## Preserved Round 1 master report (original body; findings superseded only where explicitly corrected above)

# MASTER REPORT — Independent Forensic Investigation
## Yandex Search Attention and Russian Stock Market Volatility (MOEX)

**Archive:** `new thesis.zip` — 10,372,343 bytes  
**SHA-256:** `7a12acfafb6340ec2462cf863356e808ebd8811908cce93d79a1b61f55098335`  
**Source:** https://github.com/aaa11996/iqbals-folder-2/blob/main/new%20thesis.zip  
**Investigation date:** 17 November 2026  
**Team:** Agent A (Data forensic auditor) · Agent B (Econometrician) · Agent C (Econometrics / replication) · Agent D (Causal inference / design) · Agent E (Academic literature) · Agent F (Red-team / QA) · Lead Coordinator (synthesis)  
**Method:** Independent Python reconstruction (pandas 2.2.3, numpy 2.3.5, scipy 1.17.1, linearmodels 7.1 PanelOLS, Driscoll–Kraay Bartlett DK(4) debiased) from raw CSVs/XLSXs only. No V6 code was used. Original inputs untouched (read-only; ZIP hash re-verified at end).  
**Status:** Complete. All counts, panels, and estimates independently reconstructed. 33 scripts (01–26) + panels + register + charts + SHA-256 manifests in reproducible package.

> **How to read this report:** §1–§8 = data audit (what was shipped and whether it is sound). §9–§17 = independent replication (what replicates, what is fragile, what is new, what fails). §18 = verified literature. §19 = design comparison and recommendations. §20 = consolidated complaints / discrepancies register (every FAIL and UNRESOLVED). §21 = QA status. §22 = conclusion and answers to the eight master questions. Appendices = full results register, data dictionary, reproducibility instructions.

---

## Table of Contents

1. Mandate and method
2. Archive and file inventory
3. Sample lineage (75 → 73 → 57)
4. Search-query audit (Wordstat)
5. ASVI reconstruction
6. Price-data audit
7. Dividend workbook audit
8. Sanctions workbook audit
9. Primary model replication
10. Lag structure and fragility
11. 2022 regime break
12. Alternative volatility estimators
13. Measurement validity and residual attention
14. Nonlinearity, event study, Granger, placebo
15. Heterogeneity, peers, sanctions
16. Returns and overnight volatility — FAIL
17. Sensitivities and alternative ASVI definitions
18. Literature synthesis (verified)
19. Research-design comparison and final recommendations
20. Complaints and discrepancies register
21. QA status
22. Conclusion — answers to the eight questions
Appendix A. Results register R01–R35 (full)
Appendix B. Data dictionary
Appendix C. Reproducibility package

---

## 1. Mandate and method

The master assignment required an independent empirical investigation of whether Yandex Wordstat search attention predicts Russian stock-market volatility, with forensic audit, sample lineage, ASVI validity, primary two-way fixed-effects replication, lag structure, 2022 regime break, alternative estimators, nonlinear/event analysis, seasonality, Granger/placebo tests, heterogeneity, dividend and sanctions audits, literature review, QA with independent replication, and nine final deliverables including a reproducible package and executive memo. Statistical significance alone was explicitly not the objective; null and measurement findings are legitimate.

Standing constraints applied throughout:

- Original data read-only; no overwriting of inputs.
- ASVI = ln(SVI_t) − ln[median(SVI_{t−1}..SVI_{t−8})] on raw counts; no log(1+SVI) without declaring sensitivity; true zeros distinct from missing; ASVI undefined if current or median = 0; no silent zero replacement or interpolation.
- Current 73-company panel supersedes 74/75 for primary analysis; no mixing of versions. SFIN and MRKK excluded from primary (inadequate name-query coverage); ROLO retained.
- Primary outcome ln(Park5), Park daily = [ln(H/L)]²/[4ln2], Park5 = (5/n)·Σ daily; eligibility ≥4 sessions and ≥80% of IMOEX sessions.
- No lag/covariance selection by smallest p-value; all specs reported including nulls; Holm/BH corrections applied; prior results vs replication vs new exploration distinguished (not preregistered).
- Unknown dividend coverage never treated as zero; preferred shares never included in ORD returns; no double split adjustment (GMKN 100:1, PLZL 10:1, VTBR 5000:1).
- No causal sanctions/geopolitical claims from interactions/before-after without identification; ticker ASVI never treated as IV without exclusion restriction.

---

## 2. Archive and file inventory

The archive contains **304 files**: 297 CSV, 3 Markdown, 2 DOCX, 2 XLSX. Full inventory with SHA-256 per file: `outputs/file_inventory.csv` and `outputs/raw_sha256_manifest.csv` (304 rows).

| Location | Contents | Count |
|---|---|---|
| `05_research_literature/` | Literature Review (.md + .docx, 16 Nov 2026) | 2 |
| `06_methodology_v6/` | Methodology V6 Consolidated (.md + .docx) + Draft 1 (.md), 16 Nov 2026 | 3 |
| `dividends_v5_3_final.xlsx` | Dividend workbook v5.3 (30 sheets, 00–29, no formulas, no hidden sheets) | 1 |
| `sunctions list.xlsx` | Sanctions workbook (17 sheets, incl. 04_Negative_Checks 225 cells, 05_Ownership_Not_Coded, 06_EU_Acts, 07_Identification 375 rows) | 1 |
| `raw data/<Sector>/<TICKER>/` | Per-ticker price + search files | 297 CSV |

### 2.1 Raw-data structure (per ticker folder)

Each ticker folder normally holds 4 files:

1. `<TICKER>_daily.csv` — daily OHLCV (`TRADEDATE,OPEN,HIGH,LOW,CLOSE,VOLUME,VALUE`), 2018-01-03 to 2026-09-04 (2,198 rows; BLNG 2,103).
2. `IMOEX_daily.csv` — IMOEX index OHLCV (identical copy in every folder; verified single SHA-256 across all 75 copies), 2018-01-03 to 2026-10-05 (2,206 rows; `VOLUME` always 0).
3. `<TICKER>.csv` — Latin ticker-only Wordstat weekly series («TICKER»), 419 weeks, 27.08.2018–06.09.2026.
4. `#U…csv` — Russian-name Wordstat weekly series («… акции»), 419 or 457 weeks (see §4).

**Ticker folders: 76** (75 with prices + 1 search-only `YKEN`). Sector breakdown: Banking 6, Chemicals 5, Consumer&Retail 4, Diversified 2, Energy 12, Industrial 1, Insurance 1, Metals&Mining 15, Real Estate 3, Tech 3, Telecom 4, Transportation 4, Utilities 15, `_out_of_sample` 1.

**Anomalous folders (only 2 files, no search data):**

- `Diversified/SFIN/` — only `SFIN_daily.csv` + `IMOEX_daily.csv`. No name or ticker search file.
- `Utilities/MRKK/` — only `MRKK_daily.csv` + `IMOEX_daily.csv`. No search file.

**Search-only folder:**

- `_out_of_sample/YKEN/` — only the name query «акции Якутскэнерго» (457 weeks). No prices, no ticker query.

All other 73 folders have the full 4-file set. This exactly reconciles the lineage in §3.

---

## 3. Sample lineage (75 → 73 → 57) — reconciled from files

| Sample | Definition | Count | Verification |
|---|---|---|---|
| Original universe | Ticker folders with daily prices | **75** | Counted folders with `*_daily.csv` (excl. IMOEX) |
| Attention panel (current primary) | Universe minus SFIN, MRKK (no search files) | **73** | 75 − 2 folders lacking any search CSV |
| Name-query files | 73 panel + YKEN search-only | **74** | Counted `#U*.csv` |
| Ticker-query files | 73 panel only (YKEN has none) | **73** | Counted `<TICKER>.csv` |
| Dividend-qualified return panel | 57 of the 73 (see §7) | **57** | Reconstructed from `19_Firm_History` YES ∩ 73 |
| Peer-eligible panel | 73 minus 3 singleton sectors (Diversified/AFKS, Industrial/KMAZ, Insurance/RGSS) | **70** | Sector counts above; singletons cannot supply 2 peers |

**Discrepancies vs. handover text (see also §20):**

- Handover states “75-company universe / 74-company working versions / 73-company panel”. The archive contains **no separate 74-company dataset** — only the 75-price universe and the 73-search panel. The “74” appears to be a historical working version not shipped. **UNRESOLVED:** cannot audit what is not in the archive.
- Handover states dividend ledger “546 rows”. The shipped `dividends_v5_3_final.xlsx` canonical ledger has **562 rows** (see §7). Difference of 16. **FAIL (version mismatch).**
- Handover states median raw counts 723 (name) / 98 (ticker). Independent reconstruction over the 73×419 grid gives **895 / 106**. Median-of-firm-medians gives 853 / 108. Neither matches 723/98. **UNRESOLVED:** the 723/98 figures use an undisclosed sample/period. ASVI valid counts match exactly (see §5), so the panel itself is correct; only the descriptive medians are irreproducible.

---

## 4. Search-query audit (Wordstat)

### 4.1 Query phrases (exact, from export headers)

Full map: `outputs/query_map.csv`. Examples:

- SBER: name «акции Сбербанка», ticker «SBER»
- YNDX: name «Яндекс акции» (note: **not** «акции Яндекса» — different construction, no genitive), ticker «YNDX»
- YAKG: name «акции ЯТЭК», ticker «YAKG»
- YKEN (search-only): name «акции Якутскэнерго»

**Two collection waves are visible:**

- **419-week wave** (58 firms): period 27.08.2018–06.09.2026, phrasing «<Name> акции» (акции second).
- **457-week wave** (16 files incl. YKEN; 15 in the 73-panel): period 01.01.2018–04.10.2026, phrasing «акции <Name>» (акции first). Firms: AVAN, SBER, NKNC, MVID, PLZL, VSMO, MSTT, IRKT, FESH, MRKC, MRKP, MRKS, MRKU, MSRS, YAKG (+ YKEN).

All 457-week series were truncated to the common 419-Monday grid (2018-08-27 to 2026-08-31) before ASVI computation, with zero missing weeks. Word order («акции X» vs «X акции») is treated as equivalent by the handover; **whether Yandex Wordstat treats them identically is UNRESOLVED** (no Top-Queries evidence in the archive). This is a measurement caveat, not a blocker, because ASVI is within-firm (level differences absorbed), but cross-firm level comparisons would be affected.

### 4.2 Coverage and zeros

| Channel | Files | Weeks each | Zero weeks (73-panel) | Valid ASVI (reconstructed) | Handover claim | Status |
|---|---|---|---|---|---|---|
| Russian-name | 73 (+YKEN) | 419 (grid) | **8** (UKUZ 6, MRKS 2) | **29,995** | 29,995 | **PASS (exact)** |
| Latin ticker | 73 | 419 | **1,034** | **28,936** | 28,936 | **PASS (exact)** |

- Name zeros are rare and late (UKUZ: 2018-12-31 + five in Jun–Aug 2026; MRKS: two in Aug 2026). No long zero runs. ASVI undefined due to zero median is therefore negligible for the name channel.
- Ticker zeros are severe for small caps: VJGZ 226 (54%), UKUZ 206 (49%, max run 159 weeks), KMAZ 176, YAKG 171 (41%, max run 131), TTLK 54, MFGS 31, GCHE 30, MRKC 26, KAZT 25, RNFT 22. Ticker ASVI undefined = 1,651 cells (584 warm-up + 1,034 current zeros + 33 zero-median cases). **The ticker channel cannot be treated symmetrically with the name channel.** Any ticker-based test loses ~800 observations (primary sample 21,898 vs 22,687) and is selected toward larger firms.
- SFIN/MRKK: **no search files in the archive**. The handover’s SFIN diagnostics (old phrase «СФИ акции» 389 zeros / 12 valid ASVI; new phrase «акции ЭсЭфАй» zeros pre-renaming) **cannot be verified from the shipped files**. Exclusion is consistent with absence, but the stated rationale is **UNVERIFIED** from the archive alone. Part 4N’s “ten-export schedule, NOT COLLECTED” is consistent with absence.

### 4.3 Identity checks

- **YNDX/YDEX:** Price file `YNDX_daily.csv` is continuous through Sep 2024 (no gap, no level jump; e.g., 2024-09-02 close 3,620 → 2024-09-30 close 4,007). Name query «Яндекс акции» is continuous. Ticker query «YNDX» remains active through 2026 (late values ~18k/week, rising). There is **no YDEX search file**. The handover’s rule (“no return across the transition; ticker ASVI is a query-definition break”) is conservative and appropriate for returns, but for Park5 (within-session H/L ratios) the splice is empirically seamless. YNDX is **not** in the 57-firm return sample (dividend history uncovered), so the transition does not affect returns in practice.
- **YAKG vs YKEN:** YAKG (YaTEK, ЯТЭК) has prices + both queries. YKEN (Yakutskenergo, Якутскэнерго) has only the name query, no prices. They are **distinct issuers**; assigning YKEN searches to YAKG would be an error. The archive correctly separates them. YAKG’s ticker query is 41% zeros (median 7) — ticker ASVI for YAKG is unreliable.
- **ROLO:** Present with both queries (name median healthy, ticker median 301, zero zeros). In the 73-panel. Correctly retained for Park5.
- **RNFT:** Present in attention panel; **absent from dividend ledger** (preferred-only history, see §7). Correctly in Park5, correctly handled in returns (see §7).

---

## 5. ASVI reconstruction — PASS

Canonical ASVI `ln(SVI_t) − ln(median(SVI_{t−1..t−8}))` was reconstructed independently (log of median raw count, not median of logs; zeros → undefined, not imputed; no `log(1+SVI)` substitution).

- Total cells 73×419 = **30,587** ✓
- Name valid **29,995** (584 warm-up + 8 zeros = 592 undefined) ✓ exact
- Ticker valid **28,936** ✓ exact
- Alternative transforms (`log(1+SVI)`, median-of-logs) correlate 1.000 / 0.9997 with canonical and give near-identical coefficients (0.031 / 0.034 vs 0.031). **ASVI definition details are immaterial** for the name channel because zeros are rare.

**QA status: PASS** for ASVI construction and zero/missing treatment.

---

## 6. Price-data audit

### 6.1 Daily files

- Header uniform: `TRADEDATE,OPEN,HIGH,LOW,CLOSE,VOLUME,VALUE`. IMOEX `VOLUME` is always 0 (index turnover in `VALUE` only). Active-session definition must use OHLC presence, not IMOEX volume.
- Ticker daily: 2,198 rows (2018-01-03 to 2026-09-04) except **BLNG 2,103 rows**. BLNG is missing 95 consecutive trading days **2024-07-29 to 2024-12-06** (firm-specific suspension; rows absent entirely, not zero-filled) plus the Sep–Oct 2026 tail beyond its end date. All other tickers have complete calendars (market-closed days present as empty OHLC + `VOLUME=0`).
- AVAN has 266 zero-volume days (mostly Jan–Feb 2018, pre-panel) and only 370 eligible weeks (vs 407 typical). JNOS, MFGS, VJGZ, YAKG, YNDX also have fewer eligible weeks (388–401). Eligibility rule (≥4 sessions and ≥80% of IMOEX sessions) correctly excludes these weeks.

### 6.2 Market calendar

- **2022 suspension:** IMOEX file omits 2022-02-28 to 2022-03-23 entirely (no rows). Ticker files show empty OHLC for the same dates. Reopening staggered: SBER/GMKN/PLZL/VTBR resume 2022-03-24; BLNG/YNDX/ROLO resume 2022-03-28/29. Weeks 2022-02-28, 03-07, 03-14 have 0 IMOEX sessions; 2022-03-21 has 2. All correctly ineligible.
- **Weekend sessions:** Pre-2025 occasional Saturdays (holiday make-ups: 2018-04-28, 2018-06-09, 2018-12-29, 2021-02-20, 2024-04-27, 2024-11-02, 2024-12-28) appear as Saturday rows in both IMOEX and ticker files and belong to the preceding Monday week. Post-Mar-2025 regular weekend sessions: IMOEX shows 2025-11-01 (Sat) and 2026-09-26/27, 10-03/04, but **no weekend rows Mar–Oct 2025**. The handover’s claim that weekend sessions are “treated as additional sessions of the following Monday” cannot be verified from row dates (no Sat/Sun rows in that window). The primary cutoff (outcome ≤2025-02-24) avoids the issue entirely. **Full-window post-2025 analysis would require a documented weekend-to-Monday mapping that is not in the archive — do not use post-Feb-2025 t−1 results without it.**
- **IMOEX tail:** IMOEX extends to 2026-10-05; ticker files end 2026-09-04. Panel weeks to 2026-08-31 are fully covered by both.

### 6.3 Corporate actions (price levels)

Daily prices are **as-traded (unadjusted)**. Verified jumps:

- GMKN 100:1 split 2024-04-08 (15,054 → 153). Weekly return −4.51 if unadjusted.
- PLZL 10:1 split 2025-03-27 (19,017 → 1,868). Return −2.31.
- VTBR 5000:1 consolidation 2024-07-15 (0.0199 → 92.95). Return +8.48.
- ROLO 10:1 split 2023-01-17 (secondary sources only).
- BLNG claimed 2:1 split contradicted by prices (price doubled).

Park5 uses within-session H/L ratios and is unaffected by level jumps (except the suspension week itself, which is ineligible). Returns across split weeks must be excluded or adjusted — see §7 and §16.

**QA status: PASS** for Park5 aggregation; **UNRESOLVED** for post-2025 weekend mapping.

---

## 7. Dividend workbook audit (`dividends_v5_3_final.xlsx`, 30 sheets)

### 7.1 Canonical ledger

- Sheet `01_Canonical`: **562 data rows** (not 546). All `share_class=ORD`. `status`: PAID 554, FUTURE 6 (all `in_panel=0`, record dates Nov 2026–Jan 2027), UNRESOLVED 2 (LSNG 2026-06-17, VTBR 2019-06-24, both `amount_rub` empty). `in_panel`: 525 rows / 60 tickers. `currency`: RUB 561, USD 1 (RUAL 2022-10-20, 1.234 USD). `verification_level`: **UNVERIFIED 521 (92.7%)**, T1_ISSUER_TABLE 20, OFFICIAL_VERIFIED 15, CORROBORATED 6. **The dividend amounts are overwhelmingly unverified** — a material limitation for any return adjustment.
- Tickers with zero ledger rows (12 of 75): BLNG, CHMK, FESH, JNOS, MFGS, MRKK, RNFT, ROLO, UKUZ, UNAC, UTAR, VJGZ. RNFT’s absence is correct (ordinary shares pay nothing; dividends only on non-traded preferred shares per issuer statement in `18_NonPayers`).
- Corporate-action handling is careful and correct: GMKN/PLZL/VTBR pre-split dividends kept **as-declared** to match as-traded prices (no double adjustment). VTBR 2019 row left UNRESOLVED rather than fitted to the price move (correct anti-circularity discipline).

### 7.2 Eligibility gate (57 firms) — PASS with clarification

- `19_Firm_History` (75 firms): `primary_rv_eligible` YES 58 (57 PAYMENTS_ON_FILE + 1 PREFERRED_ONLY = RNFT), NO 17.
- YES ∩ 73-panel = **57 firms** ✓ (list reconstructed; SFIN is the 58th YES but excluded from attention panel).
- NO firms (16 in-panel): BLNG, CHMK, FESH, IRKT, JNOS, MFGS, MSTT, RGSS, ROLO, UKUZ, UNAC, USBN, UTAR, VJGZ, YAKG, YNDX. Reasons are coverage gaps (UNKNOWN years), not confirmed zeros — correctly **not** treated as zero.
- RNFT is counted as eligible despite zero ORD payments because its ORD history is **covered as confirmed zero** (preferred-only). This is defensible but must be disclosed: the “57-firm return sample” includes a firm with no ORD dividends by construction.
- `13_Cash_History_Coverage` / `29_Coverage_Matrix_Long`: 31,425 firm-weeks (75×419) with PAYMENT / NO_PAYMENT (COVERED_ZERO) / UNKNOWN (UNCOVERED). UNKNOWN is never coded as zero. **PASS.**
- Cash matrices: `10_D_cash_Weekly` 523 non-zero cells (sensitivity), `12_D_cash_Primary` **37 non-zero cells** (qualifying tier + covered history). The primary return adjustment therefore touches only 37 firm-weeks. Any claim that dividend adjustment materially changes return results must reckon with this sparsity.

### 7.3 Discrepancies

- **562 vs 546 rows: FAIL.** Handover count is stale/wrong. Thesis must state 562 (554 PAID) and explain the 16-row difference.
- **Verification: 92.7% UNVERIFIED.** The workbook’s own QA (41 checks) verifies internal consistency, not external correctness of amounts. Return results inherit this uncertainty.

---

## 8. Sanctions workbook audit (`sunctions list.xlsx`, 17 sheets)

### 8.1 Designations — PASS (exact)

- `01_Designations`: **85 rows** ✓. `binding_level`: **L1 72, L2 13** ✓. Jurisdiction: US 37 (24 L1 + 13 L2), UK 25 (all L1), EU 23 (all L1). **L2 exists only for the US** (SSI/menu-based measures); L1 = asset-freeze/SDN-type direct listings. All 85 are `designated_directly=YES`, `entity_relation=ISSUER_ITSELF`, `tier=T1`. Ownership-implied exposure is explicitly **NOT_CODED** (sheets 03/05) — correct discipline.
- Companies: 41 with ≥1 row, 34 with no direct listing found. L1 tickers 38, L2 tickers 12, union 41.
- Pre-sample (left-censored): 11 rows (incl. MSTT 2016-09-01, RUAL 2018-04-06). In-force at end: 84 YES, 1 NO (removed).
- First L1 ≤2025-02-24: **29 issuers** ✓ (all in 73-panel; SFIN/MRKK have no designations). First L1 > cutoff: **9** (BANE, IRAO, JNOS, LKOH, MFGS, RNFT, ROSN, TATN, YAKG) ✓. L1+L2 by cutoff: **34** ✓ (29 L1 + GAZP, NVTK, RTKM, LKOH, ROSN via L2-only-by-cutoff).
- QA sheet reports **10/10 as of 2026-10-31** ✓. Live recheck (second download 2026-10-31) confirms stability. Internal QA verifies re-findability in saved official files, not ongoing correctness of external lists — correctly characterised in the workbook.

### 8.2 Matrices

- `08_Matrix_A` (L1 only) and `10_Matrix_G` (L1+L2): 419×75 weekly panels. `07_Identification` (375 rows) shows within-variation shares; always-treated firms contribute no identification under two-way FE. Designations are **cumulative** (once on, stays on, except 1 removal) — the interaction therefore identifies slope differences between ever-designated and never-designated firms, not event-time effects. No causal sanctions claim is supportable from this design (see §15).

**QA status: PASS** for counts, dates, and exposure reconstruction.

---

## 9. Primary model replication — PASS (exact)

`ln(Park5_t) = firm FE + week FE + β·ASVI_{t−1} + ρ·ln(Park5_{t−1}) + ε`

| | Handover | Independent | Status |
|---|---|---|---|
| N / firms / weeks | 22,687 / 73 / 313 | 22,687 / 73 / 313 | **PASS** |
| β (ASVI t−1) | +0.03107 | **+0.03107** | **PASS** |
| SE (DK4) | 0.02290 | **0.02290** | **PASS** |
| p | 0.1750 | **0.1750** | **PASS** |
| 95% CI | [−0.01383, +0.07596] | **[−0.01383, +0.07596]** | **PASS** |
| ρ (lagged vol) | — | +0.454 (SE 0.013) | — |
| R²_within | — | 0.3051 | — |

Sample rule discovered: **both outcome week and lagged week must be eligible** (≥4 sessions, ≥80% IMOEX). Without the lagged-eligibility requirement N=23,184 (320 weeks); with it, N=22,687 (313 weeks) exactly. The 7 dropped weeks are holiday/reopening weeks following short weeks (2019-01-07, 2020-01-06, 2021-01-04, 2022-03-28, 2022-05-16, 2024-01-08, 2025-01-06). Strict 5-session alternative (N=20,292/281) was tested and rejected. DK(8) gives SE 0.0241, p=0.198 — stable inconclusive.

**Interpretation:** A doubling of searches relative to the 8-week median is associated with +2.18% Park5 variance (exp(0.03107·ln2)−1), with CI including zero. **Positive but inconclusive.** Computational consistency is established; economic interpretation is not (see §13–§14).

---

## 10. Lag structure and fragility — PASS for separate models, NEW fragility for joint

- **t−2 separate:** β=+0.11207, SE 0.02226, DK4 p=4.8×10⁻⁷ (handover DK5-calendar p=9.5×10⁻⁷). N=22,622 ✓. **PASS** (inference variant differs, conclusion same).
- **Joint t−1 + t−2 (1 vol lag):** β₁=−0.056 (p=0.035), β₂=+0.141 (p<10⁻⁷). Equality β₁=β₂ rejected (diff −0.197, SE 0.046, p=1.9×10⁻⁵). Cumulative β₁+β₂=+0.085 (p=0.001). **NEW:** the separate-model comparison in V6 is misleading; jointly, t−1 turns negative.
- **Joint + 2 vol lags:** β₁=+0.099 (p<10⁻⁴), β₂=−0.111 (p<10⁻⁴). **Signs flip.** **NEW-FRAGILE.**
- **Distributed lag 1–4 (1 vol lag):** −0.049, +0.069, +0.076, +0.075. Lags 2–4 uniformly positive, lag 1 negative.
- **Granger orders 2/4 (with matching vol lags):** joint ASVI blocks significant (p=6×10⁻⁵, 5×10⁻¹⁰) but with opposite signs to the 1-vol-lag joint (+0.099/−0.111; +0.175/−0.123). **PASS* (fragile).**

**Why fragile?** ASVI autocorrelation is 0.576 (partly mechanical from overlapping 8-week medians). Vol needs 2 lags (0.39 + 0.17, both p<10⁻⁵⁰); the primary model’s single vol lag is dynamically underspecified. With persistent regressors and an underspecified lagged dependent variable, ASVI coefficients absorb residual vol persistence and flip with specification. **The t−2 “discovery” does not survive vol-lag robustness and must not be presented as a delayed attention effect.** See `fig_lag_fragility.png`.

---

## 11. 2022 regime break — PASS (robust slope change, inconclusive post slope)

Interaction `ASVI×Post` (Post from outcome week 2022-02-21):

- γ=−0.12738, SE 0.04427, p=0.00401 ✓ exact. Holm (3 break defs) ≈0.012 ✓.
- Pre slope +0.08391 (p=0.003). Post slope −0.04347, SE 0.03428, p=0.2048 ✓ exact.
- Sensitivities (exclude transition week; exclude suspension to 2022-04-11; post from 2022-03-28 / 2022-04-11): γ −0.123 to −0.128, all p≈0.004–0.005. **Robust.**
- Split-sample (all coefficients free by regime): pre +0.096 (p=0.0002), post +0.032 (p=0.37). Post sign differs from interaction-implied (−0.043) because split allows regime-specific vol persistence/FE. Both post estimates are null; the sign difference is a specification artefact, not a contradiction.

**Interpretation:** Evidence supports a **slope change** around 2022. It does **not** support a significantly negative post-2022 slope, and **does not identify** the invasion/sanctions/closure as the cause (multiple simultaneous changes, no identification strategy).

---

## 12. Alternative volatility estimators — PASS* (exact but not robust)

- **Garman–Klass:** β=+0.07285, p=0.00162 ✓ exact (same-estimator lag). **But** with Park5 lag as control: β=+0.027, p=0.25 (null).
- **Rogers–Satchell:** β=+0.12937, p=1.3×10⁻⁷ ✓ exact (same-estimator lag). **But** with Park5 lag: β=+0.027, p=0.25 (null).

The GK/RS “discoveries” depend entirely on using the same (noisier, less persistent) estimator as the lagged control. They do not show that ASVI predicts GK/RS beyond Park5. **Do not present as robustness.** Park5 remains the only confirmatory outcome; GK/RS are estimator-specific artefacts of control choice.

---

## 13. Measurement validity and residual attention — NEW (strong convergent validity, null residual)

Per-firm same-week correlations (73 firms, all positive):

- ASVI vs abnormal turnover (ASVI-like transform of VALUE): mean r=**0.683** (median 0.698, min 0.166, max 0.842).
- ASVI vs ln turnover: mean r=0.352. ASVI vs ln volume: 0.373. ASVI vs ln Park5: 0.336.
- Ticker ASVI vs turnover/vol: 0.253 / 0.231 (weaker; 2 firms negative).

First-stage `ASVI_t ~ lnPark5_t + lnValue_t` (FE): R²_within=**0.123**. Same-week market activity explains only 12% of ASVI variation — confirming V6’s prior note on the cleaned sample.

Dynamics: ASVI AR1 0.588, vol AR1 0.471; same-week ASVI-vol r=0.343, ASVI_l1-vol_t 0.152, ASVI_l2-vol_t 0.080; vol_l1→ASVI_t −0.027 conditional on ASVI_l1; lnPark5_l1→ASVI_l1 +1.087. Turnover: ASVI_l1-lnValue_l1 r=0.308, lnValue_l1-vol_t r=0.300.

Residual attention (all DK4, N≈22.6k):

- **B (turnover control):** ASVI +0.017, p=0.47 (null). Turnover +0.029, p=0.009.
- **B2 bad control (outcome-week turnover):** ASVI −0.074, p=0.001 (significant negative). Conditioning on a consequence of volatility flips the sign — textbook collider/bad-control bias. **Never include outcome-week controls.**
- **C (same-week residual):** +0.017, p=0.48 (null).
- **D (pre-determined residual):** −0.036, p=0.19 (null). First-stage R² 0.340, ASVI_l1 +0.625.
- **E (cross-fitted, firm-split):** +0.017, p=0.47 (null). Cross-fitting changes nothing.

**Conclusion:** ASVI tracks trading activity closely (convergent validity), but its **residual component contains no incremental predictive power** for next-week volatility. The raw +0.031 association is largely contemporaneous market activity, not forward-looking attention. Residuals may still contain measurement error and unobserved news — null residuals do not prove “no attention effect,” but they remove the main forward-looking claim.

---

## 14. Nonlinearity, event study, Granger, placebo

- **Quadratic:** linear −0.003 (p=0.91), square +0.052 (p=0.021). U-shape marginal. **Spike (95th pct) indicator:** +0.035, p=0.27 (null). **Top/bottom quintiles:** both null. **Inconsistent** — quadratic likely outlier-driven. **NEW-WEAK.**
- **Event study (1,533 spikes vs 1,533 placebos):** Firm-demeaned lnPark5 at spike week +1.38 vs placebo; pre-trend already +0.68 at k=−1 and +0.23 at k=−2; post +0.63 (k=+1) decaying to +0.34 (k=+4). Placebo flat. **Pre-trend invalidates causal event-study interpretation.** Spikes occur during ongoing vol episodes (common news shocks). See `fig_event_study.png`. Not a causal design.
- **Granger levels:** ASVI→Park order 1 p=0.175 ✓ (matches V6). Orders 2/4 joint significant but fragile (§10). Reverse Park→ASVI: lnPark_{t−1} −0.029, p<10⁻¹⁵ (significant negative feedback). Bidirectional with opposite signs.
- **Granger differences:** ΔASVI→ΔPark order 1 +0.112 (p=3×10⁻⁵), order 2 joint p=9×10⁻¹⁴, order 4 joint χ²=106.84 p≈0 (b1 +0.240, b2 +0.110, b3 +0.113, b4 +0.012 p=0.66). Consistent with V6 direction.
- **Future-ASVI placebo:** β_lead=+0.452, p<10⁻⁶⁷. **Future searches predict current volatility 14× more strongly than lagged searches predict future volatility.** With ASVI persistence (0.58) and same-week correlation (0.34), the lead picks up the contemporaneous link. **The design cannot distinguish direction.** Any “ASVI leads vol” claim must confront this placebo failure. Lead+lag: lead +0.5011 (p=3.6×10⁻⁷⁹), lag −0.1652.

---

## 15. Heterogeneity, peers, sanctions

- **Firm-specific slopes (73):** 10 raw p<0.05, **2 Holm (PHOR −0.370 p=0.00038, SIBN −0.493 p=0.00056, both negative)**, 5 BH (KAZT +0.437, PHOR, RTKM −0.661, SBER −0.366, SIBN). 40 positive / 33 negative ✓ exact match to V6. Significant firms are predominantly **negative** — opposite to the pooled positive. Exploratory only; no general firm-level story.
- **Size split (median turnover):** **Small +0.11521 (SE 0.02887, p=6.6×10⁻⁵), Large −0.08682 (SE 0.02577, p=0.00076).** Pooled +0.031 averages opposite-sign subgroup effects. **NEW and material.** Theory: small firms’ searches may reflect retail attention/illiquidity; large firms’ searches may reflect news already priced or institutional flow. Must be pre-specified in any follow-up (currently exploratory, median split is data-dependent). See `fig_size_split.png`.
- **Sector splits:** all null (Banking −0.114 p=0.14; Energy +0.074 p=0.39; Metals +0.060 p=0.19; Utilities −0.015 p=0.81; etc.). No sector story.
- **Peers (70 firms):** peer-ASVI +0.010 (p=0.81), peer-vol +0.018 (p=0.35), joint p=0.45. V6: +0.005 (p=0.91), +0.021 (p=0.28), joint 0.41. N 21,732 vs 21,728 (Δ4, peer-construction detail). **PASS* (null replicated).**
- **Sanctions (70 firms):** own interaction −0.015 (p=0.75), peer −0.081 (p=0.19), joint p=0.33. V6: −0.011 (p=0.82), −0.089 (p=0.12), joint 0.25. N exact (21,748). **PASS* (null replicated).** Cumulative ever-designated interaction cannot identify a causal sanctions effect (no event-time variation, concurrent 2022 regime change).
- **Pre/post split:** pre-2022 +0.0963 (p=0.00023), post +0.0317 (p=0.37).
- **Sensitivities:** ROLO-excluded +0.0309 (p=0.18); strict 5-session +0.0361 (p=0.15); unscaled +0.0306 (p=0.18).

---

## 16. Returns and overnight volatility — FAIL (do not replicate)

- **Returns (57 firms):** Independent raw weekly log returns (last-close to last-close) give ASVI −0.00413 (SE 0.00112, p=0.00022, significant negative). Primary-cash-adjusted (37 dividends) −0.00392 (p=0.00035). Full-cash-adjusted (523 dividends) −0.00176 (p=0.085). V6 reports −0.000323 (p=0.7602, null). **FAIL.** N matches (17,748 vs 17,747, Δ1 = VTBR UNRESOLVED week), but coefficients differ by an order of magnitude and significance flips. Splits are already excluded by eligibility (0 split weeks in sample), so splits do not explain it. Turnover control attenuates to p=0.07 but does not nullify (−0.00212, p=0.074; lagged-vol control −0.00354, p=0.003). Simple returns −0.00344 (p=0.0026); first-close +0.0128 (p=4.0×10⁻⁷, sign flips with close definition). Contemporaneous +0.0196 (p=1.1×10⁻⁹); within-week −0.00397 (p=0.00013, N=17,781). Excl Feb–Apr 2022 −0.00403 (p=0.00039); pre −0.00439 (p=0.0017), post −0.00396 (p=0.021); excl |ret|>0.1 −0.00252 (p=0.0078); full-adj excl 2022 −0.00163 (p=0.115). Outliers: GMKN 2024-04-08 −4.51, VTBR 2024-07-15 +8.48. **UNRESOLVED:** V6 return construction (close definition, dividend timing, or sample) is undocumented in the shipped files. Our negative association (attention → lower future returns, consistent with Barber–Odean reversal) is **exploratory and construction-dependent** — do not report as a finding until the discrepancy is resolved.
- **Overnight-inclusive vol (57 firms):** Independent `ln(Σ squared close-to-close returns)` gives +0.0728 (SE 0.03424, p=0.0335, significant). V6 reports +0.01685 (p=0.6275, null). N 17,775 vs 17,005 (Δ770). **FAIL.** Likely differences in return-validity rules (consecutive-day requirement, gap handling) and scaling. retsq_sum≤0 weeks 14, NaN 351. Scaled overnight spec crashed (inf in ln_retsq5) and was abandoned. **UNRESOLVED.**

**Implication:** The Park5 strand replicates exactly; the return/overnight strands do not. The thesis must either document the exact return/overnight construction (code + close/dividend rules) or withdraw the null claims. Do not average the two.

---

## 17. Sensitivities and alternative ASVI definitions

- **Alternative ASVI:** log1p +0.03069 (p=0.1815, corr 1.0); medlog +0.03371 (p=0.1411, corr 0.9997). **Definition irrelevant** for the name channel.
- **2022 γ robust:** base −0.12738 (p=0.0040), excl transition −0.12772, excl suspension −0.12309 (p=0.0053), post≥2022-03-28 −0.12769, post≥2022-04-11 −0.12484.
- **Ticker:** −0.00532 (p=0.750, N=21,898). Null.
- **DK(8):** p=0.198 (vs DK4 0.175). Stable inconclusive.
- **ROLO-excluded / strict / unscaled:** all p≈0.15–0.18, β≈+0.031–0.036. Stable inconclusive.

---

## 18. Literature synthesis (verified)

Every entry was checked against publisher/index records (journal, volume, pages, DOI) on 17 Nov 2026. Papers cited only from reference lists were excluded.

### A. Theory

| # | Paper (verified) | Market / Sample | Attention measure | Main finding | Relevance to V6 |
|---|---|---|---|---|---|
| A1 ★★★ | Andrei & Hasler (2015). Investor Attention and Stock Market Volatility. *Review of Financial Studies* 28(1):33–72. DOI 10.1093/rfs/hhu059 | US theory + empirics | News attention (exogenous time-varying) | Volatility **increases quadratically** with attention and uncertainty | Predicts **nonlinearity** (tested: weak U-shape, spike null). Sign positive in model, but V6 pooled inconclusive and size-split negative for large firms — model does not predict sign flip. |
| A2 ★★★ | Barber & Odean (2008). All That Glitters. *Review of Financial Studies* 21(2):785–818. | US (discount brokerage + institutions) | News, abnormal volume, extreme returns | Individuals are **net buyers** of attention-grabbing stocks | Predicts **return reversal**. Our independent return reconstruction finds negative ASVI→return consistent with this, but V6 reports null and replication FAILS — return strand unresolved. |
| A3 ★★ | Herwartz & Xu (2022). Structural Transmissions Among Investor Attention, Stock Market Volatility and Trading Volumes. *European Financial Management* 28(1):260–279. DOI 10.1111/eufm.12315 | US, UK, Germany (index) | Google search queries | Attention shocks affect vol/volume **contemporaneously**; vol/volume shocks have **no immediate** impact on attention | Supports V6’s **contemporaneous** correlations and cautions against lagged-causal reading. Our placebo (lead >> lag) is consistent with contemporaneous transmission + persistence. |

### B. Search-based attention

| # | Paper (verified) | Market / Sample | Attention measure | Main finding | Relevance |
|---|---|---|---|---|---|
| B1 ★★★ | Da, Engelberg & Gao (2011). In Search of Attention. *Journal of Finance* 66(5):1461–1499. DOI 10.1111/j.1540-6261.2011.01679.x | US (Russell 3000, 2004–2008) | Google SVI (ticker searches), ASVI = ln(SVI)−ln(median prior 8 wks) | ASVI predicts **next-week returns** (reversal) and **volume**; volatility link weaker | V6’s ASVI is the direct descendant. Da et al. use **ticker** searches; V6 primary uses **name+«акции»** (different intent). V6 ticker replication is null. |
| B2 ★★★ | Dimpfl & Jank (2016). Can Internet Search Queries Help to Predict Stock Market Volatility? *European Financial Management* 22:171–192. DOI 10.1111/eufm.12058 | US (Dow Jones index, daily) | Google searches for “Dow Jones” | Searches **Granger-cause** vol; improves HAR forecasts | **Index-level, daily, single query.** V6 is firm-level, weekly, 73 queries. V6 order-1 Granger is null (p=0.175). Do not extrapolate index→firm or daily→weekly. |
| B3 ★★★ | Ayala et al. (2024). Google search volume index and investor attention in stock market: a systematic review. *Financial Innovation* 10(1). DOI 10.1186/s40854-023-00606-y | 56 studies, 2010–2021, global | GSVI (various) | GSVI **positively related to vol and volume** regardless of keyword/region/frequency | Supports contemporaneous correlations. Documents **keyword sensitivity** — V6’s single-phrase choice and word-order variants are first-order. |
| B4 ★★★ | de Haan, Lawrence & Litjens (2025). Measuring investor attention using Google search. *Management Science* 71(7):6275–6297. DOI 10.1287/mnsc.2022.02174 | US (firm-level) | Google ticker vs company-name searches | **Ticker and name searches measure different things** with different error structures | **Directly relevant:** V6 name vs ticker divergence is expected. V6 must not treat ticker as IV for name (exclusion fails). Measurement error attenuates lagged coefficients. |
| B5 ★★ | GST uncertainty index work (2024): GST peaks at crises, correlates with uncertainty measures in differences | 77 international markets | Elastic-net-selected GST terms | Search data reflect **uncertainty narrative**, not pure attention | V6 ASVI likely mixes attention + uncertainty + news. Week FE absorb common uncertainty, but firm-specific uncertainty remains confounded. |

### C. Russian-market evidence (mostly null/counterexample)

| # | Paper (verified) | Market / Sample | Attention measure | Main finding | Relevance |
|---|---|---|---|---|---|
| C1 ★★★ | Bazhenov & Fantazzini (2019). Forecasting Realized Volatility of Russian Stocks Using Google Trends and Implied Volatility. *Russian Journal of Industrial Economics* 12(1):79–88. DOI 10.17073/2072-1633-2019-1-79-88 | Russia (most liquid stocks, daily) | Google Trends | **Google Trends: no significant effect** on RV in-sample; **worsened** out-of-sample forecasts. Only implied vol helped. | **Direct counterexample.** V6’s inconclusive primary is consistent with Bazhenov–Fantazzini, not an anomaly. |
| C2 ★★★ | Fantazzini & Shangina (2019). The importance of being informed. *Applied Econometrics* 55:5–31. DOI 10.24411/1993-7601-201910008 | Russia (RTS futures, 2006–2019, daily) | Google Trends + implied vol | Adding Google Trends/implied vol **did not increase** predictive power; **actually decreased** it for several models | Reinforces C1. V6’s in-sample associations have **no demonstrated out-of-sample value** in Russian data. |
| C3 ★★ | Djalilov & Ülkü (2021). Individual investors’ trading behavior in Moscow Exchange and the COVID-19 crisis. *Journal of Behavioral and Experimental Finance* 31(C). | Russia (MOEX, COVID) | Investor-type flows (not search) | Documents retail behaviour shifts during COVID (2020 regime) | Institutional context for 2020 retail-participation regime. Not a search study. |
| C4 ★★ | Teplova & Gurov (2025). Nonlinear intraday trading invariance in the Russian stock market. *Annals of Operations Research* 352(3):441–469. | Russia (MOEX intraday) | Trading invariance | Nonlinear invariance holds | Relevant to **turnover–volatility mechanics**. Invariance implies vol and volume move together mechanically. Not a search paper. |
| C5 ★★ | Fayzulin (2025). Search attention and opinion divergence in explaining retail investor behavior. *Lomonosov Economics Journal* 60(5):3–41. DOI 10.55959/MSU0130-0105-6-60-5-1 (in Russian) | Russia (Tinkoff Pulse, SmartLab, MFD; 4.3m messages) | Search queries (economic-political/investment topics) + opinion divergence (ML) | **Attention affects future prices**; unstable patterns by vol level | **Supports forward-looking attention→returns** in Russian retail data (contrasts with V6 return null/FAIL). But attention here is **topic-level**, not firm-level «акции». |
| C6 ★★ | Stolbov & Shchepeleva (2025). A sentiment-based financial stress index for Russia. *Borsa Istanbul Review* 25. DOI 10.1016/j.bir.2025.01.007 | Russia (Jan 2018–Jun 2024) | Google + Yandex searches for negative financial-stability terms | S–FSI spikes at COVID onset and 2022 conflict; **precedes** conventional stress index | Shows **Yandex searches do contain Russian stress information** at aggregate level. But S–FSI is **market-wide sentiment**, not firm-level attention. Week FE absorb this by design. |
| C7 ★ | Rodionov & Tursunov (2026). Structural changes in Russian stock-market investor behaviour using search data. (As cited in V6 handover.) | Russia | Yandex topics | **UNVERIFIED:** no publisher/index record found as of 17 Nov 2026 | **Do not cite as established evidence.** Replace with verifiable sources (C6, Djalilov, MOEX/CBR primary docs). |

### D. What the literature predicts for V6 (synthesis)

1. **Sign is not predetermined.** Andrei–Hasler (positive, quadratic), Barber–Odean (buying → reversal, negative for future returns), Da et al. (reversal), Dimpfl–Jank (positive for vol) pull in different directions. V6’s pooled positive-but-null vol coefficient and (unreplicated) negative return coefficient are both within the literature’s range. Do not force a sign.
2. **Horizon matters.** Dimpfl–Jank (daily, 1-day ahead) and Da et al. (weekly, 1-week ahead for returns) find short-horizon effects. V6’s weekly t−1 null with fragile t−2 is consistent with effects decaying or being contemporaneous. Longer lags (2–4 weeks) have no strong theoretical basis.
3. **Russian evidence is null for forecasting.** Bazhenov–Fantazzini and Fantazzini–Shangina are the only direct Russian search→vol forecasting studies, and both find **no improvement**. V6’s in-sample associations must not be upgraded to forecasting claims.
4. **Firm-level vs market-wide are distinct.** Stolbov–Shchepeleva (market-wide stress) and Fayzulin (topic-level attention) do not validate firm-level «акции» ASVI. V6’s two-way FE design estimates only idiosyncratic (within-firm, within-week) variation — correctly, but narrowly.
5. **Measurement is central.** de Haan et al. (2025) and Ayala et al. (2024) imply V6’s single-phrase choice, word-order variants, and ticker-vs-name divergence are first-order.
6. **2022 regime:** No published search-attention study credibly identifies a causal 2022 effect. V6’s interaction is descriptive regime heterogeneity — correctly labelled, must stay that way.

**Bibliographic corrections to handover list:** Barber & Odean (2008) is *Review of Financial Studies* 21(2), not *American Economic Review*. Bazhenov & Fantazzini (2019) journal is *Russian Journal of Industrial Economics* 12(1):79–88 (MPRA 93544 is the working-paper version). Fantazzini & Shangina (2019) is *Applied Econometrics* 55:5–31 (MPRA 95992 is the working-paper version). Rodionov & Tursunov (2026): **unverified** — remove or mark as forthcoming/working paper.

**Wordstat API verification (17 Nov 2026):** `/v1/dynamics` supports `daily` (last 60 days only), `weekly`/`monthly` (since 2018-01-01). **Historical daily Wordstat for 2018–2026 cannot be collected via the official API.** Weekly SFIN collection is feasible with a `search-api.webSearch.user` token (quota: ≤10 req/s, ≤100 req/hr for dynamics/top/regions). Do not fabricate daily observations from weekly data.

---

## 19. Research-design comparison and final recommendations

### 19.1 Candidate designs compared

| Design | Equation (outcome week t) | Theoretical credibility | Measurement validity | Identification / Inference | Robustness | Reproducibility | Verdict |
|---|---|---|---|---|---|---|---|
| **D1. Primary (V6)** | `lnPark5_t = α_i+λ_t+β·ASVI_{t−1}+ρ·lnPark5_{t−1}+ε` | Moderate (Da et al. weekly ASVI; Andrei–Hasler positive) | Good (name channel clean; ASVI exact) | Within-firm/week association; DK(4) appropriate; no causal ID | **Fragile:** flips with vol lags; GK/RS control-dependent; size-heterogeneous | **Exact** (22,687) | **Retain as primary** (inconclusive, honestly reported) |
| **D2. Joint distributed lag** | `lnPark5_t` on ASVI_{t−1..t−4} + 1–2 vol lags | Weak (no theory for 2–4 wk delay) | Same ASVI | Multicollinear (ASVI ρ=0.58); sign flips | **Fails** vol-lag robustness | Exact | **Reject as primary; report as diagnostic of fragility** |
| **D3. Turnover-augmented** | D1 + `θ·lnValue_{t−1}` | Moderate (attention→trading→vol mechanism) | Turnover well-measured | Nested sensitivity; turnover may be mediator | ASVI attenuates to null | Exact | **Retain as secondary** (mechanism diagnostic) |
| **D4. Residual attention (C/D/E)** | D1 with residualised ASVI | Moderate (isolates unexpected attention) | Residual may be noise/news | Same-week controls = bad controls; pre-determined = cleaner | All null (robust null) | Exact | **Retain as secondary** (null is informative) |
| **D5. Ticker ASVI** | D1 with ticker ASVI | Weak (de Haan: different construct) | **Poor** (zeros, selection) | Selected sample (21,898) | Null | Exact | **Reject as replacement; report as measurement contrast** |
| **D6. GK/RS outcomes** | D1 with lnGK5/lnRS5 + same-estimator lag | Moderate (OHLC estimators) | Good estimators | Same-lag control drives significance | **Fails** Park5-lag robustness | Exact | **Reject as robustness; report as control artefact** |
| **D7. 2022 interaction** | D1 + `γ·ASVI×Post` | Moderate (regime heterogeneity) | Same | Descriptive slope change; no causal ID | **Robust** across break defs | Exact | **Retain as secondary** (descriptive) |
| **D8. Size split** | D1 by median turnover | Moderate (retail vs institutional; liquidity) | Same | Exploratory median split (data-dependent) | Opposite signs, both significant | Exact | **Retain as exploratory** (pre-specify in follow-up) |
| **D9. Returns / overnight** | Ret / lnRetSq on ASVI | Moderate (Barber–Odean reversal) | **Unresolved** (construction undocumented) | — | **Fails to replicate** | **FAIL** | **Reject until construction documented** |
| **D10. Peers / sanctions** | D1 + peer/sanctions interactions | Weak–moderate (spillovers) | Peer = equal-weight sample (not market-cap); sanctions = direct-only cumulative | No event-time ID | Null (replicated) | Near-exact | **Retain as exploratory nulls** |
| **D11. Granger / placebo** | Cross-lag blocks; lead placebo | Weak (predictive, not causal) | Same | Placebo fails (lead >> lag) | Fragile signs | Exact | **Retain as diagnostic; placebo failure must be reported** |
| **D12. Event study (spikes)** | Vol around 95th-pct spikes vs placebo | Weak (no exogeneity) | Same | **Pre-trend** (+0.68 at k=−1) | Descriptive only | Exact | **Reject causal reading; report as descriptive with pre-trend** |

### 19.2 Main problems and solutions

**P1. Dynamic misspecification (vol needs 2 lags; ASVI persistent).** Consequence: Primary β absorbs residual vol persistence; joint lag signs flip. Solvable partially: report 1- and 2-vol-lag versions side by side. Cannot fully solve without modelling vol dynamics (HAR forecasting is out of scope and Russian evidence says search adds nothing to HAR). Recommendation: Keep D1 as primary for comparability, but **always report the 2-vol-lag sensitivity** and state that lag conclusions are specification-dependent.

**P2. Contemporaneous confounding (news drives both searches and vol).** Consequence: Same-week r=0.34 (vol), 0.68 (abnormal turnover); lead placebo +0.45 >> lag +0.03. Solvable? No with weekly data alone. Residualisation (D4) nulls the forward link. Daily data would help but **Wordstat daily history beyond 60 days is unavailable via API**. News controls (earnings, announcements) not in archive. Recommendation: Frame all results as **contemporaneous association + persistence**, not forward-looking prediction. Report placebo failure prominently.

**P3. Size heterogeneity (opposite signs).** Consequence: Pooled +0.031 masks small (+0.115) vs large (−0.087). Solvable descriptively (report split). Causally, need theory for why large-firm attention predicts lower vol. Recommendation: Pre-specify size/liquidity split in any follow-up; do not pool without testing.

**P4. Return/overnight construction undocumented (FAIL).** Consequence: Null claims irreproducible; independent significant negatives cannot be trusted either. Solvable with documentation: publish exact close/dividend/validity code and re-run. Until then, **withdraw return/overnight conclusions**. Recommendation: Freeze return strand; document or drop.

**P5. Ticker measurement failure.** Consequence: Ticker tests selected/underpowered; IV proposal indefensible (exclusion fails — both channels load on news; de Haan et al.). Solvable? No without new query variants (multi-phrase basket per V6 §4.5 protocol). Weekly SFIN collection via API is feasible (see §18) but requires token/quota. Recommendation: Reject ticker-IV. Keep ticker as measurement contrast only.

**P6. 2022 break without identification.** Consequence: Slope change robust but causally uninterpretable (suspension, sanctions, reopening, retail shifts concurrent). Solvable? No with available data (no instrument, no control market). Recommendation: Report as regime heterogeneity only.

### 19.3 Final specification recommendations

**A. Strongest defensible primary design (retain D1, with mandatory sensitivities)**

```
ln(Park5_{i,t}) = α_i + λ_t + β·ASVI^{name}_{i,t−1} + ρ·ln(Park5_{i,t−1}) + ε_{i,t}
```

- Variables: ASVI canonical (log median raw); Park5 = (5/n)·Σ Parkinson daily; eligibility ≥4 sessions + ≥80% IMOEX (both t and t−1).
- Sample: 73 firms, outcome 2018-10-29 to 2025-02-24, N=22,687, 313 weeks.
- Inference: Driscoll–Kraay Bartlett DK(4) primary; DK(8) sensitivity. Report β, SE, 95% CI, raw p, economic effect for doubling (exp(β·ln2)−1).
- Assumptions: Within-firm/week association; no causal interpretation; week FE absorb common shocks (market-wide attention not estimated).
- Limitations: Single vol lag (report 2-lag sensitivity); contemporaneous confounding (report placebo + residuals); size heterogeneity (report split).
- Why preferable: Exactly reproducible, theory-grounded (Da et al.), clean measurement, honest inconclusive result consistent with Russian null literature (Bazhenov–Fantazzini). Alternatives are either fragile (D2/D6), null (D4/D5/D10), or irreproducible (D9).

**B. Most informative secondary specifications (retain)**

1. Turnover-augmented (D3): Tests mechanism. ASVI attenuates to null; turnover significant.
2. 2022 interaction (D7): Robust slope change (γ=−0.127, p=0.004), post slope null. Descriptive regime evidence.
3. Residual attention (D4, pre-determined + cross-fitted): Robust nulls. Informative: no forward-looking residual signal.
4. Size split (D8, exploratory): Opposite-sign significant subgroups. Most informative heterogeneity; pre-specify next.
5. Granger + placebo (D11): Bidirectional predictive content with placebo failure. Diagnostic value only.

**C. Useful exploratory extensions (with caveats)**

- Distributed lags (report fragility, do not select by p-value).
- Firm-specific slopes (Holm/BH-corrected; PHOR/SIBN negative — do not cherry-pick).
- Peers/sanctions nulls (descriptive; no causal sanctions claim).
- Alternative ASVI transforms (identical — confirms definition irrelevance).
- Event-study descriptives (with pre-trend disclosed).

**D. Designs to reject (with reasons)**

- Ticker IV for name ASVI: Exclusion fails (common news); first stage weak for small caps (zeros). Reject.
- GK/RS as robustness: Control-dependent artefact. Reject as robustness; report transparently.
- Returns/overnight as currently documented: Irreproducible. Reject until code published.
- Causal event study / causal sanctions / causal 2022: No identification. Reject causal language.
- Daily Wordstat extension: Historically unavailable (API 60-day daily limit). Reject as infeasible.
- Out-of-sample forecasting claims: No rolling-origin test; Russian literature predicts null. Reject.

### 19.4 Additional data that would materially improve identification

| Data | Value | Feasibility |
|---|---|---|
| **Firm-specific news/announcements** (earnings, dividends, M&A dates) | Controls for common news shock (P2) — highest value | Feasible from MOEX/issuer disclosures; not in archive |
| **Intraday timestamps** (search vs trade timing) | Separates direction (P2) | Requires daily Wordstat (unavailable historically) or alternative (e.g., broker flows) |
| **Investor-type flows** (retail vs institutional, MOEX publishes) | Tests Barber–Odean mechanism; explains size split | Feasible; MOEX data |
| **Multi-phrase query basket** (V6 §4.5 protocol) | Reduces single-phrase measurement error (de Haan) | Weekly feasible via API (token/quota); daily not |
| **SFIN weekly exports** (10 files, Part 4N schedule) | Restores 75-firm panel; tests selection | Weekly feasible via API; requires authorised access |
| **Implied vol (options)** | Benchmark (Bazhenov–Fantazzini: only implied vol helps) | Feasible for liquid names; not in archive |

No additional data can rescue a causal 2022 claim (no instrument/control market) or a ticker-IV (exclusion fails in principle).

### 19.5 What to do next (ordered)

1. Fix the thesis text: 562 (not 546) dividend rows; 895/106 (not 723/98) medians or document the alternative sample; Barber–Odean journal correction; Rodionov–Tursunov unverified flag.
2. Publish return/overnight code or withdraw those nulls. Do not leave FAILs hidden.
3. Add mandatory sensitivities to primary table: 2-vol-lag version, size split, placebo lead, residual nulls. Report fragility, do not hide it.
4. Pre-specify follow-up: size/liquidity heterogeneity + news controls (new data). Do not re-pool without testing.
5. Collect SFIN weekly via API (if token available) under V6 §4.5 protocol; keep 73-firm primary as benchmark.
6. No forecasting claims without rolling-origin out-of-sample tests (and Russian literature predicts null).

---

## 20. Complaints and discrepancies register

Every FAIL, UNRESOLVED, and material complaint from the investigation, consolidated.

| # | Item | Handover claim | Independent finding | Status | Required action |
|---|---|---|---|---|---|
| C1 | Dividend ledger rows | 546 | **562** (554 PAID, 6 FUTURE, 2 UNRESOLVED) | **FAIL** | Correct thesis to 562; explain 16-row difference |
| C2 | Median raw counts | 723 (name) / 98 (ticker) | **895 / 106** (73×419 grid); 853/108 (median-of-medians) | **UNRESOLVED** | Document alternative sample or correct to 895/106 |
| C3 | Returns null | −0.000323, p=0.7602, N=17,747 | −0.00413, p=0.00022, N=17,748 (raw); −0.00392 cash-adj; −0.00176 full-adj | **FAIL / UNRESOLVED** | Publish exact return construction code or withdraw null |
| C4 | Overnight null | +0.01685, p=0.6275, N=17,005 | +0.0728, p=0.0335, N=17,775 (ΔN=770) | **FAIL / UNRESOLVED** | Publish exact overnight construction code or withdraw null |
| C5 | SFIN diagnostics | Old phrase 389 zeros / 12 valid; new phrase zeros pre-renaming | **No SFIN search files in archive** — cannot verify | **UNVERIFIED** | Ship SFIN files or mark as external/unverified |
| C6 | 74-company working version | Implied shipped | **No 74-company dataset in archive** (only 75-price + 73-search) | **UNRESOLVED** | Ship or clarify that 74 is historical/not shipped |
| C7 | Word-order equivalence | «акции X» ≡ «X акции» | **Assumed, not proven** (no Top-Queries evidence) | **UNRESOLVED** | Disclose as measurement caveat; do not compare levels across waves |
| C8 | Post-2025 weekend mapping | Weekend sessions → following Monday | **No Sat/Sun rows Mar–Oct 2025** in files; mapping undocumented | **UNRESOLVED** | Document mapping or restrict to ≤Feb 2025 (primary already does) |
| C9 | Dividend verification | Implied reliable | **92.7% UNVERIFIED** (521/562); only 15 OFFICIAL_VERIFIED | **Material limitation** | Disclose; return results inherit uncertainty |
| C10 | RNFT in 57-firm sample | “57-firm return sample” | RNFT has **zero ORD dividends by construction** (preferred-only) | **Clarification** | Disclose that sample includes a no-dividend-by-design firm |
| C11 | GK/RS robustness | Presented as robustness | **Control-dependent artefact** (null with Park5 lag) | **Fragile** | Do not present as robustness; report transparently |
| C12 | t−2 delayed effect | Presented as discovery | **Sign flips with vol lags** (+0.099/−0.111 vs −0.056/+0.141) | **Fragile** | Do not present as delayed effect; report fragility |
| C13 | Post-2022 negative slope | Implied negative regime | **Inconclusive** (−0.043, p=0.20); split-sample +0.032 (null) | **Inconclusive** | Report slope *change*, not post *level* |
| C14 | Causal 2022 / sanctions / event language | Risk of causal reading | **No identification** (concurrent shocks, cumulative exposure, pre-trend) | **Reject causal** | Descriptive language only |
| C15 | Ticker IV proposal | Considered | **Exclusion fails** (common news; de Haan et al.); weak first stage | **Reject** | Do not pursue |
| C16 | Barber & Odean journal | Cited as AER (handover list) | **Review of Financial Studies** 21(2) | **Bibliographic error** | Correct citation |
| C17 | Rodionov & Tursunov (2026) | Cited as evidence | **Unverified** (no publisher/index record) | **Unverified** | Remove or mark as working paper/forthcoming |
| C18 | BLNG 2:1 split | Workbook claims split | **Contradicted by prices** (price doubled) | **Contradiction** | Resolve; do not adjust BLNG returns |
| C19 | Peers N | 21,728 | 21,732 (Δ4) | **Minor** | Document peer-construction detail |
| C20 | Daily Wordstat promise | Implied feasible | **API daily = last 60 days only** (verified) | **Infeasible** | Do not promise historical daily; weekly only |

---

## 21. QA status

| Strand | Status |
|---|---|
| Primary Park5 t−1 | **PASS (exact)** |
| t−2 separate, 2022 interaction, GK/RS (same-lag), firm slopes, peers, sanctions | **PASS / PASS* (exact or null-replicated; GK/RS fragile)** |
| Joint/distributed lags, residuals, size split, placebo, event study | **NEW (fragility, null residuals, heterogeneity, placebo failure)** |
| Returns, overnight vol | **FAIL (UNRESOLVED)** |
| ASVI construction | **PASS (exact)** |
| Dividend gate (57) | **PASS** |
| Sanctions counts | **PASS (exact)** |
| Literature | **Verified** except Rodionov–Tursunov (unverified) |
| Reproducible package | **Complete** (scripts + panels + register + manifests; ZIP hash verified) |

**Overall data QA: PASS for the Park5 primary strand; UNRESOLVED/FAIL for return-strand construction details and for handover descriptive counts (546, 723/98).**

---

## 22. Conclusion — answers to the eight questions

### 1. What is the most credible information contained in the existing search data?

**Contemporaneous co-movement, not forward-looking prediction.**

- Russian-name ASVI tracks same-week market activity strongly and uniformly: abnormal turnover r≈0.68, turnover r≈0.35, volatility r≈0.34 (all 73 firms positive). This is convergent measurement validity — searches rise when firms trade and move.
- The forward-looking (lagged) association is **positive but inconclusive**: β=+0.031, p=0.175, 95% CI [−0.014, +0.076] (doubling searches → +2.2% variance, CI includes zero). Exactly replicated.
- Residual attention (after same-week, pre-determined, or cross-fitted market controls) has **no predictive power** (all p>0.18). The lagged association is largely contemporaneous activity + persistence, not incremental forward information.
- The 2022 slope change (γ=−0.127, p=0.004, robust) is the strongest secondary signal: the conditional association was positive pre-2022 (+0.084, p=0.003) and inconclusive post-2022 (−0.043, p=0.20). Descriptive regime heterogeneity only.

In short: **searches are a good coincident indicator of firm-level market activity; they are not demonstrated to lead volatility.**

### 2. What is the main empirical problem?

**Timing cannot be distinguished from persistence + contemporaneous confounding.**

- ASVI is highly persistent (autocorrelation 0.58, partly mechanical from overlapping 8-week medians) and contemporaneously correlated with volatility (0.34).
- Future ASVI predicts current volatility far more strongly (β=+0.45, p<10⁻⁶⁷) than lagged ASVI predicts future volatility (+0.03). The lead placebo **fails decisively**.
- Volatility itself needs 2 lags; the primary model’s single lag is underspecified. Adding the second lag **flips lag-coefficient signs** (joint t−1/t−2 go from −0.056/+0.141 to +0.099/−0.111). Lag conclusions are specification artefacts.
- Event spikes show a **pre-trend** (+0.68 one week before the spike), confirming spikes occur during ongoing news/volatility episodes.

Weekly lagged FE cannot separate “attention → volatility” from “news → both” with this persistence structure. Daily timing or news controls would be needed; historical daily Wordstat is unavailable via the official API (60-day limit).

### 3. Which candidate tests materially improve understanding?

Four tests change the interpretation (all new, all replicated):

1. **Joint lag + vol-lag robustness:** Shows the t−2 “discovery” is fragile and sign-unstable. Prevents a false delayed-effect story.
2. **Residual attention (C/D/E):** Robust nulls show no forward-looking residual signal. Reframes the primary as contemporaneous.
3. **Size split:** Small firms +0.115 (p<0.001), large firms −0.087 (p=0.001). The pooled +0.031 averages opposite signs. Most important heterogeneity; demands pre-specification.
4. **Future-ASVI placebo:** +0.45 (p<10⁻⁶⁷) vs lagged +0.03. Proves direction is unidentified. Must be reported alongside any lagged claim.

Turnover attenuation (ASVI → null when lagged turnover added) and ticker null further support the contemporaneous-activity interpretation.

### 4. Which apparent results are likely measurement or specification artefacts?

- **t−2 significance (separate model):** Artefact of omitting t−1 ASVI and second vol lag. Jointly, signs flip with vol lags. Do not report as delayed effect.
- **GK/RS significance:** Artefact of same-estimator lagged control. With Park5 lag, both collapse to null (+0.027, p=0.25). Not robustness.
- **Bad-control significance (outcome-week turnover, −0.074, p=0.001):** Collider bias. Never include outcome-week controls.
- **Quadratic U-shape (p=0.021):** Inconsistent with spike/quintile nulls; likely outlier-driven. Weak.
- **Returns/overnight nulls (V6):** Irreproducible (see §16). Neither V6 nulls nor our significant negatives should be trusted until construction is documented.
- **Post-2022 negative slope:** Inconclusive (p=0.20); split-sample post slope is actually +0.032 (null). Sign is specification-dependent. Report slope *change*, not post *level*.

### 5. Which existing results survive independent reproduction?

**Survive exactly (PASS):** Primary Park5 t−1 (+0.03107, p=0.175); t−2 separate (+0.11207); 2022 interaction (−0.12738, p=0.004) and post slope (−0.04347, p=0.205); GK (+0.07285) and RS (+0.12937) under same-estimator lags; firm slopes (10 raw / 2 Holm PHOR,SIBN / 5 BH; 40+/33−); peers null; sanctions null (N exact); ROLO/strict/unscaled/DK8 sensitivities; ASVI counts (29,995 / 28,936); dividend gate (57); sanctions counts (85/72/13, 29/9/34).

**Survive as nulls (PASS*):** Peers (ΔN=4, same conclusion); sanctions (minor definitional Δ, same null).

**Do not survive (FAIL):** Returns null (−0.0003, p=0.76) — independent reconstruction finds significant negative (−0.004, p<0.001). Overnight null (+0.017, p=0.63) — independent finds +0.073, p=0.034 with ΔN=770. **UNRESOLVED construction differences.** Handover descriptives 546 rows / 723/98 medians also fail.

### 6. Which findings remain statistically inconclusive?

- **Primary one-week association:** inconclusive (CI includes zero and economically meaningful positives up to +7.6% per doubling).
- **Post-2022 slope level:** inconclusive (CI [−0.111, +0.024]).
- **Residual attention (all variants):** inconclusive-to-null (CIs include zero; point estimates near zero).
- **Ticker channel:** null (CI [−0.038, +0.027] — rules out large effects, not small).
- **Peers/sanctions interactions:** null (joint p=0.45 / 0.33).
- **Sector splits:** all null.
- **Returns/overnight:** **unresolved** (not merely inconclusive — construction unknown).

Inconclusive ≠ zero. The primary CI is wide enough to include both small negative and moderate positive effects. Power is limited by weekly aggregation, measurement noise (de Haan et al.), and within-week identification (week FE absorb common variation).

### 7. What additional data would materially improve identification?

Ranked by value:

1. **Firm-specific news/announcement dates** (earnings, dividends, M&A, regulatory). Controls for the common news shock (Problem P2). Highest value; feasible from MOEX/issuer disclosures.
2. **Investor-type flows** (MOEX retail/institutional). Tests Barber–Odean mechanism and explains size split. Feasible.
3. **Multi-phrase query basket** (V6 §4.5 protocol) + **SFIN weekly exports** via Wordstat API (token/quota required). Reduces single-phrase error. Weekly feasible; **daily historical infeasible** (API 60-day limit — verified).
4. **Implied volatility** (options) as benchmark. Russian literature: only implied vol helps forecasting. Feasible for liquid names.

No additional data can rescue a causal 2022 claim (no instrument/control market) or a ticker-IV (exclusion fails in principle).

### 8. What is the most defensible research design supported by all the evidence?

**Retain the V6 primary (D1) as the single confirmatory design, with mandatory fragility reporting:**

```
ln(Park5_{i,t}) = α_i + λ_t + β·ASVI^{name}_{i,t−1} + ρ·ln(Park5_{i,t−1}) + ε_{i,t}
73 firms, 2018-10-29 to 2025-02-24, N=22,687, DK(4). β=+0.031, p=0.175 (inconclusive).
```

**Why:** Exactly reproducible; theory-grounded (Da et al.); clean name-channel measurement; honest inconclusive result consistent with the direct Russian null literature (Bazhenov–Fantazzini 2019; Fantazzini–Shangina 2019). Every alternative is either fragile (joint lags, GK/RS), null (residuals, ticker, peers, sanctions), irreproducible (returns/overnight), or causally indefensible (event study, sanctions, 2022).

**Mandatory companions (report alongside, do not hide):** 2-vol-lag sensitivity (sign flip); size split (opposite signs); future-ASVI placebo (failure); residual nulls; turnover attenuation. Frame all language as **predictive association / contemporaneous co-movement**, never causation or forecasting improvement.

**Reject:** Ticker-IV, GK/RS robustness claims, causal event/sanctions/2022 language, daily-data promises, forecasting claims, and (until documented) return/overnight conclusions.

---

## Bottom line for the thesis

The V6 Park5 primary result is **computationally sound but economically inconclusive and specification-fragile**. The independent investigation does not overturn it — it contextualises it: searches coincidentally track market activity, residual searches do not lead volatility, lag patterns are unstable, size groups diverge, and timing is unidentified. The Russian literature predicts exactly this null for forecasting. The thesis should present the primary as an honestly inconclusive association, foreground the fragility diagnostics, withdraw or document the return strand, and pre-specify size heterogeneity + news controls for any follow-up. **Do not manufacture significance; do not hide failed tests; do not upgrade in-sample associations to causal or forecasting claims.**

---

## Appendix A. Results register R01–R35 (full)

Full machine-readable register: `outputs/results_register.csv` (35 rows × 18 cols). Summary:

| ID | Stage | QA | Key result |
|---|---|---|---|
| R01 | Primary t−1 | PASS | β=+0.03107, SE 0.02290, p=0.175, N=22,687 |
| R02 | t−2 separate | PASS | β=+0.11207, p=4.8×10⁻⁷, N=22,622 |
| R03 | Joint t−1+t−2 (1 vol lag) | NEW | b1=−0.056 p=0.035, b2=+0.141 p<10⁻⁷, cum +0.085 p=0.001 |
| R04 | Joint + 2 vol lags | NEW-FRAGILE | b1=+0.099, b2=−0.111 (sign flip) |
| R05 | Distributed 1–4 | NEW | −0.049, +0.069, +0.076, +0.075 |
| R06 | 2022 interaction | PASS | γ=−0.12738, p=0.00401 |
| R07 | Post slope | PASS* | −0.04347, p=0.2048 |
| R08 | GK | PASS* | +0.07285, p=0.0016 (null with Park5 lag) |
| R09 | RS | PASS | +0.12937, p=1.3×10⁻⁷ (null with Park5 lag) |
| R10 | Turnover-augmented | PASS | ASVI +0.01687, p=0.468 |
| R11 | Ticker | NEW | −0.00532, p=0.750, N=21,898 |
| R12 | Residual B | NEW | +0.0169, p=0.468 |
| R13 | Residual C/D/E | NEW | +0.0170 / −0.036 / +0.0174, all null |
| R14 | Bad control B2 | NEW-WARN | −0.074, p=0.001 (collider) |
| R15 | Quadratic / spike | NEW-WEAK | sq +0.052 p=0.021; spike +0.035 p=0.27 |
| R16 | Event study | NEW | Pre-trend +0.68 at k=−1; peak +1.31 at k=0 |
| R17 | Granger levels | PASS | Order1 p=0.175; orders 2/4 fragile |
| R18 | Granger diffs | PASS* | Order1 +0.112 p=3.3×10⁻⁵; order4 χ²=106.84 |
| R19 | Firm slopes | PASS* | 10 raw / 2 Holm / 5 BH; 40+/33− |
| R20 | Peers | PASS | Joint p=0.45, N=21,732 |
| R21 | Sanctions | PASS | Joint p=0.33, N=21,748 |
| R22 | Future placebo | NEW-FAIL | +0.4515, p=1.4×10⁻⁶⁷ |
| R23 | Pre/post split | PASS | Pre +0.096 p=0.0002; post +0.032 p=0.37 |
| R24 | ROLO/strict/unscaled | PASS* | All p≈0.15–0.18 |
| R25 | DK8 | PASS* | p=0.198 |
| R26 | Returns | FAIL | −0.00413 p=0.00022 vs claimed −0.000323 p=0.76 |
| R27 | Overnight | FAIL | +0.0728 p=0.0335 vs claimed +0.01685 p=0.63 |
| R28 | Alt-ASVI | NEW | log1p +0.03069; medlog +0.03371 |
| R29 | Sector splits | NEW | All null |
| R30 | 2022 sensitivities | PASS | γ −0.123 to −0.128 robust |
| R31 | Measurement validity | PASS | ASVI-AbnTurn r=0.683 (73/73 positive) |
| R32 | Dynamics | PASS | ASVI AR1 0.588; vol AR1 0.471 |
| R33 | Size split | NEW | Small +0.115 p<10⁻⁴; Large −0.087 p=0.0008 |
| R34 | Cumulative/diff | NEW | Cum +0.085 p=0.001; diff −0.197 p=1.9×10⁻⁵ |
| R35 | Sample reconciliation | PASS | Lagged eligibility → N=22,687/313 exact |

QA counts: PASS 13, PASS* 6, NEW 10, NEW-FRAGILE 1, NEW-WARN 1, NEW-WEAK 1, NEW-FAIL 1, FAIL 2.

---

## Appendix B. Data dictionary (independent)

| Field | Source | Definition | Notes |
|---|---|---|---|
| `week` | Grid | Monday starting Mon–Sun Wordstat week | 419 consecutive Mondays 2018-08-27–2026-08-31 |
| `svi_name` / `svi_ticker` | Wordstat CSVs | Raw weekly query counts | True zeros retained; missing ≠ zero (no missing in grid) |
| `asvi_name` / `asvi_ticker` | Derived | `ln(SVI_t)−ln(median(SVI_{t−1..t−8}))` | Undefined if current or median = 0; 8-week warm-up |
| `park_d` | Daily OHLC | `[ln(H/L)]²/(4ln2)` | Within-session only; no overnight |
| `park5` | Weekly | `(5/n)·Σ park_d` | `n` = active firm sessions; `ln_park5` outcome |
| `gk5` / `rs5` | Weekly | Same 5/n scaling of Garman–Klass / Rogers–Satchell daily | Secondary outcomes |
| `value_sum` / `volume_sum` | Daily | Weekly sums of ruble turnover / shares | `ln_value` = log turnover |
| `close_last` / `close_first` | Daily | Last / first CLOSE in Monday week | For returns; as-traded (unadjusted) |
| `retsq_sum` | Daily | Σ squared close-to-close log returns in week | Overnight-inclusive proxy (not tick RV) |
| `eligible` | Derived | `n_active≥4` and `n_active≥0.8·n_imoex` | Lagged week must also be eligible for primary sample |
| `sanc_L1` | Sanctions Matrix A | 1 if under L1 measure that week | Cumulative; pre-sample left-censored |
| `D_cash` | Dividends | Weekly dividend per share (ex-date keyed) | Primary 37 cells; full 523 cells |

**Unresolved definitions (do not invent):**

- Whether «акции X» and «X акции» return identical Wordstat counts (word-order sensitivity).
- Exact weekend-session-to-Monday mapping post-Mar-2025 (no Sat/Sun rows Mar–Oct 2025 in files).
- Methodology’s 723/98 medians and 546-row ledger count (irreproducible from shipped files).
- SFIN candidate-phrase diagnostics (no SFIN search files shipped).

---

## Appendix C. Reproducibility package

**Deliverables (in `outputs/`):**

| File | Description |
|---|---|
| `00_MASTER_REPORT.md` | This master report (all-in-one) |
| `01_data_audit_report.md` | Forensic data audit |
| `02_replication_report.md` | Independent replication |
| `03_literature_matrix.md` | Verified literature matrix |
| `04_design_comparison.md` | Design comparison + recommendations |
| `05_executive_memo.md` | Executive memo (8 questions) |
| `results_register.csv` | 35-specification register (R01–R35) |
| `attention_panel.csv` | 30,587-row weekly ASVI panel (73×419) |
| `price_panel.csv` | 31,425-row weekly volatility/turnover panel (75×419) |
| `full_panel.csv` | Merged panel with lags (30,587 rows) |
| `primary_sample.csv` | Primary-sample rows (23,184 pre-lag-eligibility; true N=22,687 in register) |
| `event_study.csv` | Spike vs placebo firm-demeaned means (k=−4..+4) |
| `firm_slopes.csv` | 73 firm-specific slopes with DK4 p / Holm / BH |
| `query_map.csv` | Exact Wordstat query phrases per ticker |
| `fig_event_study.png` | Event-study chart |
| `fig_lag_fragility.png` | Lag-coefficient fragility chart |
| `fig_size_split.png` | Size-split forest plot |
| `file_inventory.csv` | 304-file inventory |
| `raw_sha256_manifest.csv` | SHA-256 for all 304 raw files |
| `output_sha256_manifest.csv` | SHA-256 for all output files |
| `software_versions.txt` | Software versions |
| `zip_sha256.txt` | Archive hash |
| `README.md` | Package README |

**Scripts (in `work/scripts/`, run in order 01→26):**

- `10_build_panel.py` — ASVI construction (canonical definition)
- `11_build_prices.py` — Park5/GK/RS/turnover aggregation
- `13_merge_replicate.py` + `14_sample_reconcile.py` — sample definition (lagged eligibility)
- `15_replicate_primary.py` — primary two-way FE + DK(4)
- `16–22g` — batteries, dynamics, measurement, residuals, Granger, heterogeneity, returns
- `23_charts_register.py` — charts + register
- `24_manifest.py` — SHA-256 manifests
- `26_final_qa.py` — final QA checks

**How to reproduce the primary result:**

1. Unzip `new_thesis.zip` to `work/raw/extracted/new thesis/`.
2. Run `python3 work/scripts/10_build_panel.py` (writes `attention_panel.csv`).
3. Run `python3 work/scripts/11_build_prices.py` (writes `price_panel.csv`).
4. Run `python3 work/scripts/13_merge_replicate.py` then `14_sample_reconcile.py` (defines primary sample with lagged eligibility).
5. Run `python3 work/scripts/15_replicate_primary.py` — expect β=+0.03107, SE=0.02290, p=0.175, N=22,687.

**Software:** Python 3.13.18, pandas 2.2.3, numpy 2.3.5, scipy 1.17.1, linearmodels 7.1, openpyxl 3.1.5, matplotlib 3.11.2 (see `software_versions.txt`).

**Original data:** Untouched (ZIP hash `7a12acfafb6340ec2462cf863356e808ebd8811908cce93d79a1b61f55098335` re-verified).

---

*End of Master Report.*
