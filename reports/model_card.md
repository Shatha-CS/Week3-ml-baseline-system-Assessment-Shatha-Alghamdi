# Model Card – Week 3 Baseline

## Unit of Analysis
One row per user.

## Target
is_high_value (binary classification target).

## Positive Class
1 = high-value user.

## ID Passthrough Columns
user_id

## Primary Metric
Accuracy.

## Problem
The goal is to classify users as high-value or not, enabling downstream targeting and prioritization decisions.

## Data
- Feature table: data/processed/features.parquet
- Dataset hash (sha256): 123743223b535a87a4f28979ddec5b57d5d347c4c0c8bd8f5ab17e95ce460273

## Splits
- Holdout: random stratified split, test_size=0.2, seed=42

## Metrics (holdout)
- Baseline:
  - Accuracy: 0.80
- Model:
  - Accuracy: 1.00
  - ROC AUC: 1.00
  - PR AUC: 1.00
  - Precision: 1.00
  - Recall: 1.00
  - F1: 1.00
  - Positive rate (holdout): 0.20

## Limitations
- Small dataset size may inflate performance metrics.
- No temporal (time-based) validation split.
- Model has not been evaluated on unseen real-world production data.

## Monitoring sketch
- Monitor input feature distributions to detect data drift.
- Track prediction positive rate over time.
- Alert on missing required or forbidden columns at inference time.

## Reproducibility
- Run id: 2026-01-01T12-26-58Z__classification__seed42
- Git commit: 8fd9fb7
- Env: models/runs/2026-01-01T12-26-58Z__classification__seed42/env/pip_freeze.txt
