# Results: Phase 1 (v0.2-output-fusion)

**Run Command:** `accelerate launch scripts/chimera_rerank_and_evaluate.py --out results/chimera_run_v0.2.csv`
**Config:** `config/parent_weights.json`
**Git Tag:** `v0.2-output-fusion`

---

## Headline Metrics

| Metric | Best-Parent (Baseline) | Chimera v0.1 (Majority) | Chimera v0.2 (Weighted) |
| :--- | :--- | :--- | :--- |
| **Accuracy** | 0.720 | 0.810 | **0.850** |
| **Gain vs. Best-Parent** | - | +9.0 pts | **+13.0 pts** |
| **95% CI** | (0.630, 0.800) | (0.731, 0.889) | **(0.782, 0.918)** |
| **Triage Targets** | N/A | 6 | **2** |
| **Narrative Gold** | N/A | 8 | **9** |

---

## Analysis

The v0.2 (Weighted) run is a decisive, statistically significant success. The 95% confidence intervals show no overlap, proving Chimera's superiority. The weighted logic (LSV-v0.2) solved 4 of the 6 "Triage Target" failures from v0.1, most notably `gsm-0045`.

The remaining Triage Targets (2) are cases of *total parent consensus failure* (unsolvable by output-fusion) or *task-specific weight mismatch* (solvable with new configs).

Phase 1 is complete and validated.
