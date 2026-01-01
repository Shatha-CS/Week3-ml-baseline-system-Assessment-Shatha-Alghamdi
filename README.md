# Week 3 — Ship-Ready Baseline Machine Learning System

This repository contains the Week 3 project, focused on building an **end-to-end baseline machine learning system** with an emphasis on correctness, reproducibility, and safe batch prediction.

The goal is not model optimization, but demonstrating a clean and reliable ML workflow without training–serving mismatches.

---

## Project Description

The system trains a **binary classification model** to predict whether a user is considered high value (`is_high_value`).  
Each row represents a single user, and the same input schema is enforced during training and prediction.

---

## Quickstart

### 1) Setup

The project is run from the repository root after cloning the repository and navigating to the project directory.  
A virtual environment is created using `uv venv` and activated from `.venv\Scripts\activate`.  
All required dependencies are installed using `uv sync`.

### 2) Verify the setup

The environment setup can be verified by running the automated test suite using `uv run pytest`.


---

### 3) Create sample data

A processed feature table is generated for training and prediction using the sample data generation command.  
The generated features are stored under `data/processed/features.csv`.

---

### 4) Train the baseline model

The baseline model is trained using the target column `is_high_value`.  
Each training run creates a new versioned directory under `models/runs/<run_id>/`.

The most recent run is automatically tracked in `models/registry/latest.txt`.

---

### 5) Batch prediction

Batch predictions are generated using the latest trained model on the processed feature data.  
Prediction results are written to the `outputs/preds.csv` file.

---

## Artifacts

Each training run creates a versioned directory under `models/runs/<run_id>/`.  
The most recent run is tracked in `models/registry/latest.txt`.

Stored artifacts include the trained model, input schema, holdout metrics, run metadata, and holdout predictions.

---

## What you submit

- working code (`src/`)
- passing tests (`tests/`)
- filled `reports/model_card.md`
- filled `reports/eval_summary.md`

