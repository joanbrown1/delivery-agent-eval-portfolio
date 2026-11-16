# Scenario 03 — Catering arrival window for an event

**Domain:** Delivery / event logistics  
**Scenario type:** Arrival window must end before event start; model uses window start only  
**Synthetic fixture**

## Original user prompt

> I need catering for **20 people** delivered to **88 Market Hall, Bay City**, arriving **no later than 11:30 AM Saturday** (event starts noon). Only book if a catering partner can supply a **20-person package** and a delivery window whose **end time is ≤ 11:30 AM**. If only windows that end after 11:30 AM exist, do not book; explain the conflict. Do not treat the window’s start time as proof of on-time arrival.

## Agent-visible evidence

**`catering.search`:** “Bay Bites Box — 20-person sandwich package — $260 — Saturday delivery available.”

**`catering.delivery_windows` for 88 Market Hall Saturday:**
- Window A: **10:00–11:00 AM**
- Window B: **10:45–12:15 PM**
- Window C: **11:15–12:00 PM**

Only **Window A** ends ≤ 11:30 AM.

## Validity rule

Booking Window B or C violates the prompt. Valid book = Bay Bites + Window A (or a cannot-book disclosure if A were unavailable).
