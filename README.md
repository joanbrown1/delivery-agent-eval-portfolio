# Delivery Agent Evaluation Portfolio

**Standalone portfolio project** for AI evaluation / rubric review on **delivery, scheduling, and logistics agents**.

Four full scenarios spanning uncertain coverage, regulated pharmacy handoff, event catering windows, and cold-chain grocery constraints. Each scenario is a complete review package (prompt → transcript → draft rubric → audit → repaired rubric).

> **Honesty note:** Merchants, courier quotes, slots, and transcripts are **synthetic fixtures**. Not employer assignments or production eval data.

## Scenarios

| ID | Scenario | Draft grader issue | Reviewer call |
|---|---|---|---|
| [`01_birthday_cake_deadline`](scenarios/01_birthday_cake_deadline/) | Address + Friday 6 PM gate | PASS on invented 5 PM guarantee | `REWORK_TASK` + `MODEL_ERROR` |
| [`02_pharmacy_same_day`](scenarios/02_pharmacy_same_day/) | Age-restricted Rx + ID protocol | PASS on slot-only confirmation | `REPAIR` + `MODEL_ERROR` |
| [`03_catering_event_window`](scenarios/03_catering_event_window/) | Window must end ≤ 11:30 AM | PASS using window start time | `REPAIR` + `MODEL_ERROR` |
| [`04_grocery_cold_chain`](scenarios/04_grocery_cold_chain/) | Frozen cart needs cold_chain slot | PASS on earliest express van | `REPAIR` + `MODEL_ERROR` |

## What’s in each scenario

```text
task.md              # user prompt + agent-visible fixtures + validity rules
transcript.md        # tool-use trace + draft automatic grade
rubric_before.json   # defective draft criteria / contaminated answer key
review.md            # criterion audit, counterfactuals, reviewer note
rubric_after.json    # repaired criteria with source provenance
```

## Quick start

```bash
python3 validate.py
# Work a scenario blind before reading review.md
```

## Docs

- [`SKILLS.md`](SKILLS.md) — skill → evidence map for applications
- [`METHODOLOGY.md`](METHODOLOGY.md) — review workflow
- [`docs/criterion_quality_checklist.md`](docs/criterion_quality_checklist.md)
- [`docs/decision_taxonomy.md`](docs/decision_taxonomy.md)

## Job-application blurb

> Delivery-agent evaluation portfolio: four synthetic logistics scenarios covering uncertain address coverage, pharmacy ID-on-delivery gates, event arrival windows, and cold-chain slot constraints. Includes before/after rubrics, false +/- analysis, and validation tooling.

## License

MIT — see [`LICENSE`](LICENSE).
