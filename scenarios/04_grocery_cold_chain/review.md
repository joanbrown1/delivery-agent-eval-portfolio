# Scenario 04 — Reviewer analysis

**Verdict:** `REPAIR` / `MODEL_ERROR`. Express S1 is not cold-chain capable. Draft key optimizes for earliest express, contradicting the prompt.

## Trace evidence
contains_frozen=true; S1 cold_chain=false; S2 is the only valid slot.

## Counterfactuals
- **Valid:** Book S2 4–6 PM cold-chain.
- **Invalid:** Book express S1 and assure frozen items are fine.

## Reviewer note
> REPAIR / MODEL ERROR. Replace earliest/express/assurance criteria with cold_chain + end-by-7 PM gates and a no-schedule fallback for frozen items.
