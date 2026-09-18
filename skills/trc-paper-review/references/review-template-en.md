# TR-C Simulated Review Template (English, Full)

Follow this structure exactly. Label all scores as **TR-C-style simulated calibration**. Where evidence is unavailable, write **Not sufficiently specified in the provided material**.

---

# TR-C Simulated Review Report

## 0. Paper Summary

In 3–5 sentences: the transportation problem, the proposed method, the data/network used for validation, the main results, and the claimed contributions.

**Metadata**: title / paper type (methodological, empirical, simulation-based, field experiment, survey, data paper) / subfield / target venue (TR-C by default).

## 0.5 Calibration Baseline (only when exemplar papers were uploaded)

List the exemplars used, the extracted bar per dimension (evidence depth, experiment scale, baselines, metrics, reproducibility), and the manuscript's gap against each. If no exemplars were provided, state that calibration used the built-in TR-C journal profile.

## 1. Scope Fit and Title/Abstract/Consistency Check

### 1.1 Transportation-System-Consequence Test (TR-C's core editorial criterion)
- Is the intellectual core on the transportation side or the technology side? State the verdict with evidence.
- Which system-level metrics are reported (delay, capacity, reliability, safety, energy, emissions, service quality) — or only algorithmic metrics?
- If judged "technology demo without transportation consequence", give an explicit redirect recommendation (TR-B / IEEE T-ITS / a CS venue, etc.).

### 1.2 Title Promises
### 1.3 Abstract Claims
### 1.4 Main-Text Support
Judge each abstract claim as supported / partially supported / unsupported, with locations.
### 1.5 Mismatches
List all overclaims (e.g., "general" but tested on a single intersection; "real-time" without runtime reporting; "outperforms SOTA" against outdated baselines).

## 2. Reviewer 1 — Methodological Soundness

### 2.1 Summary
### 2.2 Strengths
Each with a specific section/equation/figure/table anchor and why it matters.
### 2.3 Weaknesses
#### Fatal Issues (structural problems sufficient for rejection)
#### Major Issues (significantly lower the score; fixable in one major-revision cycle)
#### Minor Issues (quick fixes)

Format for each item: **[Location] Problem → Impact on conclusions → Suggested fix**.

### 2.4 Method-Specific Checks
Per the applicable subfield sections of `domain-checklist.md`: assumption realism, model correctness, theoretical properties (stability/convergence/complexity), units and notation, reproducibility of the method.

### 2.5 Questions for Authors
3–6 genuine clarifying questions, not rhetorical ones.
### 2.6 Required Fixes
What must be done to reach Minor-Revision level.
### 2.7 Rating
- Rating: X / 10 (TR-C-style simulated calibration)
- Confidence: X / 5
### 2.8 Score Justification / Why Not Higher / Why Not Lower

## 3. Reviewer 2 — Data, Experiments & Validation

### 3.1 Summary
### 3.2 Strengths
### 3.3 Weaknesses
#### Fatal Issues
#### Major Issues
#### Minor Issues

### 3.4 Missing Experiments
Ranked list of the most needed experiments, e.g.:
- Calibration/validation on real data (first priority for simulation-only papers)
- Stronger baselines (list the subfield-standard baselines from `domain-checklist.md`)
- Sensitivity analyses: penetration rate / demand level / congestion regime
- Multiple seeds with variance and significance reporting
- Scalability: single point → corridor → network
- Degraded-mode tests (communication loss, sensor failure, low MPR)
- Runtime and computational cost reporting
- Surrogate safety metrics (TTC/PET/DRAC) — mandatory whenever safety benefits are claimed

### 3.5 Reproducibility Concerns
Data availability statement, code, seeds, hyperparameters, simulator version and settings, hardware.

### 3.6 Questions for Authors
### 3.7 Required Fixes
### 3.8 Rating
- Rating: X / 10
- Confidence: X / 5
### 3.9 Score Justification / Why Not Higher / Why Not Lower

## 4. Reviewer 3 — Novelty, Significance & Literature

### 4.1 Summary
### 4.2 Strengths
### 4.3 Weaknesses
#### Fatal Issues
#### Major Issues
#### Minor Issues

### 4.4 Novelty Assessment
- The core innovation in one sentence
- Genuine novelty or recombination/scenario-shift of existing modules?
- Is the distinction from the 2–3 closest works made clear?
- Would TR-C reviewers call it incremental? Verdict with reasoning.

### 4.5 Related-Work Gaps
- Without literature search: name only missing **directions/families** (e.g., "recent LLM-based traffic prediction", "robustness of MFD perimeter control"); never fabricate specific titles.
- With search: separate "discussed in the paper" from "found externally but not discussed", with sources.

### 4.6 Significance Assessment
Value to the TR-C readership: theoretical / methodological / data / practical value, assessed separately.

### 4.7 Questions for Authors
### 4.8 Required Fixes
### 4.9 Rating
- Rating: X / 10
- Confidence: X / 5
### 4.10 Score Justification / Why Not Higher / Why Not Lower

## 5. Score Summary Table

| Reviewer | Role | Rating / 10 | Confidence / 5 | Main Positive | Main Negative |
|---|---|---:|---:|---|---|
| R1 | Methodological Soundness | | | | |
| R2 | Data & Experiments | | | | |
| R3 | Novelty & Literature | | | | |

Compute: average / median / lowest / highest; whether there is a clear champion; whether there is a strong reject voice; where the disagreement lies.

## 6. Associate Editor Meta-Review

### 6.1 Overall Assessment
### 6.2 Consensus Strengths
### 6.3 Consensus Weaknesses
### 6.4 Main Disagreement (and whether author response could resolve it)
### 6.5 Fatal Issues (only the truly fatal ones)
### 6.6 Fixable Issues
### 6.7 Revision Potential
High / Medium / Low — can the authors substantively resolve the Major Issues within one major-revision cycle?
### 6.8 Editorial Recommendation
Choose one: **Accept / Minor Revision / Major Revision / Reject**.
If deviating from the score mapping, explain (e.g., the methods expert's Fatal finding outweighs two lenient scores).
### 6.9 TR-C Readiness Score
**XX / 100**, with one or two sentences of derivation (ratings + Fatal/Major ledger).

## 7. Priority Revision Plan

### P0 — Must Fix (rejection otherwise)
### P1 — Strongly Recommended (decides Major vs Minor Revision)
### P2 — Nice to Have

For each item: which reviewer comment it answers, estimated effort (days/weeks), required resources (data, experiments, writing).

## 8. Revision Timeline

A realistic plan matching journal cadence (TR-C's median review cycle ≈ 3 months):
- Week 1–2: …
- Week 3–6: …
- …through resubmission and response-letter drafting.

## 9. Final Direct Answers

1. Can this paper be submitted to TR-C now?
2. If submitted now, what is the biggest rejection risk?
3. Which reviewer would most likely score it low, and why?
4. Which experiment group should be added first?
5. Which section should be rewritten first?
6. What score pattern does the current version look like (e.g., 445 / 556 / 667)?
7. After one serious revision round, what is the realistic score pattern?
8. Should the authors redirect to another venue (TR-B / TRR / T-ITS / ITSC …)? Give the fit reasoning.
9. If major revision: which three points need the most strategic handling in the response letter?

Be strict, direct, and specific. Do not comfort the authors. Every judgment must serve one question: does this paper meet the TR-C publication standard?
