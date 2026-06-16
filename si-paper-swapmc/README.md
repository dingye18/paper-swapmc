# Supporting Information for SwapMC Paper

This directory contains the supporting information (SI) data for the SwapMC paper, including free energy calculation results and simulation parameters.

## Directory Structure

### `schedule.json`

Lambda schedule used for the alchemical free energy calculations. Contains 16 lambda windows with parameters for charge (qA, qB) and van der Waals (vdwA, vdwB) scaling, along with REST2 (Replica Exchange with Solute Tempering) scaling factors.

### `sch8_abfe_swapmc/` and `sch8_abfe_no_swapmc/`

Absolute binding free energy (ABFE) results using the Schrodinger 8-target benchmark set, **with** and **without** SwapMC enhanced sampling, respectively.

**Target systems:** bace, cdk2, jnk1, mcl1, p38, ptp1b, thrombin, tyk2

Each target contains a `graph/` subdirectory with:
- `dG.csv` / `dG.png` — Predicted vs. experimental absolute binding free energies (dG)
- `dG_shifted.csv` / `dG_shifted.png` — Shifted dG values (offset-corrected)
- `stat.txt` — Summary statistics (R², RMSE, Kendall's tau)
- `stat_shifted.txt` — Statistics for offset-corrected predictions

### `watersets-swapmc/` and `watersets-noswapmc/`

Relative binding free energy (RBFE) results from the WaterSet benchmark, **with** and **without** SwapMC enhanced sampling, respectively.

**Target systems (with SwapMC):** brd41_ASH106, chk1, hsp90_kung, hsp90_wood, scytalone_dehy, taf12, throm, urokinase

**Target systems (without SwapMC):** brd4, chk1, hsp90_kung, hsp90_woodhead, scyt, taf12, throm, urokinase

Each target contains a `graph/` subdirectory with:
- `dG.csv` / `dG.png` — Predicted vs. experimental absolute free energies
- `ddG.csv` / `ddG.png` — Predicted vs. experimental relative binding free energies (ddG)
- `cycle_error.csv` — Thermodynamic cycle closure errors (cycle dG, std, and hysteresis)
- `stat.txt` — Summary statistics (R², RMSE, and optionally Kendall's tau)

## Data Format

### CSV files
- `dG.csv`: columns — `mol, dG_pred, std_dG_pred, dG_expt, std_dG_expt, has_expt, dG_diff`
- `ddG.csv`: columns — `mol1, mol2, ddG_pred, std_ddG_pred, ddG_expt, std_ddG_expt, has_expt, ddG_diff`
- `cycle_error.csv`: columns — `cycle, dG, std_dG, hysteresis`

### Statistics
- **R²** — Coefficient of determination
- **RMSE** — Root mean square error (kcal/mol)
- **Kendall's tau** — Rank correlation coefficient (reported in ABFE results)
