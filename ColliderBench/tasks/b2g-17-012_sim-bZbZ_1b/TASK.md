> **Paper:** CMS-B2G-17-012
> **Centre-of-mass energy:** 13 TeV
> **Luminosity:** 35.9 fb⁻¹
> **Task type:** simulation
> **Signal benchmark:** `BB_bZbZ_1200`
> **Observable:** `S_T`
> **Signal region:** `1b` category (BB̄ search, Section 4)

### Task

Implement the search analysis described in **CMS-B2G-17-012** (arXiv:1812.09768) and use it to predict the binned differential signal yield in `S_T` for the benchmark point `BB_bZbZ_1200`, in the **`1b` event category** of the analysis's BB̄ search, with the Z → e⁺e⁻ and Z → μ⁺μ⁻ channels combined, normalized to 35.9 fb⁻¹ at √s = 13 TeV.

You should:

1. Generate `BB_bZbZ_1200` events using a matrix-element generator + parton shower + detector simulation chain of your choice.
2. Read the paper to determine the object identification, the event-selection requirements, the boosted-object taggers and the `1b` category definition of the BB̄ search. Apply them to your generated events.
3. Histogram the surviving events in `S_T` using the 16 bin edges already present in the `results/*.yaml` template (do not modify them).

### Definitions

- `S_T` — the scalar sum of `H_T`, `pT(Z)` and `pT_miss`, where `H_T` is the scalar sum of the transverse momenta of all selected AK4 jets and `pT(Z)` is the transverse momentum of the leptonic Z boson candidate.
- `BB_bZbZ_1200` — pair-produced vector-like bottom-partner quarks B at `m(B) = 1200 GeV`, each decaying via B → bZ (`B(B → bZ) = 100%`), with one Z boson decaying to e⁺e⁻ or μ⁺μ⁻ and the other decaying hadronically.
- `1b` category — events with N_b = 1 and no V, H or t candidates (N_V = N_H = N_t = 0), where N_b counts b-tagged AK4 jets and N_V, N_H and N_t count the V → qq, H → bb and t → bqq' candidates identified with the jet-substructure tagger on AK8 jets, using the BB̄-search working points.

### Output requirements

| Artifact | Purpose |
|---|---|
| `results/*.yaml` | Fill the `null` bin values with your predicted signal yields. |
| `analysis/*.py` | Event-selection code, runnable on your generated sample(s). |
| `data/*.root`, `sims/*.dat` | Selected-event files + generator / detector cards. |
| `report.md` | What you produced, the methodological choices you made, and where you deviated from the paper (if at all). |

### Important

> The goal is to *predict* the signal event distribution from your own simulation and analysis pipeline. Do not extract bin values from the paper's figures, tables, HEPData record, or elsewhere.
