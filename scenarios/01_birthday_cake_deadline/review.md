# Scenario 01 — Reviewer analysis

**Verdict:** `REWORK_TASK` / `MODEL_ERROR`. Draft PASS is a false positive. Model invents a 5 PM guarantee; address check never ran.

## Trace evidence
T5 estimate 4–7 PM ≠ guarantee by 6 PM. T7 invents “guaranteed 5 PM.”

## Counterfactuals
- **Valid:** Cannot confirm delivery to 46 Oak Street by 6 PM; missing street-address verification and deadline guarantee.
- **Invalid:** Guaranteed 5 PM from postal estimate only.

## Reviewer note
> REWORK TASK / MODEL ERROR. Replace D3–D5 with source-grounded coverage, deadline, and uncertainty criteria. For confirmed-booking scoring, supply a real address_check result; do not fabricate it in the rubric.
