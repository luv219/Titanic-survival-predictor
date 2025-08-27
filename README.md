
# Titanic Survival Predictor

This repository provides a **Jupyter Notebook** for predicting passenger survival on the Titanic dataset.  
It follows a resilient data loading pattern inspired by the diabetes example—downloading from multiple sources, normalizing headers, and caching locally.

## Contents

- **Titanic_Survival_Predictor.ipynb** — Main notebook with complete workflow:
  - Multi-source dataset loader (with header handling & caching)
  - Data cleaning and exploratory analysis (EDA)
  - Feature engineering and preprocessing with `ColumnTransformer`
  - Model training: Logistic Regression and Random Forest
  - Evaluation with ROC-AUC, confusion matrix, classification report
  - Feature importance visualization
  - Model saving (`joblib`) and inference example

## Data

The notebook attempts to download from:
- [Datasciencedojo Titanic dataset](https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv)
- [Plotly Titanic dataset](https://raw.githubusercontent.com/plotly/datasets/master/titanic.csv)

Standardized schema:
```
Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked
```

The dataset is cached locally at `data/titanic.csv`.

## Requirements

Install dependencies via pip:

```bash
pip install numpy pandas scikit-learn matplotlib joblib
```

Jupyter Notebook is also required to run interactively:

```bash
pip install notebook
```

## Usage

1. Launch Jupyter Notebook:

```bash
jupyter notebook Titanic_Survival_Predictor.ipynb
```

2. Run the cells step by step.

3. The notebook will:
   - Train two models
   - Select the best based on ROC-AUC
   - Save the trained model in `models/`
   - Show inference examples with survival probabilities

## Example Inference

The notebook demonstrates predictions for:

- A 22-year-old male, 3rd class, SibSp=1, Parch=0, Fare=7.25, Embarked=S  
- A 38-year-old female, 1st class, SibSp=1, Parch=0, Fare=71.28, Embarked=C

Output includes predicted survival probability and label.

