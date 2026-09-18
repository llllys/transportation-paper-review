# TR-C Journal Profile / TR-C 期刊档案

## Scope (official, paraphrased from Elsevier Guide for Authors)

TR-C publishes high-quality scholarly research on the **development, applications, and implications of emerging technologies for transportation systems**. The interest is **not in the individual technologies per se**, but in their ultimate implications for the planning, design, operation, control, maintenance and rehabilitation of transportation systems, services and components. **The intellectual core of the journal is on the transportation side, not on the technology side.** Quantitative methods from operations research, control systems, complex networks, computer science and AI are encouraged as tools, not as the contribution itself.

Performance dimensions of interest: monitoring, efficiency, safety, reliability, resource consumption, environment.

Welcome areas: multimodal/intermodal transportation; on-demand transport; intelligent transportation systems; traffic and demand management; real-time operations; connected and autonomous vehicles; logistics; railways; resource and infrastructure management; aviation; pedestrians and soft modes.

**Open science emphasis**: TR-C explicitly promotes open-science initiatives and the opening of large-scale datasets supporting transferability and benchmarking.

## Practical facts

- Publisher: Elsevier; ISSN 0968-090X. Editor-in-Chief (as of 2026): Nikolas Geroliminis (EPFL).
- Impact factor ≈ 8; consistently top-2 transportation journal by citations. Q1, CAS 一区.
- Typical pipeline (journal-published medians): first decision in days (desk screen), post-review decision ≈ 3 months, acceptance ≈ 8 months. Reviewers are typically 2–4 domain experts plus an Associate Editor.
- Decision scale in Editorial Manager: **Accept / Minor Revision / Major Revision / Reject** (Reject-and-resubmit is effectively a heavy Major Revision signal in reviewer comments).
- Submission requirements relevant to review: structured abstract, highlights (3–5 bullets ≤ 85 chars), graphical abstract, CRediT statement, competing-interests declaration, data/code availability statement, ethics statement for human-subjects work, generative-AI-in-writing disclosure.

## The desk-reject / early-reject risk patterns (highest-value checks)

Ranked by how often they kill real submissions:

1. **Technology demo without transportation consequence** — a generic ML/control/optimization method tested on a transportation-flavored dataset, where the only metrics are algorithmic (MSE, accuracy, reward) and no system-level outcome (delay, throughput, reliability, safety surrogate, energy) is demonstrated. The #1 TR-C failure mode.
2. **Unrealistic traffic assumptions** — toy networks (single intersection, single link) with claims of network-level impact; demand patterns invented without justification; no congestion regime coverage (free-flow only); no mixed-traffic / penetration-rate analysis for CAV papers.
3. **Uncalibrated simulation** — SUMO/VISSIM/Aimsun or custom simulator used with default parameters, no calibration or validation against field data, single random seed, no warm-up, no sensitivity analysis.
4. **Strawman baselines** — comparing a deep model only against ARIMA/HA, or a control method only against fixed-time signals, ignoring domain-standard and SOTA baselines (see `domain-checklist.md`).
5. **Incremental recombination** — existing method A + existing method B applied to scenario C, without a clear statement of what was technically hard or what transportation insight emerges.
6. **Missing literature positioning** — citing only CS venues (NeurIPS/ICLR/KDD) while ignoring the transportation literature (TR-C/TR-B/TRR/T-ITS/ITSC), or vice versa; missing the 2–3 most closely related papers.
7. **Claims exceeding evidence** — "general", "robust", "real-time", "scalable", "safe" in title/abstract without corresponding experiments.
8. **No reproducibility package** — no data availability statement, no code, proprietary data with no access path, insufficient hyperparameter/hardware reporting.
9. **Safety claims without safety metrics** — CAV papers claiming safety benefits using only efficiency metrics; no surrogate safety measures (TTC, PET, DRAC) or crash-risk analysis.
10. **Statistical weakness** — single-run results, no variance, no significance testing, improvements within noise.

## Positioning within the TR family (for scope-redirect advice)

| Journal | Core | Redirect here when… |
|---|---|---|
| TR-A: Policy and Practice | policy, planning, behavior-policy interface | contribution is policy analysis, not system technology |
| TR-B: Methodological | mathematical/analytical models, OR | contribution is primarily the math (theory, proofs, new algorithms for classic problems) with transportation as motivation |
| **TR-C: Emerging Technologies** | tech-driven system innovation | the default target for AI/ML/CAV/IoT/data-driven work **with demonstrated system consequence** |
| TR-D: Transport and Environment | emissions, environment | environmental outcome is the core claim |
| TR-E: Logistics | freight, logistics OR | freight/supply-chain core |
| TR-F: Traffic Psychology | human behavior, psychology | behavioral/acceptance study core |

Also consider (non-TR): IEEE T-ITS (vehicle-side/intelligent-vehicle systems emphasis), TRR (broader, lower bar), IEEE ITSC (conference), Networks and Spatial Economics, Transportation Science (heavier OR).

## What distinguishes a strong TR-C paper (positive calibration)

- A real transportation problem motivates everything; the method is a means.
- System-level evaluation on real or realistically-calibrated networks/data; public benchmarks where they exist (NGSIM, HighD, pNEUMA, PeMS, METR-LA/PEMS-BAY, TaxiBJ, NYC taxi, smart-card datasets, CityFlow/SUMO networks of real cities).
- Clear statement of assumptions and where they break; discussion of transferability and deployment constraints (communication loss, sensor noise, penetration rates, equity, privacy).
- Reproducibility: code + data + seeds; data availability statement with a real repository.
- Writing that respects the transportation community's vocabulary (demand, supply, MFD, string stability, spillback, queue discharge) rather than only ML vocabulary.
