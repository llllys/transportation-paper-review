# Reference-Paper Calibration / 范例论文校准

When the user uploads one or more **published TR-C papers** (or other exemplars) as references, use them to calibrate the review — this is what makes the review "符合 TRC 真实难度" rather than generic. Build the calibration profile BEFORE writing any review verdicts.

## Step 1 — Classify each exemplar

For each uploaded reference paper, record:

- Subfield and paper type (must overlap with the manuscript's subfield to be useful for calibration; note mismatches)
- Publication venue and year (confirm it is actually TR-C if claimed)
- Approximate quality tier based on evidence depth (field data vs. simulation-only, network scale, baseline strength)

## Step 2 — Extract the calibration profile

Distill the exemplars into concrete, comparable benchmarks:

| Dimension | What to extract from exemplars |
|---|---|
| Structure | Section organization, typical length, appendix usage |
| Evidence depth | Real data vs. simulation; dataset scale (links, intersections, days, trajectories); field validation presence |
| Experiment scale | Number of scenarios/demand levels/seeds; sensitivity analyses included |
| Baselines | Which baselines the exemplars compare against — the de-facto standard for the subfield |
| Metrics | Which system-level metrics are expected (delay, VKT, TTC, MFD-based measures...) |
| Figures/tables | Standard of visualization and result presentation |
| Related work | Breadth and venues of citations |
| Reproducibility | Data/code availability practices in the exemplars |

## Step 3 — Use the profile in the review

- Compare the manuscript against the exemplar-derived bar **dimension by dimension**, explicitly: "The manuscript's validation uses a single 4×4 synthetic grid; the exemplar papers [A], [B] validate on real networks of 100+ intersections with field-measured demand — this is the gap Reviewer 2 scores."
- Calibrate scores: if the manuscript matches exemplar evidence depth, scores in the 7–8 range are defensible; if clearly below, cap accordingly and state why.
- Do NOT penalize the manuscript for not being the exemplar papers (different contributions are legitimate). Penalize only gaps in evidence standard.
- If exemplars are NOT from TR-C or clearly weaker than TR-C standard, say so and fall back to `journal-profile.md` as the bar, noting the exemplars' limitations.

## Step 4 — Report the calibration

Include a short "校准基准 / Calibration Baseline" section in the final report (Section 0.5) listing: exemplars used, the extracted bar per dimension, and how the manuscript compares. If no exemplars were uploaded, state that calibration used the built-in TR-C profile and skip this section.

## Guardrails

- Treat exemplars as evidence of *standards*, never as ground truth of *correctness*.
- If an exemplar PDF is unreadable or partially extracted, say so and calibrate on what is legible.
- Never fabricate details of an exemplar (page counts, datasets, results). If unreadable → omit from calibration.
