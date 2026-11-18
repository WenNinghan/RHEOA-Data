# Data dictionary

## Common conventions

- `case`: Wuhan 2024, Wuhan 2025, Changsha 2024 or Chongqing 2024.
- `case_id`: 1 = Wuhan 2024; 2 = Wuhan 2025 in the shared-interface records.
- `seed`: independent-run identifier. Match seeds only within the declared case and experiment.
- `FE`, `simulations`: actual evaluation/uncached hydraulic-solve counts, respectively. Runtime fields are in seconds.
- `hv`: hypervolume on the experiment-specific normalized scale; larger is better. HV is not divided by the reference-box volume and can exceed one.
- `igd`, `igd_plus`, `igd_plus_loso`: IGD+ on the documented experiment-specific scale; smaller is better. The declared leave-one-seed-out convention is given in Text S5.
- `feasible_fraction`, `population_feasible`: dimensionless fractions, not percentages. `any_feasible` and `all_feasible` are binary run indicators.
- Empty CSV fields indicate unavailable or undefined values. In particular, no feasible front means undefined HV and IGD+, not zero.
- Summary SDs use the sample definition. The manuscript tables may round values; retain unrounded data for calculations.

## Method identifiers

| Archived identifier | Current display meaning |
|---|---|
| `ProjectionAware_CFR_HEOA` | RHEOA in the main comparison |
| `HEOA Raw`, `HEOA_Raw` | Original HEOA |
| `H-Score` | RHEOA in the shared-interface experiment |
| `H-Outer` | HEOA: outer repair |
| `H-Write` | HEOA: writeback |
| `H-Fixed-Score` | HEOA: no learning |
| `D-Outer` | DE: outer repair |
| `D-Score` | DE: repaired scoring |
| `D-Write` | DE: writeback |
| `Frozen_RHEOA` in the Hanoi centered batch | Matched original-coordinate RHEOA control |

Archived aliases are retained to keep source records traceable. They do not introduce additional proposed algorithms. Historical names inside S11/S17 belong to the documented historical configuration, not automatically to the current RHEOA implementation.

## Controls and statistical files

S5 has `stage=core` and `stage=final`. Filter to `final` for the 280 final outputs. S7 `checkpoint_budget` is the requested checkpoint, and `source_FE` identifies the saved snapshot used; do not interpolate populations. S8 `changed_fraction` and `feasible_evaluation_fraction` describe inner candidates; `mean_normalized_displacement` is dimensionless. These are not final-population feasibility statistics.

In S4, S6, S14 and S16, `n` or `n_pairs` counts usable paired runs. `p_raw`/`p` are raw probabilities; `p_holm` is adjusted within the documented family. Positive `advantage`/`mean_advantage` favors the named focal method: focal minus comparator for HV, comparator minus focal for IGD+. S16 intervals are unadjusted pointwise paired-percentile 95% intervals from 10,000 resamples, not multiplicity-adjusted significance tests. `bootstrap_seed` is a deterministic random-number seed, not a date.

## Allocation records

S9/S10 volumes, shortage volumes and demands use **10^8 m^3**. Source fractions and `reliability` are dimensionless. `max_quarter_fairness_gap` is a dimensionless shortage-rate gap; multiply by 100 for percentage points. Cost and ecological-loss columns are model indices, not measured financial or ecological outcomes.

`selection=balanced` is the compromise solution; `endpoint_1`, `endpoint_2` and `endpoint_3` minimize the shortage/equity, cost and ecological-loss objectives, respectively. Different selections can identify the same point. S9 includes H-Score, H-Write and D-Score; only H-Score is RHEOA for the main representative-allocation analysis. S10 `region=1,2,3` denotes central urban, development-zone and new-urban groups in that order; `quarter=1,2,3,4` denotes Q1-Q4. Source fractions are computed within a selected solution before averaging across runs.

S12 `reliability_upper_bound` is an optimistic mathematical bound, not an observed allocation result. Its baseline records and pressure records must be distinguished by `scenario`, `case_id` and `include_fairness`.

## Network records and Fig. 8

S13-S15 contain three separate batches: `Net3`, `Hanoi original` and `Hanoi centered`. `arm` identifies a method within a batch. `configuration` gives the detailed configuration. Pressures are in metres; `cv` fields are normalized summed residuals under the problem-specific tolerances. `requests` may exceed `simulations` because cached requests do not consume a new hydraulic solve. `official_igd_plus` is an additional published-front readout where available and is not the same as the empirical leave-one-seed-out IGD+ column.

The `Fig7_*.csv` filenames preserve the numbering used when the water-network records were first exported. In `Fig7_solution_records.csv`, `objective_1` is energy in **kWh** for Net3 (divide by 1,000 for the MWh axis), and construction cost in **million USD** under the benchmark coefficient convention for Hanoi. `objective_2` is normalized pressure-service loss for Net3 and resilience loss for Hanoi. `minimum_pressure_m` is the minimum pressure for that solution, and `required_pressure_m` is 20 m or 30 m for the respective benchmark. The Net3 preferred service pressure is 35 m and is distinct from its 20 m feasibility limit.

Fig. 8 pools 20 runs of 36 solutions per problem. The example run is the run with HV closest to the case median, with the seed breaking ties. `point` is the one-based solution index within a saved run; `source_file` is a filename, not a public download URL. The plotted solutions are not a single pooled non-dominated front and are not 720 independent runs.
