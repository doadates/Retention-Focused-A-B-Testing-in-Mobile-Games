# Retention-Focused A/B Testing: Gate Placement in Mobile Games

## Overview
This project analyzes the impact of a **game design change on player retention** using a controlled A/B test in a mobile game context.  
Specifically, it evaluates whether moving the **first gameplay gate** from level 30 to level 40 affects short-term and mid-term player retention.

The analysis follows a **product analytics mindset**, combining hypothesis testing with business-oriented interpretation rather than surface-level metric comparison.

---

## Business Context
Progression gates are commonly used in mobile games to regulate pacing and monetization.  
However, poorly timed gates can introduce friction that negatively impacts player experience and long-term retention.

**Key question:**  
> Does delaying the first progression gate improve onboarding without harming retention?

---

## Experiment Design

### Variants
- **gate_30** — First gate at level 30  
- **gate_40** — First gate at level 40  

### Metrics
- **Primary metric:** `retention_7` — player returned on day 7  
- **Secondary metric:** `retention_1` — player returned on day 1  

### Statistical Methods
- Two-proportion **Z-test**
- **Bootstrap confidence intervals** (95%)

---

## Key Results

### Short-Term Retention (Day 1)
- No statistically significant difference between **gate_30** and **gate_40**
- *p-value* ≈ **0.074**
- 95% confidence interval includes zero

**Interpretation**  
Players do not meaningfully interact with the gating mechanism on their first day.  
Early gameplay experience remains comparable across both variants.

---

### Mid-Term Retention (Day 7)
- Statistically significant difference detected
- *p-value* ≈ **0.0016**
- 95% confidence interval for *(gate_40 − gate_30)* is entirely negative

**Interpretation**  
Players exposed to the gate at level 40 are **less likely to return after one week** compared to those gated at level 30.

---

## Effect Size & Robustness
- Absolute difference in day-7 retention: **~0.3–1.3 percentage points**
- Effect direction is consistent across bootstrap resampling

Although the effect size is modest, it is **statistically robust** and unlikely to be driven by random variation.  
At scale, even small retention losses can translate into meaningful **LTV and revenue impact**.

---

## Behavioral Interpretation
- With **gate_30**, players encounter the core friction or monetization mechanic earlier and adapt to it sooner.
- With **gate_40**, players experience extended uninterrupted gameplay followed by a late introduction of friction.
- This delayed disruption likely increases frustration or perceived inconsistency, leading to higher mid-term drop-off.

**Delaying the gate does not improve onboarding and negatively impacts longer-term retention.**

---

## Business Recommendation
Based on retention metrics alone, **gate_30** is the preferred configuration.

The **gate_40** variant should only be considered if it demonstrates compensating improvements in other key metrics such as:
- Revenue per user
- Conversion rate
- Lifetime value (LTV)

A combined evaluation with monetization data is recommended before any rollout decision.

---

## Notes
- Extreme values in engagement metrics (e.g., `sum_gamerounds`) were inspected but not removed, as retention outcomes are binary and unaffected by continuous outliers.
- All statistical tests were conducted after verifying randomization, data integrity, and experiment assumptions.

