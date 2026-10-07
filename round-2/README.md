# Round 2 — Investigate

## Team

Team ID: BB-018

## Hypothesis

The confidence score is influenced by multiple input parameters, and changing individual parameters while keeping the others approximately constant can reveal their relationships with the model's confidence score.

## Experiments

We investigated the effect of different parameters on the confidence score by changing one parameter at a time while keeping the other parameters approximately constant.

### Site

Changing the site produced noticeable changes in the confidence score. This suggests that site has a moderate influence, but site alone does not determine the final decision.

### Tenure Years

Changing tenure years also produced changes in the confidence score. The effect was moderate and appeared to contribute along with other parameters.

### History Score

History score produced the strongest observed change in the confidence score among the parameters tested. This suggests that historical information has a stronger influence on the model output.

## What We Concluded

The confidence score appears to depend on a combination of parameters rather than a single input. History score showed the strongest observed effect, while site and tenure years also affected the confidence score.

## What We Ruled Out

- The confidence score is not controlled by only one parameter.
- Changing tenure years alone does not completely determine the decision.
- A single observed change is not sufficient to explain the entire model behaviour.

## What We Are Still Unsure About

The exact mathematical relationship between the parameters and the confidence score is still unknown. More controlled experiments would be required to determine interactions between parameters.

## Evidence

The supporting experiments, findings, report, and plots are included in this Round 2 submission.
