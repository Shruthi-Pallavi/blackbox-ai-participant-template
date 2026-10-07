# Round 2 — Parameter Relationship Experiments

## Hypothesis

The confidence score is influenced by multiple input parameters, and changing individual parameters while keeping the others fixed can reveal their relationship with the score.

## Experiment 1 — Site

We tested different site values while keeping the other parameters approximately constant.

- Site A produced high confidence scores in our observations.
- Site C was also tested and produced noticeably different scores in some queries.
- Site D was tested with the same general parameter settings and produced a score around 0.87.
- Therefore, site appears to influence the confidence score, but site alone does not determine the decision.

## Experiment 2 — Tenure Years

We varied `tenure_years` while keeping other parameters similar.

- Different tenure values produced changes in the confidence score.
- The changes were noticeable but were not as large or consistent as the changes observed for some other parameters.
- This suggests that tenure contributes to the score but is not the only major factor.

## Experiment 3 — History Score

We tested different `history_score` values.

- With `history_score` around 300, the confidence score was around the higher range in our observations.
- Increasing `history_score` to around 900 caused a major decrease in confidence in one of our controlled comparisons.
- This indicates that `history_score` can have a strong effect on the confidence score.

## Experiment 4 — Anomaly Ratio

We also changed `anomaly_ratio` while keeping several other parameters fixed.

- Changes in anomaly ratio resulted in changes in the confidence score.
- This indicates that anomaly-related behaviour is considered by the system.

## Overall Observation

The experiments show that the confidence score is affected by a combination of parameters. Site, tenure years, history score and anomaly ratio all showed some relationship with the output, while `history_score` showed one of the more significant changes in our observations.

Further controlled experiments are required to determine the exact mathematical relationship and the relative importance of each parameter.
