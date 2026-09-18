# Rating Calibration / 评分校准

All scores are **TR-C-style simulated calibration** — an internal instrument for this review, not the journal's official form and not an acceptance prediction.

## Per-reviewer rating (1–10)

| Score | Meaning | Anchor at TR-C level |
|---|---|---|
| 10 | Landmark | Would redefine a subfield (e.g., a new fundamental traffic theory with field validation). Almost never given. |
| 9 | Exceptional | Top few % of TR-C papers: novel problem + rigorous method + field/large-scale validation + open data. |
| 8 | Strong accept | Clear novelty, sound method, thorough experiments incl. realistic networks/data and strong baselines; minor gaps only. |
| 7 | Accept | Solid contribution; some weaknesses (e.g., simulation-only validation done well) but publishable with minor revision. |
| 6 | Marginally above threshold | Contribution real but evidence thin in 1–2 dimensions (e.g., missing sensitivity analysis, baselines incomplete). Major revision candidate, lean positive. |
| 5 | Borderline | Roughly equal strengths and weaknesses; the revision burden is heavy but a path exists. |
| 4 | Marginally below threshold | Significant methodological or experimental gaps; incremental feel. Major revision candidate, lean negative. |
| 3 | Clear rejection | Core claims unsupported; fatal scope or validity problems; revision cannot fix within one cycle. |
| 2 | Strong rejection | Fundamental flaws (wrong model, invalid data, fatal overclaiming). |
| 1 | Trivial or wrong | No contribution or incorrect work. |

**Calibration discipline:**
- 8+ requires ALL of: genuine novelty, sound methodology, convincing system-level evaluation, reproducibility package, clean writing. Be conservative — at TR-C level most published papers sit at 6.5–7.5 on this scale.
- A paper strong on method but simulation-only, toy-network, no calibration tops out around 6.
- A paper failing the transportation-consequence test tops out at 4 regardless of technical quality.
- Never give the same score to all reviewers by default; independent reviewers genuinely disagree. Score dispersion must be justified in each reviewer's "Score Justification".

## Confidence (1–5)

- 5 = certain, expert-level familiarity with this exact subfield
- 4 = confident, minor uncertainty
- 3 = fairly confident
- 2 = willing to defend, but likely misunderstood central parts
- 1 = educated guess

Use 2–3 honestly when the paper is outside the simulated reviewer's deepest expertise or material is incomplete. Confidence 5 for every reviewer signals a lazy simulation.

## Editorial recommendation mapping (AE)

| Recommendation | Typical score pattern |
|---|---|
| Accept (rare in round 1) | All ≥ 8, no Major issues |
| Minor Revision | Average ≥ 6.5, no Fatal, few Major, no reviewer ≤ 4 |
| Major Revision | Average 4.5–6.5, no Fatal OR Fatal plausibly fixable in one cycle, at least one champion reviewer |
| Reject | Any unfixable Fatal, or average < 4.5, or no reviewer ≥ 6 |

The AE may deviate from the numeric mapping when reviewer expertise weights differ (e.g., the methods expert's Fatal finding outweighs two lenient scores). Explain any such deviation.

## TR-C Readiness Score (0–100)

Holistic editorial-readiness instrument, reported once at the end:

- 85–100: competitive at TR-C now; expect minor revision at worst
- 75–84: plausible submission; targeted fixes needed (1–2 Major issues)
- 65–74: borderline; structural weaknesses likely to trigger major revision or reject; fix before submitting
- 50–64: likely rejection in current form; substantial additional work (experiments, repositioning)
- < 50: do not submit to TR-C; reconsider venue or redesign the study

Derive it from the reviewer ratings and the Fatal/Major/Minor ledger, and state the derivation in one or two sentences. Do not present it as a probability of acceptance.
