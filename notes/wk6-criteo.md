# Presentation
## What is new this week
- Hygiene: train/test split, be more careful about how we trained and tested our models
- Evaluations of basic methods
- Exploration of metrics dataset
- PCA/dimensional reduction

## Recap
- clearly broken grids (current definition): triangle/line structure not visible even with noisy bootstrap enhancement
- baseline ground truth: triangle grid 333519 -> 57/872 broken (6.5%), line grid 333346 -> 113/681 broken (13.5%)
- Click clustering method
- metrics dataset: visualization. 
  - dropped many collinear features (e.g. sov_short_ttc highly correlated with sov_short_ttc_score)
  - compare distribution of broken vs non broken
  - importance of features from decision tree methods
  - problems: unbalanced dataset/overfitting, easy to overfit


- ensemble method