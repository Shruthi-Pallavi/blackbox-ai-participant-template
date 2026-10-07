# Round 2 — Investigate

## What we concluded

- We tested multiple parameters while keeping the other parameters fixed to identify their effect on the confidence score.
- Changes in **site** (A, C and D) produced noticeable changes in the score, showing that site has an influence on the decision.
- Changes in **tenure_years** also affected the confidence score, but its effect was smaller compared with some of the other parameters tested.
- Increasing **history_score** showed a major effect on the confidence score. In our tests, changing history_score from around 300 to 900 caused the score to drop significantly.
- Changes in **anomaly_ratio** also affected the score, indicating that the system considers anomaly-related behaviour.
- Overall, the results suggest that the confidence score depends on a combination of parameters rather than a single parameter.

## How we got there

- We first kept most parameters constant and changed one parameter at a time.
- We compared the resulting confidence scores after each query.
- We tested different site values including A, C and D.
- We also varied tenure_years and compared the resulting scores.
- We repeated observations with other parameters such as history_score and anomaly_ratio to check whether the effect was consistent.
- The observations were compared across multiple queries rather than relying on a single result.

## What we ruled out

- We ruled out the idea that the confidence score is controlled by only the site value.
- We also ruled out the idea that changing tenure_years alone completely determines the decision.
- No single tested parameter consistently explained every change in the confidence score.

## What we are still unsure about

- The exact mathematical relationship between the parameters is still unknown.
- Some parameters may interact with each other, so changing two parameters together may produce a different effect than changing them individually.
- More controlled experiments are required to determine the relative importance of each parameter.
