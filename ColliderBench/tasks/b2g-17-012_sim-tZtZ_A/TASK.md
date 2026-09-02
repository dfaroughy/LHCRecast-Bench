> **Paper:** CMS-B2G-17-012
> **Centre-of-mass energy:** 13 TeV
> **Luminosity:** 35.9 fb⁻¹
> **Task type:** simulation
> **Signal benchmark:** `TT_tZtZ_1200`
> **Observable:** `S_T`
> **Signal region:** event group A (TT̄ search, Section 4)

### Task

Implement the search analysis described in **CMS-B2G-17-012** (arXiv:1812.09768) and use it to predict the binned differential signal yield in `S_T` for the benchmark point `TT_tZtZ_1200`, in the **event group A** of the analysis's TT̄ search, with the Z → e⁺e⁻ and Z → μ⁺μ⁻ channels combined, normalized to 35.9 fb⁻¹ at √s = 13 TeV.

You should:

1. Generate `TT_tZtZ_1200` events using a matrix-element generator + parton shower + detector simulation chain of your choice.
2. Read the paper to determine the object identification, the event-selection requirements, the boosted-object taggers and the event group A definition of the TT̄ search. Apply them to your generated events.
3. Histogram the surviving events in `S_T` using the 20 bin edges already present in the `results/*.yaml` template (do not modify them).

### Definitions

- `S_T` — the scalar sum of `H_T`, `pT(Z)` and `pT_miss`, where `H_T` is the scalar sum of the transverse momenta of all selected AK4 jets and `pT(Z)` is the transverse momentum of the leptonic Z boson candidate.
- `TT_tZtZ_1200` — pair-produced vector-like top-partner quarks T at `m(T) = 1200 GeV`, each decaying via T → tZ (`B(T → tZ) = 100%`), with one Z boson decaying to e⁺e⁻ or μ⁺μ⁻ and the remaining bosons and top quarks decaying hadronically.
- event group A — events with exactly one b-tagged AK4 jet (N_b = 1), at least one V → qq candidate (N_V ≥ 1) and at least one t → bqq' candidate (N_t ≥ 1), with any number of H → bb candidates (N_H = 0 or ≥ 1), where N_b counts b-tagged AK4 jets and N_V, N_H and N_t count the V → qq, H → bb and t → bqq' candidates identified with either the jet-substructure tagger (AK8 jets) or the resolved tagger (AK4 jets) of the TT̄ search.

### Output requirements

| Artifact | Purpose |
|---|---|
| `results/*.yaml` | Fill the `null` bin values with your predicted signal yields. |
| `analysis/*.py` | Event-selection code, runnable on your generated sample(s). |
| `data/*.root`, `sims/*.dat` | Selected-event files + generator / detector cards. |
| `report.md` | What you produced, the methodological choices you made, and where you deviated from the paper (if at all). |

### Important

> The goal is to *predict* the signal event distribution from your own simulation and analysis pipeline. Do not extract bin values from the paper's figures, tables, HEPData record, or elsewhere.
