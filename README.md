A/B Testing: Gate Placement and Player Retention
Overview

This project analyzes an A/B test conducted in a mobile game to evaluate whether moving the first gameplay gate from level 30 to level 40 affects player retention. The analysis focuses on short-term and mid-term retention using statistically sound hypothesis testing and confidence intervals.

Experiment Design

Variants

gate_30: first gate at level 30

gate_40: first gate at level 40

Primary Metric

retention_7 (player returned on day 7)

Secondary Metric

retention_1 (player returned on day 1)

Statistical Method

Two-proportion Z-test

Bootstrap confidence intervals (95%)

Key Results
Retention Day 1

No statistically significant difference between gate_30 and gate_40

p-value ≈ 0.074

95% confidence interval includes zero

Interpretation

Players do not meaningfully interact with the gating mechanism on the first day. Early engagement remains similar across both variants.

Retention Day 7

Statistically significant difference detected

p-value ≈ 0.0016

95% confidence interval for (gate_40 − gate_30) is entirely negative

Interpretation

Players exposed to the gate at level 40 are less likely to return after one week compared to those gated at level 30.

Effect Size

Absolute difference in day-7 retention: approximately 0.3–1.3 percentage points

Effect direction is consistent across bootstrap resampling

Although the effect size is small, it is statistically robust and unlikely to be driven by random variation.

Behavioral Interpretation

With gate_30, players encounter the core friction/monetization mechanic earlier and adapt to it sooner.

With gate_40, players experience extended uninterrupted gameplay, followed by a late introduction of friction.

This late disruption likely increases frustration or perceived inconsistency, leading to higher mid-term drop-off.

Delaying the gate does not improve onboarding but negatively impacts longer-term retention.

Recommendation

Based on retention metrics alone, gate_30 is the preferred configuration.

gate_40 should only be considered if it demonstrates compensating improvements in other key metrics such as revenue per user, conversion rate, or lifetime value. A combined evaluation with monetization data is recommended before any rollout decision.

Notes

Extreme values in engagement metrics (sum_gamerounds) were inspected but not removed, as retention outcomes are binary and unaffected by continuous outliers.

All statistical tests were conducted after verifying randomization, data integrity, and experiment assumptions.