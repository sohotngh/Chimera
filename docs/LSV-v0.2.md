# Lightweight Symbolic Verifier (LSV-v0.2)

**Version:** 0.2
**Status:** Stable
**Parent:** LSV-v0.1
**Objective:** Introduce a meritocratic bias to the ensemble by weighting votes based on empirical parent-model reliability.

---

## 1. Core Logic Change (from v0.1)

LSV-v0.1 used a "1 model, 1 vote" majority-rules system. This was vulnerable to a "consensus of wrongness," where multiple low-reliability models could outvote a single high-reliability model.

LSV-v0.2 replaces this with a **Weighted Majority Vote**.

## 2. Methodology

### 2.1. Parent Reliability Weights

A new configuration file (`config/parent_weights.json`) stores the baseline empirical accuracy of each parent model on a given task (e.g., GSM8K).

*Example `parent_weights.json`:*
```json
{
  "phi": 0.68,
  "mistral": 0.71,
  "llama": 0.76
}
