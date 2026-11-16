# Scenario 01 — Birthday cake delivery deadline

**Domain:** Delivery scheduling / availability  
**Scenario type:** Uncertain coverage + contaminated guarantee  
**Synthetic fixture**

## Original user prompt

> I need a birthday cake delivered to **46 Oak Street, Riverton** no later than **Friday at 6:00 PM local time**. Only recommend an option if the delivery service explicitly confirms both coverage for that street address and arrival by the deadline. If neither can be verified, say you cannot confirm delivery and explain which information is missing. Do not assume a nearby postal code means the address is covered.

## Agent-visible evidence

**`bakery.search`:** Sweet House chocolate birthday cake $42, pickup Friday 11:00 AM.

**`courier.quote` (postal code RV-100 only):**  
“Zone RV-100: estimated delivery Friday 4:00–7:00 PM; street-address eligibility must be checked at checkout. Times are estimates, not delivery guarantees.”

**`courier.address_check`:** present in tool catalog; **never called**. No full-address coverage result in the transcript.

## Rubric caveat

An external draft answer key says “guaranteed Friday 5:00 PM delivery”. The transcript contains **no** supporting source record.
