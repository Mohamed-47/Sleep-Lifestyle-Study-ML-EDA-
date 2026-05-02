# Sleep Health & Lifestyle Study — EDA & Predictive Modeling

A machine learning project exploring how daily habits and health metrics relate to sleep disorders.  
Course: Machine Learning | Metropolitan State University of Denver  
Dataset: [Sleep and Lifestyle Study – Kaggle](https://www.kaggle.com/datasets/ayeshaimran1619/sleep-and-lifestyle-study)

---

## Overview

This project analyzes a dataset of 374 individuals to understand how lifestyle factors like stress, physical activity, and occupation relate to sleep health. The goal is to build machine learning models that can predict whether a person has no sleep disorder, insomnia, or sleep apnea based on their daily habits and health data.

---

## Research Questions

1. Can we predict whether a person has a sleep disorder (None / Insomnia / Sleep Apnea) from lifestyle and health data?
2. Does higher stress always mean worse sleep quality, and does this hold across all groups?
3. Does a person's occupation affect how likely they are to have a sleep disorder?

---

## Dataset

| Feature | Description |
|---|---|
| Sleep Duration | Average hours of sleep per night |
| Quality of Sleep | Subjective rating (1–10) |
| Stress Level | Self-reported stress rating (1–10) |
| Physical Activity Level | Minutes of exercise per day |
| Occupation | Job/profession of the individual |
| BMI Category | Normal, Overweight, or Obese |
| Blood Pressure | Systolic / Diastolic readings |
| Heart Rate | Resting heart rate (bpm) |
| Daily Steps | Average steps per day |
| Age / Gender | Demographic information |
| Sleep Disorder** | Target variable — None, Insomnia, or Sleep Apnea** |

---

## Project Structure

```
Sleep-Lifestyle-Study-ML-EDA/
│
├── sleep_health_ML_project.ipynb   # Main Jupyter notebook (EDA + Models)
├── README.md                       # Project overview (this file)
```

---

## Methodology

### Exploratory Data Analysis
- Summary statistics for all features
- Distribution plots for key numeric features
- Stress vs. Sleep Quality scatter plot with regression line
- Sleep disorder rates by occupation (stacked bar chart)
- Correlation heatmap across all numeric features
- Feature distributions split by disorder group (box plots)

### Models Trained
| Model | Purpose |
|---|---|
| Logistic Regression | Baseline model |
| Random Forest | Comparison model |
| XGBoost | Primary model |

All models used:
- Stratified train/test split (80/20)
- 5-fold stratified cross-validation
- Class weighting** to handle imbalanced classes
- Macro F1-score** as the primary evaluation metric

---

## Key Findings

- XGBoost achieved the best performance across all three disorder classes
- Stress Level** is the single strongest predictor of sleep quality (Pearson r ≈ –0.90)
- The stress–sleep quality relationship holds consistently across all occupations and disorder groups
- Sales representatives and managers** show higher rates of insomnia compared to other occupations
- Stress Level, Sleep Duration, Age, and BMI Category** are the most important features for predicting sleep disorders

---

## How to Run

### Option 1 — Google Colab (Recommended, no setup needed)
1. Open [Google Colab](https://colab.research.google.com)
2. Click **File → Open Notebook → GitHub**
3. Paste this repo URL and open `sleep_health_ML_project.ipynb`
4. Click **Runtime → Run All**

### Option 2 — Run Locally
```bash
# Clone the repo
git clone https://github.com/Mohamed-47/Sleep-Lifestyle-Study-ML-EDA.git
cd Sleep-Lifestyle-Study-ML-EDA

# Install dependencies
pip install kagglehub xgboost scikit-learn seaborn matplotlib pandas numpy

# Open the notebook
jupyter notebook sleep_health_ML_project.ipynb
```

> Note: A [Kaggle API key](https://www.kaggle.com/settings) is required to download the dataset automatically via `kagglehub`.

---

## Dependencies

- Python 3.8+
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- xgboost
- kagglehub
- scipy

---

## AI Tool Usage

This project used **Claude (Anthropic)** as an AI assistant for debugging Python code, understanding model outputs, and reviewing analysis. All code, analysis, and conclusions are the author's own work.

---

## Author

Mohamed Abdin  
Metropolitan State University of Denver
