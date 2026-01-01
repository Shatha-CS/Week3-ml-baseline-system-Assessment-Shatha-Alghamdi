# Evaluation Summary – Week 3 Baseline

## What was trained
- Model family: Logistic Regression (binary classification).
- Preprocessing:
  - Numeric features used as-is.
  - Categorical feature (country) encoded via one-hot encoding.
  - Fixed decision threshold = 0.5.
- Input schema enforced at inference time to prevent target leakage.

## Results (baseline vs model)
- Baseline (holdout):
  - Accuracy: 0.80
  - ROC AUC: 0.50
- Trained model (holdout):
  - Accuracy: 1.00
  - ROC AUC: 1.00
  - Precision: 1.00
  - Recall: 1.00
  - F1: 1.00
- Positive rate in holdout set: 0.20

## Error analysis
- No misclassifications observed on the small holdout set; results likely optimistic.
- High performance may be influenced by limited dataset size and simple feature relationships.
- Explicit checks prevent target leakage ( `is_high_value` is forbidden at inference).

## Recommendation
- Do **not ship to production yet**.
- While metrics are perfect on holdout, the dataset is small and lacks temporal or real-world validation.
- Recommended next steps:
  - Evaluate on a larger and more representative dataset.
  - Add temporal or group-based splits.
  - Monitor performance stability before deployment.

