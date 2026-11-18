# RHEOA Supporting Data

Version: `data-20261118`. This is a private, version-controlled data archive during manuscript revision. Its existence does not imply public access. The accompanying ZIP can be shared directly with an authorized reviewer without granting GitHub access.

The 2026-11-18 revision maps the data to main Figs. 1–8 and supplementary Figs. S1–S6. S17 records terminal-refinement batch caps of 13 for Wuhan and 21 for Changsha and Chongqing. Tables S1–S33 and Texts S1–S9 retain their numbering.

The archive supports the study of repair-guided human evolutionary optimization (RHEOA) for quarterly, multi-source urban water allocation, with problem-specific Net3 pump-scheduling and Hanoi pipe-sizing extensions. It contains saved numerical results and parameter records, not an executable optimization-software release. No new optimization or hydraulic simulation was performed to prepare this release.

## Contents

| Location | Contents |
|---|---|
| `data/Supporting_Data_S1_case_inputs.json` | City inputs, regional mappings, source records and input checks |
| `data/Supporting_Data_S2_factor_structure.json` | The 73-factor register, graph, structural scores and sensitivity records |
| `data/Supporting_Data_S3_city_runs.csv` | 1,120 formal runs: 14 methods, four city-year cases, 20 runs each |
| `data/Supporting_Data_S4_city_tests.csv` | 234 saved method-metric statistical comparisons |
| `data/Supporting_Data_S5_control_runs.csv` | 280 shared-interface runs, each recorded at core and final stages (560 rows) |
| `data/Supporting_Data_S6_control_tests.csv` | 24 registered paired component comparisons |
| `data/Supporting_Data_S7_checkpoints.csv` | 2,240 saved search checkpoints |
| `data/Supporting_Data_S8_inner_diagnostics.csv` | 280 run-level inner-repair diagnostic records |
| `data/Supporting_Data_S9_representatives.csv` | 480 representative selections, including 160 RHEOA selections |
| `data/Supporting_Data_S10_quarterly_allocations.csv` | 5,760 quarter-region records for those selections |
| `data/Supporting_Data_S11_sensitivity.json` | Historical coefficient, engineering, threshold and aggregation analyses |
| `data/Supporting_Data_S12_supply_bounds.csv` | 12 optimistic supply-bound records, including baseline and pressure cases |
| `data/Supporting_Data_S13_network_runs.csv` | 440 formal network runs across three separate comparison batches |
| `data/Supporting_Data_S14_network_tests.csv` | 38 paired network comparisons |
| `data/Supporting_Data_S15_network_replay.csv` | 15,840 previously saved cache-disabled replay records |
| `data/Supporting_Data_S16_component_effect_intervals.csv` | 24 paired-bootstrap effect estimates for Fig. 5b |
| `data/Supporting_Data_S17_complete_settings_and_table_records.json` | Complete settings and archived table records; historical table labels are retained as provenance |
| `figure_data/Fig7_solution_records.csv` | 1,440 plotted RHEOA solutions, checked against the formal run JSON files |
| `figure_data/Fig7_feasibility_summary.csv` | Per-network pressure limits and example-run selections |
| `DATA_DICTIONARY.md` | Units, identifiers, stages, missing values and configuration mappings |
| `MANUSCRIPT_MAP.md` | Current figure/table to data-file map |
| `audit/verification_20261118.json` | Current comparison with the formal inputs, outputs, effect intervals, archive tables and network front records |
| `audit/verification_20261102.json` | Verification results recorded on 2026-11-02 |
| `audit/verification_20261027.json` | Historical verification record, preserved with its original date and scope |
| `manifest.csv` | File sizes and SHA-256 checksums for the data and audit files |
| `RHEOA_Supporting_Data.zip` | Portable copy of the data, documentation and verification records |

S1–S16 and the numerical figure records match the previous release byte for byte. The water-network plots in Fig. 8 use the original `Fig7_*.csv` filenames. The November 18 checks compare those 1,440 plotted solutions with the saved formal fronts. S17 retains the original table records and separately identifies the batch cap for each allocation case.

## Correct interpretation

An independent seed run is the statistical unit. Core/final stages, checkpoints, multiple representatives and individual solutions from the same run are not independent experimental replicates. Blank quality values indicate that the feasible-front metric is undefined; they do not mean zero performance.

HV normalization and IGD+ reference fronts are specific to each case and experiment. The main comparison, shared-interface controls and network batches must not be pooled or compared by their absolute indicator values. Feasible fractions describe the native returned population before common-cardinality quality-set reduction. The quality cap is 36 points, not necessarily the native population size.

The current allocation study uses the common fairness cap of 0.21. Historical analyses in S11 retain their earlier algorithm versions, aggregation choices and thresholds, including the 0.36 cap in some Wuhan 2025 tests. These records are not substitutes for the current formal comparison.

## Provenance and reproducibility

City statistics originate from the Wuhan, Changsha, Hunan and Chongqing sources identified in S1 and in the manuscript references. Reported statistics, derived model inputs and assumed management settings remain distinct. The Wuhan transfer category is a partition of reported surface-water supply, not an independently added supply total. Source paths in JSON identify records in the authors' research archive; they are provenance identifiers, not files promised to be present in this repository.

This release permits inspection and recomputation of the supplied summaries, paired effects and plotted records. It does not contain the complete frozen MATLAB/PlatEMO implementations, EPANET dependencies or every native run file. Re-running the optimizers from scratch requires a separate software release. The saved hydraulic checks are verification evidence from the formal experiments, not a new hydraulic replay performed for this deposit.

## Rights and access

Author-created experimental outputs and documentation are licensed under **CC BY 4.0**; see `LICENSE` and `RIGHTS.md`. Third-party inputs and source materials retain their original rights and attribution requirements. No unpublished manuscript, reviewer comments, credentials or personal machine paths are included.

The repository remains private until the owner explicitly changes its visibility. No public DOI or public-access claim is made for this revision-stage archive. See `CITATION.cff` for dataset citation metadata.
