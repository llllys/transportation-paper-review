# TR-C Domain Checklist / 领域专项核查清单

Match the manuscript's subfield(s) and apply the corresponding checks. Multiple sections may apply. This list encodes what experienced TR-C referees actually probe; it is not exhaustive — add paper-specific checks.

## 0. All papers

- [ ] Transportation-consequence test passed (system-level metrics reported, not only algorithm metrics)
- [ ] Problem motivation grounded in a real transportation need, not a method looking for an application
- [ ] Assumptions stated explicitly; realism of each assumption discussed (demand, information availability, compliance, communication)
- [ ] Notation consistent; units correct (veh/h vs veh/s, km/h vs m/s — a classic error source)
- [ ] Limitations section honest and specific
- [ ] Data/code availability statement present with a usable repository pointer
- [ ] References cover the transportation literature (TR-C/TR-B/TRR/T-ITS/ITSC), not only CS venues

## 1. Traffic state estimation & prediction (speed/flow/demand/travel time)

- [ ] Real-world datasets (PeMS, METR-LA, PEMS-BAY, NGSIM, HighD, taxi GPS, smart card) or justified synthetic data; if synthetic only → Major at best
- [ ] Baselines include domain standards: HA, ARIMA/SARIMA, SVR, FNN, and recent SOTA (ST-GCN family, DCRNN, Graph WaveNet, ASTGNN, STTN, or newer); not only weak classical baselines
- [ ] Metrics beyond RMSE/MAE/MAPE where relevant: breakdown by congestion regime, peak vs off-peak, horizon-wise degradation
- [ ] Missing-data / sensor-failure robustness tested
- [ ] Multi-horizon evaluation (15/30/60 min), not single-step
- [ ] Statistical significance across runs/seeds; improvement magnitude vs. practical significance (is a 1.5% MAPE reduction operationally meaningful?)
- [ ] Spatial transferability: trained on one city/network, tested on another?
- [ ] Physical consistency: does the model respect flow conservation / fundamental diagram constraints where it should?

## 2. Traffic flow theory & car-following / lane-changing models

- [ ] Model calibrated AND validated on trajectory data (NGSIM, HighD, pNEUMA, Zen Traffic Data), not only simulated truth
- [ ] Stability analysis: local and string stability, conditions derived, not just claimed
- [ ] Fundamental-diagram consistency (macroscopic implications of microscopic model)
- [ ] Comparison against standard models (IDM, Gipps, OVM, Wiedemann; MOBIL for lane changing)
- [ ] Parameter identifiability and sensitivity; calibration method described (objective, algorithm, goodness-of-fit)
- [ ] Heterogeneity and human factors considered where relevant

## 3. Traffic signal control & intersection/network management

- [ ] Baselines: fixed-time (Webster), actuated, SCOOT/SCATS-like where relevant, max-pressure, and recent RL/optimization SOTA (IntelliLight, PressLight, CoLight, MPLight, Advanced-MP...)
- [ ] Network realism: single intersection → arterial → grid/real network (Jinan, Hangzhou, Manhattan benchmarks); scalability claims match testbed size
- [ ] Demand scenarios: multiple demand levels, turning ratios, peak patterns, spillback/oversaturation included
- [ ] Metrics: delay, queue length, throughput, stops, travel time distribution (not just average); fairness across movements where relevant
- [ ] Simulator settings reported (SUMO/CityFlow/VISSIM version, step length, warm-up, seeds, number of replications)
- [ ] Yellow/all-red, safety constraints, pedestrian phases treated or explicitly excluded
- [ ] RL specifics: state/action/reward definitions justified, training curves shown, variance across seeds, comparison against non-learning control

## 4. Connected & autonomous vehicles (CAV) and cooperative control

- [ ] Penetration-rate analysis (MPR sweep incl. low MPR), mixed traffic with realistic human-driver models
- [ ] Communication imperfections: latency, packet loss, range limits — or explicit idealization with justification
- [ ] Safety evaluation: surrogate safety measures (TTC, PET, DRAC), conflict rates, not only efficiency
- [ ] String stability / platoon stability analysis for platooning and cooperative control
- [ ] Baselines: human-driven benchmark (IDM/MOBIL-calibrated), existing control (e.g., ACC models, PATH lab benchmarks)
- [ ] Comfort metrics (jerk, acceleration variance) when claiming comfort
- [ ] Energy/emissions model validity (CMEM, MOVES, VT-Micro) when claiming environmental benefits
- [ ] Failure/degraded-mode behavior discussed

## 5. Shared mobility, ride-hailing, MaaS, on-demand transit

- [ ] Real or realistically synthesized demand (NYC TLC, DiDi GAIA, smart-card, survey data); demand elasticity considered
- [ ] Matching/routing algorithm complexity and runtime at city scale reported
- [ ] Supply-side behavior modeled (driver repositioning, acceptance, working-hour heterogeneity) or acknowledged
- [ ] System metrics: empty miles/VKT, waiting time, service rate, deadheading, platform profit vs social welfare trade-off
- [ ] Equity/distributional effects where claims touch accessibility
- [ ] Comparison against published benchmarks on the same datasets where available

## 6. Network modeling, MFD, and large-scale control

- [ ] MFD existence and well-definedness justified for the studied network (scatter, hysteresis)
- [ ] Perimeter control / routing baselines (e.g., PI control, MPC variants) included
- [ ] Heterogeneity treatment (regional partitioning method validated)
- [ ] Route choice / user equilibrium consistency when control interacts with assignment
- [ ] Sensitivity to demand pattern, incident scenarios, turning fraction uncertainty

## 7. Data, sensing, and mobility big data

- [ ] Sensor/data provenance, sampling rate, penetration/coverage bias quantified
- [ ] Ground truth construction described; label quality discussed
- [ ] Privacy/ethics for trajectory and personal mobility data (anonymization, IRB/consent where human subjects)
- [ ] Dataset-release contribution: if the paper claims a data contribution, the dataset must actually be accessible (link, license, documentation) — TR-C's open-science emphasis makes this a scored item
- [ ] Data leakage check: train/test separation across space and time, no feature peeking

## 8. Surveys & reviews

- [ ] Search protocol transparent (databases, queries, date range, inclusion criteria) — PRISMA-style preferred
- [ ] Taxonomy adds structure beyond listing; gaps and open problems identified
- [ ] Coverage of both transportation and CS literature; recent (last 3 years) coverage adequate
- [ ] Comparative tables factual and checkable

## 9. Writing, structure & compliance (Reviewer-agnostic, always apply)

- [ ] Abstract claims ⊆ demonstrated results; every quantitative claim in abstract traceable to a table/figure
- [ ] Figures: legible axis labels/units, error bars where applicable, no misleading scales, colorblind-safe preferred
- [ ] AI-writing patterns flagged: empty transitions ("firstly/secondly/finally" chains), overclaiming adjectives without evidence ("novel", "superior", "robust" unsupported), coined unnecessary terminology, redundant restatement
- [ ] Generative-AI disclosure present if applicable (Elsevier policy)
- [ ] CRediT, competing interests, data availability statements present
- [ ] Reference formatting consistent (Elsevier numbered or author-year per guide)
