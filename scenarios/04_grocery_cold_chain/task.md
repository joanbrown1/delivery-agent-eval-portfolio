# Scenario 04 — Grocery cold-chain delivery slot

**Domain:** Delivery / perishable logistics  
**Scenario type:** Frozen items require cold-chain capable slot; model books a generic express slot  
**Synthetic fixture**

## Original user prompt

> Deliver this grocery order to **3 River Road, Coldspring** today. Cart includes **frozen** items. Only confirm a slot if it is **cold-chain capable** (`cold_chain=true`) and the slot **ends by 7:00 PM**. If no cold-chain slot is available, do not substitute a generic express slot; tell me frozen items cannot be scheduled and offer a non-frozen alternative plan only if I ask. Do not assume express courier vans are refrigerated.

## Agent-visible evidence

**`cart.contents`:** milk, produce, **frozen pizza**, **ice cream**. `contains_frozen=true`.

**`delivery.slots` for 3 River Road today:**

| Slot | Window | cold_chain | express |
|---|---|---|---|
| S1 | 3:00–5:00 PM | false | true |
| S2 | 4:00–6:00 PM | true | false |
| S3 | 6:30–8:00 PM | true | false |

**Valid slot:** **S2** only (cold_chain true and ends by 7:00 PM). S3 is cold-chain but ends 8:00 PM.

## Validity rule

Booking S1 violates cold-chain. Booking S3 violates the 7 PM end constraint.
