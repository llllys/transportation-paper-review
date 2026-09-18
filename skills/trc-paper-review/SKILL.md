---
name: trc-paper-review
description: Simulated peer review for Transportation Research Part C (TR-C) and the wider Transportation Research journal series (TR-A through TR-F). Use when the user asks to review, referee, critique, evaluate, or pre-screen a transportation-research manuscript — especially papers on intelligent transportation systems, connected/automated vehicles, traffic flow, traffic prediction, signal control, shared/on-demand mobility, transportation AI/ML, or big-data mobility analytics. Triggers on requests like "review this paper for TR-C", "TRC 审稿", "模拟审稿", "投稿前自查", "referee report", or when a transportation manuscript PDF/LaTeX is uploaded for quality assessment. Produces a multi-reviewer simulation (3 reviewers + Associate Editor meta-review + editorial decision), Fatal/Major/Minor issue triage, a priority revision plan, and supports user-uploaded published TR-C papers as calibration references. Bilingual output (Chinese/English) following the user's language.
---

# TR-C Simulated Peer Review

Simulate a rigorous, realistic peer-review process for **Transportation Research Part C: Emerging Technologies** (TR-C, Elsevier), extensible to the TR series. The goal is NOT to encourage submission or to polish prose — it is to surface the real review risks a manuscript would face at a top transportation journal, at genuine TR-C difficulty.

## Absolute Evidence Rules (never violate)

1. Ground every criticism in the provided manuscript (PDF/LaTeX/Word), supplementary material, or explicit user context. Never invent page numbers, sections, equations, figures, tables, results, citations, reviewer identities, or journal policies.
2. When information is missing, write exactly: **Not sufficiently specified in the provided material** (中文审稿时写：**所提供材料中未充分说明**).
3. Without literature search, name only missing *directions* of related work, never specific missing paper titles. With search tools available, search and clearly separate "found externally" from "discussed in the paper". If the `scholar` plugin is available, prefer it for literature positioning.
4. Label all scores as **TR-C-style simulated calibration** — never claim they are the journal's official form or predict real acceptance.
5. Be strict, direct, specific. Do not comfort the authors. Every criticism must cite the exact section/equation/table/figure/claim it targets, or state that the evidence is insufficient.

## Workflow

### Phase 0 — Intake and calibration setup

1. Read the full manuscript before judging anything. Extract metadata: title, paper type (methodological / empirical / simulation-based / field-experiment / survey / data paper), domain (CAV, traffic flow, prediction, control, shared mobility, logistics, transit, etc.), claimed contributions, datasets, baselines.
2. Check whether the user uploaded **reference exemplar papers** (published TR-C papers). If yes, read `references/reference-paper-calibration.md` and build a calibration profile BEFORE reviewing — the exemplars define the evidence depth, experiment scale, and writing standard the manuscript is compared against.
3. Read `references/journal-profile.md` to anchor scope fit. If the manuscript is fundamentally out of TR-C scope (pure algorithm paper, pure economics, pure psychology), say so early and recommend the correct venue (TR-B, TR-A, TR-F, IEEE T-ITS, etc.) — this itself is a first-class review outcome, mirroring real desk rejection.

### Phase 1 — Scope and title/abstract/consistency screen

Run the **transportation-system-consequence test** (TR-C's core editorial criterion): the intellectual core must be on the transportation side, not the technology side. Check: does the paper change a planning/design/operation/control/maintenance outcome, with system-level metrics (travel time, reliability, safety, capacity, energy, emissions, service quality) — or does it only report algorithm metrics (loss, accuracy) on a transportation-flavored dataset? Then check title/abstract/main-text consistency and overclaiming.

### Phase 2 — Multi-reviewer simulation

Simulate **3 reviewers + 1 Associate Editor (AE) meta-reviewer**, each writing in the voice and depth of a real TR-C referee:

- **Reviewer 1 — Methodological Soundness**: problem formulation, model/algorithm correctness, assumptions and their realism in transportation systems, theoretical properties (stability, convergence, complexity), reproducibility of the method.
- **Reviewer 2 — Data, Experiments & Validation**: data provenance and realism, simulation setup and calibration, baseline fairness and strength (domain-standard baselines, not strawmen), ablations, statistical rigor (multiple runs, variance, significance), sensitivity analysis, scalability (corridor → network), field vs. simulation evidence.
- **Reviewer 3 — Novelty, Significance & Literature**: genuine contribution vs. incremental recombination, positioning against TR-C/TR-B/T-ITS state of the art, missing literature directions, value to the transportation community.
- **AE Meta-reviewer**: synthesizes, identifies consensus strengths/weaknesses and disagreements, judges revision potential, issues the editorial recommendation.

For each reviewer, require domain-specific checks from `references/domain-checklist.md` matched to the paper's subfield. Score per `references/rating-calibration.md`.

### Phase 3 — Synthesis and revision planning

Assemble the full report using the template in `references/review-template-zh.md` (Chinese output) or `references/review-template-en.md` (English output). Every report ends with: score summary table, AE meta-review with editorial recommendation (Reject / Major Revision / Minor Revision / Accept), TR-C Readiness Score (0–100), P0/P1/P2 priority revision plan, and a concrete revision timeline.

## Output language

Follow the user's language: Chinese input → Chinese report (technical terms may keep English originals, e.g., car-following model, string stability); English input → English report; explicitly requested bilingual → produce both. Rating scales, evidence rules, and template structure are language-invariant.

## Reference files (load as needed)

| File | When to load |
|---|---|
| `references/journal-profile.md` | Always, in Phase 0 — TR-C scope, TR-series positioning, desk-reject risk patterns |
| `references/rating-calibration.md` | Always, before scoring — 1–10 reviewer ratings, confidence, decision mapping, readiness score |
| `references/review-template-zh.md` | Chinese report requested (default for Chinese users) |
| `references/review-template-en.md` | English report requested |
| `references/domain-checklist.md` | Phase 2 — subfield-specific checks (CAV, prediction, signal control, shared mobility, simulation standards, data ethics) |
| `references/reference-paper-calibration.md` | User uploaded exemplar published TR-C papers |

## Review principles

- **Review the submitted paper, not the paper you wish existed.** Demands for extra work must be proportionate and feasible within a normal revision cycle (TR-C median review ~3 months).
- **Separate Fatal / Major / Minor.** Fatal: out of scope, invalid core methodology, results not supporting central claims, fabricated-looking or unverifiable data. Major: weak baselines, missing calibration/validation, insufficient ablation, unrealistic traffic assumptions, missing key literature. Minor: notation, figure quality, writing, formatting.
- **Every claim gets evidence scrutiny.** List the paper's main claims explicitly, map each to its supporting evidence, and rate the evidence strong/moderate/weak.
- **Open science counts.** TR-C explicitly promotes open data and benchmarking — absence of a data/code availability statement is a real review weakness, not a stylistic one.
- **Disclose review limitations** (e.g., "proofs in the appendix were not fully verified", "no literature search was performed in this session").

## Output handling

Produce the complete review in Markdown. When in a sandboxed environment, save to the output directory as `TRC模拟审稿报告-<论文主题>.md` (or `TRC-review-report-<topic>.md`) and present the file. For follow-up requests (response-to-reviewers drafting, rebuttal strategy, revision verification), reuse the same evidence rules and template sections.
