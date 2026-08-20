# ❤️ Heart Disease Prediction

<p align="center">
  <img src="project-banner.png" alt="Heart Disease Prediction Project Banner" width="100%">
</p>

<h2 align="center">Data Understanding, Feature Selection & Preprocessing</h2>

<p align="center">
  <strong>AnalystLab Africa | Data Science Internship - Week 3</strong>
</p>

<p align="center">
  Preparing a Clean, ML-Ready Dataset
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-blue?logo=pandas)
![Statistics](https://img.shields.io/badge/Statistics-Feature%20Selection-purple)
![Scikit Learn](https://img.shields.io/badge/Scikit--learn-Preprocessing-orange?logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

</p>

---

# 📌 Project Overview

This project focuses on understanding and preparing a heart disease dataset for future predictive analysis.

Using the **Heart Failure Prediction Dataset**, the project investigates patient demographic and clinical variables, assesses data quality, identifies relevant features, and determines the appropriate preprocessing techniques required before machine learning.

The current stage of the project focuses on:

* Business Understanding
* Data Understanding
* Data Quality Assessment
* Exploratory Analysis
* Data Preprocessing
* Categorical Encoding
* Scaling Assessment
* Correlation Analysis
* Outlier Assessment
* Feature Selection using Statistical Significance

The objective is to produce a **clean, well-understood, and machine-learning-ready dataset** before proceeding to predictive modelling.

> ⚠️ **Disclaimer:** This project is for educational, research, and portfolio purposes only. It is not intended to provide medical diagnosis or replace professional medical advice.

---

# 🎯 Business Understanding

## Problem Statement

Heart disease is one of the major health challenges worldwide. Identifying factors associated with heart disease can help researchers and analysts understand patterns within patient data.

The purpose of this project is to analyze patient health information and identify variables that may be relevant to the presence of heart disease.

The project first focuses on understanding and preparing the dataset before proceeding to predictive modelling in a later stage.

## Business Objective

The main objective is to investigate factors associated with heart disease and prepare a high-quality dataset for future predictive analysis.

### Specific Objectives

1. Understand the structure and characteristics of the dataset.
2. Identify the target variable.
3. Identify numerical and categorical variables.
4. Assess the quality of the dataset.
5. Check for missing values and duplicate records.
6. Investigate the distribution of variables.
7. Identify relevant features for the prediction problem.
8. Investigate relationships and correlations between variables.
9. Determine which variables require encoding.
10. Determine which numerical variables may require scaling.
11. Identify potentially redundant or highly correlated features.
12. Investigate possible outliers.
13. Apply appropriate preprocessing techniques.
14. Determine whether the dataset is ready for future machine learning applications.

---

# 📊 Dataset at a Glance

The project uses the **Heart Failure Prediction Dataset** from Kaggle.

[Heart Failure Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?utm_source=chatgpt.com)

| Dataset Metric      |                     Value |
| ------------------- | ------------------------: |
| Observations        |                   **918** |
| Predictor Variables |                    **11** |
| Target Variable     |                     **1** |
| Total Columns       |                    **12** |
| Missing Values      |                     **0** |
| Duplicate Records   |                     **0** |
| Problem Type        | **Binary Classification** |

---

# 🔎 Data Understanding

The dataset contains demographic and clinical information relating to patients and their heart disease status.

## Features

| Feature          | Description                           | Data Type   |
| ---------------- | ------------------------------------- | ----------- |
| `Age`            | Age of the patient                    | Numerical   |
| `Sex`            | Sex of the patient                    | Categorical |
| `ChestPainType`  | Type of chest pain                    | Categorical |
| `RestingBP`      | Resting blood pressure                | Numerical   |
| `Cholesterol`    | Serum cholesterol level               | Numerical   |
| `FastingBS`      | Fasting blood sugar indicator         | Binary      |
| `RestingECG`     | Resting electrocardiogram results     | Categorical |
| `MaxHR`          | Maximum heart rate achieved           | Numerical   |
| `ExerciseAngina` | Exercise-induced angina               | Categorical |
| `Oldpeak`        | ST depression induced by exercise     | Numerical   |
| `ST_Slope`       | Slope of the peak exercise ST segment | Categorical |
| `HeartDisease`   | Presence or absence of heart disease  | Target      |

---

# 🎯 Target Variable

The target variable is:

```text
HeartDisease
```

It contains two possible classes:

| Value | Meaning          |
| ----: | ---------------- |
|   `0` | No Heart Disease |
|   `1` | Heart Disease    |

Because the target contains two classes, the prediction problem is a **binary classification problem**.

---

# 🧹 Data Quality Assessment

The dataset was examined to determine whether it contained common data-quality problems.

## Missing Values

The dataset was checked for missing values.

**Finding:**

> No missing values were identified.

Therefore, imputation techniques such as mean, median, or mode replacement were not required.

## Duplicate Records

The dataset was checked for duplicate observations.

**Finding:**

> No duplicate records were identified.

Therefore, duplicate removal was not necessary.

---

# 🔤 Categorical Variables

The categorical variables identified in the dataset are:

### `Sex`

```text
M
F
```

### `ChestPainType`

```text
ATA
NAP
ASY
TA
```

### `RestingECG`

```text
NORMAL
ST
LVH
```

### `ExerciseAngina`

```text
N
Y
```

### `ST_Slope`

```text
UP
FLAT
DOWN
```

These variables require appropriate encoding before being used in most numerical analytical procedures and future machine learning models.

---

# 🔢 Encoding Assessment

## Binary Categorical Variables

The following variables contain two categories:

* `Sex`
* `ExerciseAngina`

These can be converted into binary numerical representations.

For example:

```text
Sex

M → 1
F → 0
```

and:

```text
ExerciseAngina

Y → 1
N → 0
```

## Nominal Categorical Variables

The following variables contain multiple categories without a simple numerical order:

* `ChestPainType`
* `RestingECG`

These are suitable for **One-Hot Encoding**.

For example, instead of assigning:

```text
ATA = 0
NAP = 1
ASY = 2
TA  = 3
```

One-Hot Encoding creates separate binary columns.

This prevents the model from incorrectly interpreting the categories as having a numerical ranking.

---

# 📐 ST_Slope Encoding

`ST_Slope` contains:

```text
UP
FLAT
DOWN
```

This variable requires careful consideration because the categories represent different slope conditions.

An appropriate categorical encoding method should be selected based on the intended analytical interpretation.

The encoding should avoid introducing an artificial numerical relationship that is not supported by the data.

---

# 📏 Numerical Variables

The numerical variables identified are:

* `Age`
* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

These variables are measured using different scales.

For example:

* `Age` represents years.
* `RestingBP` represents blood pressure.
* `Cholesterol` represents cholesterol level.
* `MaxHR` represents maximum heart rate.
* `Oldpeak` represents ST depression.

Because their ranges differ, scaling may be required for certain future analytical and machine learning techniques.

---

# ⚖️ Scaling & Normalization Assessment

Scaling is not required for every type of analysis.

However, it may be important for algorithms that are sensitive to differences in feature magnitude.

A common standardization formula is:

```text
z = (x - mean) / standard deviation
```

The numerical variables that may require scaling include:

* `Age`
* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

Scaling will be applied at the appropriate stage rather than unnecessarily modifying the original dataset.

---

# 📈 Correlation Analysis

Correlation analysis is useful for understanding relationships between numerical variables and identifying potentially redundant features.

The following variables can be examined:

* `Age`
* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

A correlation matrix can help identify variables that have strong relationships with each other.

Highly correlated predictors may contain overlapping information.

However, a feature should **not automatically be removed simply because it is correlated with another feature**. Domain knowledge and additional feature-selection techniques should also be considered.

---

# 🚨 Outlier Assessment

Potential outliers should be investigated in numerical variables such as:

* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

Possible techniques include:

* Boxplots
* Histograms
* Descriptive statistics
* Interquartile Range (IQR)

## Outlier Treatment

Outliers should not automatically be removed.

In a health-related dataset, an extreme value may represent a genuine medical observation rather than a data-entry error.

Therefore, an outlier should only be removed or transformed when there is sufficient evidence that it is incorrect or problematic.

---

# 🔍 Feature Selection

Feature selection was explored to determine which variables may contribute to the heart disease outcome.

Statistical significance was investigated using **p-values**.

The exploratory OLS analysis produced:

| Statistic          |       Value |
| ------------------ | ----------: |
| R-squared          | **≈ 0.533** |
| Adjusted R-squared | **≈ 0.525** |

Several variables and categorical levels showed statistically significant relationships with the target.

Potentially relevant variables identified during the exploratory analysis included:

* `Sex`
* `ChestPainType`
* `FastingBS`
* `MaxHR`
* `ExerciseAngina`
* `Oldpeak`
* `ST_Slope`

### Important Note

The OLS analysis is being used as an **exploratory statistical feature-selection technique**.

It should not be considered the final predictive approach because `HeartDisease` is a binary target variable.

The p-value analysis provides useful statistical insight into which variables may have stronger relationships with the outcome.

---

# 🧠 Feature Relevance

Based on the exploratory statistical analysis, several variables showed evidence of being relevant to the heart disease outcome.

Potentially important variables include:

* `Sex`
* `ChestPainType`
* `FastingBS`
* `MaxHR`
* `ExerciseAngina`
* `Oldpeak`
* `ST_Slope`

However, feature relevance should not be determined using p-values alone.

Further analysis should consider:

* Correlation
* Domain knowledge
* Multicollinearity
* Feature distributions
* Additional feature-selection techniques
* Performance during future modelling

---

# 🛠️ Preprocessing Summary

| Data Issue                    | Finding               | Treatment                         |
| ----------------------------- | --------------------- | --------------------------------- |
| Missing values                | None                  | No treatment required             |
| Duplicate records             | None                  | No treatment required             |
| Binary categorical variables  | Present               | Binary/Label Encoding             |
| Nominal categorical variables | Present               | One-Hot Encoding                  |
| Numerical variables           | Present               | Scaling where required            |
| Potential outliers            | Require investigation | Statistical and visual assessment |
| Correlated variables          | Require investigation | Correlation analysis              |
| Feature relevance             | Investigated          | Statistical significance          |
| Target variable               | Binary                | Keep as 0/1                       |

---

# 🏆 Dataset Quality Assessment

Overall, the dataset is in good condition for further analysis.

### Positive Findings

✅ No missing values
✅ No duplicate records
✅ Clearly defined target variable
✅ Combination of numerical and categorical features
✅ Manageable dataset size
✅ Clearly identifiable categorical variables

### Remaining Preprocessing Considerations

🔄 Investigate potential outliers
🔄 Finalize correlation analysis
🔄 Apply appropriate encoding
🔄 Determine final scaling requirements
🔄 Finalize feature selection

---

# 🚧 Project Status

| Project Stage                       | Status         |
| ----------------------------------- | -------------- |
| Business Understanding              | ✅ Completed    |
| Data Understanding                  | ✅ Completed    |
| Data Quality Assessment             | ✅ Completed    |
| Missing Value Analysis              | ✅ Completed    |
| Duplicate Analysis                  | ✅ Completed    |
| Categorical Variable Identification | ✅ Completed    |
| Encoding Assessment                 | ✅ Completed    |
| Scaling Assessment                  | ✅ Completed    |
| Statistical Feature Selection       | ✅ Completed    |
| Correlation Analysis                | 🔄 In Progress |
| Outlier Assessment                  | 🔄 In Progress |
| Final Preprocessing                 | 🔄 In Progress |
| Machine Learning Modelling          | ⏳ Upcoming     |
| Model Evaluation                    | ⏳ Upcoming     |
| Deployment                          | ⏳ Upcoming     |

---

# 📚 Key Learning Outcomes

Through this project, I have strengthened my understanding of:

* Business understanding in data science
* Dataset exploration
* Data quality assessment
* Missing-value analysis
* Duplicate detection
* Categorical data identification
* Categorical encoding
* Numerical feature scaling
* Correlation analysis
* Outlier detection
* Statistical significance
* Feature selection
* Preparing datasets for machine learning
* Documenting data science projects using GitHub

---

# 🚀 Next Steps

The next stage of the project will focus on:

1. Finalizing the preprocessing analysis.
2. Applying the selected encoding techniques.
3. Investigating and handling relevant outliers.
4. Completing correlation analysis.
5. Finalizing feature selection.
6. Preparing the final clean dataset.
7. Proceeding to machine learning modelling.

Machine learning modelling will begin **after the preprocessing stage has been completed**.

---

# 🛠️ Technologies & Tools

| Technology                | Purpose                           |
| ------------------------- | --------------------------------- |
| 🐍 Python                 | Data analysis                     |
| 🐼 Pandas                 | Data manipulation                 |
| 🔢 NumPy                  | Numerical computation             |
| 📊 Matplotlib             | Data visualization                |
| 📈 Seaborn                | Statistical visualization         |
| 📐 Statsmodels            | Statistical analysis              |
| 🤖 Scikit-learn           | Preprocessing                     |
| 📓 Jupyter / Google Colab | Development and experimentation   |
| 🐙 Git & GitHub           | Version control and documentation |

---

# 📁 Project Structure

```text
heart-disease-prediction/
│
├── assets/
│   └── project-banner.png
│
├── data/
│   └── heart.csv
│   └──clean_heart_disease_dataset.csv
│   └── X_selected.csv
│
├── notebooks/
│   ├── jupyternotebook.ipynb
│
├── files/
│    └── business_understanding_report.pdf 
│    └── datapreprocessing_report.pdf
│
├── README.md
├── requirements.txt
└── .gitignore
```

The structure can be modified to reflect the actual organization of the project.

---

# 💻 Installation

## Clone the Repository

```bash
git clone https://github.com/your-username/heart-disease-prediction.git
cd heart-disease-prediction
```

## Create a Virtual Environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### macOS/Linux

```bash
source venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Requirements

A basic `requirements.txt` file can contain:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
jupyter
```

---

# 📓 Running the Project

If the project uses Jupyter Notebook:

```bash
jupyter notebook
```

Then open the notebooks in the `notebooks/` directory in the recommended order:

```text
01 → Business Understanding
02 → Data Understanding
03 → Data Preprocessing
04 → Feature Selection
```

---

# 📝 Current Project Scope

This repository currently focuses on:

> **Understanding → Cleaning → Preprocessing → Feature Selection**

Machine learning model development has **not yet been included** because it represents the next stage of the project.

This ensures that the repository accurately reflects the work completed during the current phase of the **AnalystLab Africa Data Science Internship**.

---

# 👤 Author

**Gabriel Dzimado**

BSc Data Science and Analytics
**Ghana Communication Technology University (GCTU)**

**Data Science Intern — AnalystLab Africa**

---

# ⚠️ Disclaimer

This project is intended strictly for **educational, research, and portfolio purposes**.

The analysis does not provide medical diagnosis or treatment recommendations. The dataset and any future predictive models should not be used as a substitute for professional medical advice.

---

# 📚 Dataset Reference

**Heart Failure Prediction Dataset — Kaggle**

[Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?utm_source=chatgpt.com)

---

<p align="center">
  <strong>Built with Python 🐍 | Data Science 📊 | Statistics 📐</strong>
</p>

<p align="center">
  AnalystLab Africa — Data Science Internship
</p>
