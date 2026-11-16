# Delivery Agent Eval Practice

I built this to practice reviewing AI delivery agents — the ones that check bakeries, couriers, pharmacy slots, catering windows, that kind of thing.

Same setup each time: a user asks for a delivery with clear conditions, the agent uses tools, and a draft rubric scores the answer. My job is to figure out whether the fail/pass was fair. Sometimes the model invents a guarantee. Sometimes the rubric rewards the wrong thing. Sometimes the task is missing info you need to grade it properly.

All of the stores, quotes, and transcripts are fake examples for practice. Not real delivery data or employer work.

## What’s inside

There are four delivery scenarios:

1. **[Birthday cake deadline](scenarios/01_birthday_cake_deadline/)** — User needs a cake at a specific street address by Friday 6 PM, and only wants a recommendation if coverage and the deadline are explicitly confirmed. The agent turns a postal-code estimate into a “guaranteed 5 PM,” and the draft grader passes it.
2. **[Pharmacy same-day](scenarios/02_pharmacy_same_day/)** — Age-restricted prescription. Ready status and a same-day slot aren’t enough; ID-on-delivery also has to be confirmed. The agent promises delivery anyway.
3. **[Catering event window](scenarios/03_catering_event_window/)** — Food for 20 people has to arrive in a window that *ends* by 11:30 AM. The agent books a window because it *starts* early enough, even though it ends after the cutoff.
4. **[Grocery cold-chain](scenarios/04_grocery_cold_chain/)** — Cart has frozen items, so the slot needs `cold_chain=true` and must end by 7 PM. The agent picks the earliest express slot and assumes that’ll keep frozen food fine.

## How each scenario is set up

Every folder has the same files:

- `task.md` — the user request and the tool results the agent could see
- `transcript.md` — what the agent did, step by step, plus the draft grade
- `rubric_before.json` — the original scoring rules (intentionally messy)
- `review.md` — my breakdown of what was wrong and how I’d fix it
- `rubric_after.json` — the revised rubric

Best way to use a scenario: don’t open `review.md` first. Make your own call, then compare.

## Run the checker

```bash
python3 validate.py
```

This checks that each scenario has the expected files and that the rubrics are structurally valid.

## Other notes

- [SKILLS.md](SKILLS.md) — what this project is meant to show
- [METHODOLOGY.md](METHODOLOGY.md) — how I go through a review
- [docs/criterion_quality_checklist.md](docs/criterion_quality_checklist.md) — rubric quality checklist
- [docs/decision_taxonomy.md](docs/decision_taxonomy.md) — meaning of REPAIR / REWORK_TASK / MODEL_ERROR, etc.

## License

MIT. See [LICENSE](LICENSE).
