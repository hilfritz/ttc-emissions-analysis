# Transit Operational Efficiency & GHG Analysis (GTFS-Based)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![ML](https://img.shields.io/badge/Machine%20Learning-RF%20%7C%20GB-green)
![Workflow](https://img.shields.io/badge/Git-Feature%20Branch-orange)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## Table of Contents
- [Transit Operational Efficiency \& GHG Analysis (GTFS-Based)](#transit-operational-efficiency--ghg-analysis-gtfs-based)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Analytical Objective](#analytical-objective)
  - [Dataset Information](#dataset-information)
  - [Architecture](#architecture)
  - [Data Analytics Pipeline](#data-analytics-pipeline)
  - [Modeling Approach](#modeling-approach)
    - [Random Forest](#random-forest)
    - [Gradient Boosting](#gradient-boosting)
  - [Evaluation Metrics](#evaluation-metrics)
    - [R²](#r)
    - [MAE](#mae)
    - [RMSE](#rmse)
  - [Project Structure](#project-structure)
  - [Installation \& Setup](#installation--setup)
  - [▶️ How to Run](#️-how-to-run)
    - [Run scripts](#run-scripts)
    - [Run application](#run-application)
    - [Run dashboard](#run-dashboard)
    - [Run tests](#run-tests)
  - [Results \& Outputs](#results--outputs)
  - [Git Workflow \& Naming Conventions](#git-workflow--naming-conventions)
    - [Branch Strategy](#branch-strategy)
    - [Branch Naming](#branch-naming)
    - [Optional Branch Naming With User Stories](#optional-branch-naming-with-user-stories)
    - [Commit Message Convention](#commit-message-convention)
    - [Pull Requests](#pull-requests)
  - [Project Team](#project-team)

---

## Project Overview

This project analyzes **public transit operational efficiency and environmental impact** using **GTFS data**.

The project examines how route characteristics such as distance, stop density, route curvature, and route efficiency may influence:

- Trip duration
- Operational efficiency
- Relative GHG intensity

The README provides a simple project-level summary only. The full academic explanation, research questions, hypotheses, and references are documented in the project proposal/report.

---

## Analytical Objective

- Predict trip duration using GTFS-derived features
- Compare transit efficiency across selected agencies
- Estimate relative GHG intensity
- Support scalable and data-light transit performance analysis

---

## Dataset Information

Source: Public GTFS feeds

```
data/
   raw/
   processed/
```

GTFS data may include:

- Routes
- Stops
- Trips
- Stop times
- Schedules
- Route geometry

---

## Architecture

```
GTFS Data
   ↓
Processing
   ↓
Feature Engineering
   ↓
ML Models
   ↓
Predictions
   ↓
Dashboard
```

---

## Data Analytics Pipeline

```
Raw Data
   ↓
Cleaning
   ↓
Feature Engineering
   ↓
EDA
   ↓
Model Training
   ↓
Evaluation
   ↓
Visualization
```

---

## Modeling Approach

The project applies machine learning regression models to predict transit trip duration using GTFS-derived features.

Two ensemble learning methods are used:

```
Random Forest Regression
Gradient Boosting Regression
```

### Random Forest
- Uses multiple decision trees
- Handles nonlinear relationships well
- Provides feature importance insights

### Gradient Boosting
- Builds models sequentially
- Focuses on correcting previous errors
- Typically achieves higher predictive accuracy

These models are suitable for structured tabular data and help capture complex interactions between route features such as:

- Distance
- Stop density
- Route curvature
- Route efficiency

---

## Evaluation Metrics

Model performance is evaluated using standard regression metrics:

```
R² (Coefficient of Determination)
MAE (Mean Absolute Error)
RMSE (Root Mean Squared Error)
```

### R²
- Measures how well the model explains variance
- Higher is better (closer to 1)

### MAE
- Average absolute prediction error
- Easy to interpret in real units

### RMSE
- Penalizes larger errors more heavily
- Useful for understanding model stability

---

## Project Structure

```
ttc-emissions-analysis/

data/
docs/
logs/
outputs/
scripts/
src/
tests/

requirements.txt
README.md
LICENSE
```

---

## Installation & Setup

Create environment:

```
python -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```
pip install -r requirements.txt
```

---

## ▶️ How to Run

### Run scripts

```
python scripts/<script_name>.py
```

### Run application

```
python src/app.py
```

### Run dashboard

```
streamlit run src/app.py
```

### Run tests

```
pytest
```

---

## Results & Outputs

Expected outputs may include:

- Predicted trip durations
- Feature importance results
- Agency comparison summaries
- Relative GHG intensity index
- Charts, tables, and reports saved in `outputs/`

```
outputs/
   charts/
   tables/
   reports/
```

---

## Git Workflow & Naming Conventions

### Branch Strategy

This project follows a feature-branch workflow.

- `main` → stable branch
- Do not commit directly to `main` after the initial setup commit
- Use separate working branches for changes
- All changes should go through Pull Requests before merging into `main`

---

### Branch Naming

Format:

```
type/short-description
```

Branch types:

```
feature/    – new functionality
fix/        – bug fixes
docs/       – documentation updates
test/       – testing work
chore/      – setup / maintenance tasks
refactor/   – internal code improvements
experiment/ – model experiments / trials
```

Examples:

```
feature/gtfs-loader
feature/feature-engineering
feature/model-training
feature/dashboard-ui
fix/date-parsing
docs/readme-update
test/model-tests
chore/project-setup
refactor/data-pipeline
experiment/random-forest-baseline
```

---

### Optional Branch Naming With User Stories

If the team later decides to use user stories, this format can also be used:

```
type/US-##-short-description
```

Examples:

```
feature/US-03-gtfs-loader
test/US-03-loader-tests
docs/US-01-readme-update
```

---

### Commit Message Convention

Format:

```
type: short description
```

Commit types:

```
feat       – new feature
fix        – bug fix
docs       – documentation update
test       – add or update tests
chore      – setup / maintenance
refactor   – internal improvements
experiment – modeling / analysis experiments
```

Examples:

```
feat: implement GTFS loader
feat: add route distance calculation
fix: correct stop density formula
docs: update README
test: add feature engineering tests
chore: initialize project structure
refactor: simplify model pipeline
experiment: compare gradient boosting vs random forest
```

---

### Pull Requests

Pull Request workflow:

```
working branch
      ↓
Pull Request
      ↓
Review
      ↓
Merge into main
```

Rules:

- Do not commit directly to `main` after the initial setup commit
- Each change should be completed in a separate branch
- Pull Requests should clearly describe the change
- Pull Requests should be reviewed before merging
- Keep Pull Requests small and focused where possible

Example Pull Request titles:

```
Add GTFS data loader
Update README documentation
Fix route distance calculation
Add model evaluation metrics
```

---

## Project Team

Group 7

University of Niagara Falls  
Master of Data Analytics  
Capstone Project
