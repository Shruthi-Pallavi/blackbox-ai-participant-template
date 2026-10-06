# round-1 — Observe

**Team:** BB-018 **Queries used:** 31

## What we concluded

We tested the building access control system using 31 queries and varied several input fields.

The system returned both a numerical confidence score and an APPROVE/DECLINE decision.

The score changes when the input values are changed, but the effect of each input is not the same.

In at least one controlled comparison, changing the number of escorts from 3 to 4 did not change the score: both queries produced a score of 0.9669.

This suggests that some inputs may have little effect in certain regions of the input space.

## How we got there

We varied inputs including:

- anomaly_ratio
- badge_age_days
- clearance_level
- escorts
- history_score
- linked_badges
- recent_denials
- requested_zone
- site
- tenure_years

We compared the scores returned by repeated queries and observed which input values changed between queries.

For example, queries 26 and 27 had the same visible values for the other fields while the escorts value changed from 4 to 3. Both produced a score of 0.9669.

Other observations showed score changes when different input values were modified. However, some of those queries changed multiple inputs at once, so they cannot be used to prove the effect of one individual feature.

## What we ruled out

We did not find evidence that every input has a large effect on the score.

We also did not find enough evidence to claim a simple threshold for APPROVE versus DECLINE.

We cannot attribute every observed score change to one particular input because some experiments changed multiple inputs simultaneously.

## What we are still unsure about

We are still unsure about:

- which individual inputs have the strongest influence;
- whether each input has a monotonic relationship with the score;
- whether different inputs interact with each other;
- the exact boundary between APPROVE and DECLINE.
