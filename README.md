# Heart_Disease_Prediction_Feature_Preprocessing

# Heart Disease Prediction

## Project Overview

This project focuses on understanding and preparing a heart disease dataset for future predictive analytics and machine learning applications.

The project uses the **Heart Failure Prediction Dataset**, which contains demographic and clinical information about patients. The current stage of the project focuses on **Business Understanding, Data Understanding, Data Preprocessing, Data Quality Assessment, and Feature Selection**.

The goal is to understand the dataset, identify relevant variables, assess its quality, and determine whether it is suitable for further analytical and machine learning work.

> **Disclaimer:** This project is for educational, research, and portfolio purposes only. It is not intended to provide medical diagnosis or replace professional medical advice.

---

# 1. Business Understanding

## Problem Statement

Heart disease is one of the major health challenges worldwide. Identifying factors associated with heart disease can help researchers and analysts understand patterns within patient data.

The purpose of this project is to analyze patient health information and identify variables that may be relevant to the presence of heart disease.

The project will first focus on understanding and preparing the dataset before proceeding to predictive modelling in a later stage.

## Business Objective

The main objective is to investigate the factors associated with heart disease and prepare a high-quality dataset that can be used for future predictive analysis.

### Specific Objectives

1. Understand the structure and characteristics of the dataset.
2. Identify the target variable.
3. Identify numerical and categorical variables.
4. Assess the quality of the dataset.
5. Check for missing values and duplicate records.
6. Investigate the distribution of the variables.
7. Identify relevant features for the prediction problem.
8. Investigate relationships and correlations between variables.
9. Determine which variables require encoding.
10. Determine which numerical variables may require scaling.
11. Identify potentially redundant or highly correlated features.
12. Investigate possible outliers.
13. Apply appropriate preprocessing techniques.
14. Determine whether the dataset is ready for future machine learning applications.

---

# 2. Dataset Understanding

The project uses the **Heart Failure Prediction Dataset** from Kaggle.

[Heart Failure Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?utm_source=chatgpt.com)

## Dataset Size

The dataset contains:

* **918 observations**
* **12 columns**
* **11 predictor variables**
* **1 target variable**

## Data Quality

The initial data quality assessment established that:

* There are **no missing values**.
* There are **no duplicate records**.
* The dataset contains both numerical and categorical variables.
* The target variable is binary.

---

# 3. Dataset Features

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

# 4. Target Variable

The target variable is:

`HeartDisease`

It contains two possible values:

| Value | Meaning          |
| ----: | ---------------- |
|   `0` | No Heart Disease |
|   `1` | Heart Disease    |

Since the target contains two classes, it is a **binary target variable**.

---

# 5. Categorical Variables

The categorical variables identified in the dataset are:

### Sex

```text
M
F
```

### ChestPainType

```text
ATA
NAP
ASY
TA
```

### RestingECG

```text
NORMAL
ST
LVH
```

### ExerciseAngina

```text
N
Y
```

### ST_Slope

```text
UP
FLAT
DOWN
```

These variables require appropriate encoding before they can be used in most numerical analytical procedures and future machine learning models.

---

# 6. Data Preprocessing Assessment

The dataset was assessed to determine the preprocessing techniques required before further analysis.

The main preprocessing questions considered were:

1. Which features are most relevant to the prediction problem?
2. Which variables require encoding?
3. Which variables require scaling or normalization?
4. Are there redundant or highly correlated features?
5. How should missing values and outliers be handled?
6. Which preprocessing techniques can improve dataset quality?
7. Is the dataset ready for further analysis and machine learning?

---

# 7. Missing Values

The dataset was checked for missing values.

### Finding

**No missing values were identified.**

Therefore, the following techniques were not required:

* Mean imputation
* Median imputation
* Mode imputation
* Forward filling
* Backward filling

This is an advantage because no information needs to be estimated or replaced.

---

# 8. Duplicate Records

The dataset was checked for duplicate observations.

### Finding

**No duplicate records were identified.**

Therefore, duplicate removal was not necessary.

This indicates that each observation represents a unique record within the dataset.

---

# 9. Encoding Requirements

Categorical variables must be converted into numerical representations before they can be used in most numerical modelling techniques.

## Binary Categorical Variables

The following variables contain two categories:

* `Sex`
* `ExerciseAngina`

These variables can be encoded using **Label Encoding or Binary Encoding**.

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

These variables are suitable for **One-Hot Encoding**.

For example, `ChestPainType` contains:

```text
ATA
NAP
ASY
TA
```

Instead of assigning arbitrary values such as:

```text
ATA = 0
NAP = 1
ASY = 2
TA  = 3
```

One-Hot Encoding can create separate binary columns.

This prevents the encoding from incorrectly suggesting that one type of chest pain is numerically greater or smaller than another.

---

# 10. ST_Slope Encoding

`ST_Slope` contains:

```text
UP
FLAT
DOWN
```

This variable requires careful consideration because the categories represent different slope conditions.

An appropriate categorical encoding method should be selected based on how the variable is intended to be interpreted during subsequent analysis.

The encoding should avoid introducing an artificial relationship that is not supported by the data.

---

# 11. Numerical Variables

The numerical variables identified in the dataset are:

* `Age`
* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

These variables are measured on different numerical scales.

For example:

* Age represents years.
* RestingBP represents blood pressure.
* Cholesterol represents cholesterol level.
* MaxHR represents maximum heart rate.
* Oldpeak represents ST depression.

Because the variables have different ranges, scaling may be required for some future analytical and machine learning techniques.

---

# 12. Scaling and Normalization

Scaling is not necessarily required for every analysis.

However, numerical scaling may be useful when using techniques that are sensitive to differences in feature magnitude.

Standardization can transform numerical variables so that they have a comparable scale.

A common technique is **Standardization**, which transforms values using:

```text
z = (x - mean) / standard deviation
```

For this project, numerical features that may require scaling include:

* `Age`
* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

Scaling will be applied at the appropriate stage before future modelling, rather than unnecessarily altering the raw dataset.

---

# 13. Correlation and Redundant Features

Correlation analysis is important for identifying relationships between numerical variables.

The following numerical variables can be examined:

* `Age`
* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

A correlation matrix can help determine whether two or more variables have a strong relationship.

Highly correlated features may contain overlapping information and could potentially introduce redundancy.

However, a feature should not be removed based solely on correlation. Domain knowledge and additional feature-selection techniques should also be considered.

---

# 14. Outlier Assessment

Outliers are observations that are unusually high or low compared with the majority of observations.

Potential outliers should be investigated in variables such as:

* `RestingBP`
* `Cholesterol`
* `MaxHR`
* `Oldpeak`

Possible techniques for identifying outliers include:

* Boxplots
* Histograms
* Interquartile Range (IQR)
* Descriptive statistics

### Outlier Treatment

Outliers should **not automatically be removed**.

In a health-related dataset, an extreme value may represent a genuine medical observation rather than an error.

Therefore, an outlier should only be removed or transformed when there is sufficient evidence that it is an incorrect or problematic observation.

---

# 15. Feature Selection Using Statistical Significance

Feature selection was also explored using **statistical significance and p-values**.

An OLS-based exploratory analysis was performed to investigate the relationship between the variables and the target.

The analysis produced:

```text
R-squared ≈ 0.533
Adjusted R-squared ≈ 0.525
```

The analysis also showed that some variables and categorical levels had statistically significant relationships with the target, while others were less statistically significant.

### Important Note

The OLS analysis was used as an **exploratory feature-selection technique**.

It should not be considered the final predictive approach because `HeartDisease` is a binary target variable.

The p-value analysis is useful for understanding which variables may have stronger statistical relationships with the outcome.

---

# 16. Relevant Features

Based on the exploratory statistical analysis, several variables showed evidence of being relevant to the heart disease outcome.

Variables identified as potentially important include:

* `Sex`
* `ChestPainType`
* `FastingBS`
* `MaxHR`
* `ExerciseAngina`
* `Oldpeak`
* `ST_Slope`

However, feature relevance should not be determined using p-values alone.

Other factors such as:

* Correlation
* Domain knowledge
* Data distribution
* Model-based feature importance
* Multicollinearity

should be considered in later stages.

---

# 17. Preprocessing Techniques Applied or Recommended

The preprocessing assessment identified the following approaches:

| Data Issue                    | Finding            | Recommended Treatment                          |
| ----------------------------- | ------------------ | ---------------------------------------------- |
| Missing values                | None               | No treatment required                          |
| Duplicate records             | None               | No treatment required                          |
| Binary categorical variables  | Present            | Binary/Label Encoding                          |
| Nominal categorical variables | Present            | One-Hot Encoding                               |
| Numerical variables           | Present            | Scaling where required                         |
| Potential outliers            | Need investigation | Statistical and visual assessment              |
| Correlated variables          | Need investigation | Correlation analysis                           |
| Feature relevance             | Investigated       | Statistical significance and further selection |
| Target variable               | Binary             | Keep as 0/1                                    |

---

# 18. Dataset Quality Assessment

Overall, the dataset is in good condition for further analysis.

The major positive findings are:

* No missing values
* No duplicate records
* Clearly defined target variable
* Combination of useful numerical and categorical features
* Manageable dataset size
* Categorical variables with identifiable categories

Some preprocessing is still required because categorical variables need appropriate encoding and numerical variables may need scaling depending on the next analytical technique.

---

# 19. Is the Dataset Ready for Machine Learning?

### Current Status: **Mostly Ready**

The dataset is of sufficient quality to proceed to the next stage.

However, it should not be considered completely ready in its raw form because:

* Categorical variables still require encoding.
* Numerical variables may require scaling depending on the selected technique.
* Potential outliers should be investigated.
* Correlations and redundant variables should be assessed further.
* Feature selection should be finalized.

After these preprocessing steps are completed, the dataset can be prepared for the next stage of the project.

---

# 20. Current Project Status

| Project Stage                       | Status                        |
| ----------------------------------- | ----------------------------- |
| Business Understanding              | Completed                     |
| Dataset Understanding               | Completed                     |
| Data Quality Assessment             | Completed                     |
| Missing Value Assessment            | Completed                     |
| Duplicate Assessment                | Completed                     |
| Categorical Variable Identification | Completed                     |
| Encoding Assessment                 | Completed                     |
| Scaling Assessment                  | Completed                     |
| Correlation Assessment              | In Progress / To be finalized |
| Outlier Assessment                  | In Progress / To be finalized |
| Statistical Feature Selection       | Completed                     |
| Machine Learning Modelling          | **Not Started**               |
| Model Evaluation                    | **Not Started**               |
| Deployment                          | **Not Started**               |

---

# 21. Next Steps

The next stage of the project will focus on implementing the identified preprocessing techniques.

The planned workflow is:

```text
Data Preprocessing
       ↓
Encoding
       ↓
Scaling
       ↓
Correlation Analysis
       ↓
Outlier Assessment
       ↓
Final Feature Selection
       ↓
Prepared Dataset
       ↓
Machine Learning Modelling
```

Machine learning modelling will only begin after the preprocessing stage has been completed and the final feature set has been established.

---

# 22. Technologies Used

The project currently uses:

* **Python**
* **Pandas** — data manipulation and analysis
* **NumPy** — numerical computation
* **Matplotlib** — visualization
* **Seaborn** — statistical visualization
* **Statsmodels** — statistical analysis and p-value testing
* **Scikit-learn** — preprocessing and future machine learning work
* **Jupyter Notebook / Google Colab** — analysis and experimentation
* **Git & GitHub** — version control and project documentation

---

# 23. Project Structure

A recommended project structure is:

```text
heart-disease-prediction/
│
├── data/
│   └── heart.csv
│
├── notebooks/
│   ├── business_understanding.ipynb
│   ├── data_understanding.ipynb
│   ├── data_preprocessing.ipynb
│   └── feature_selection.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```



---

# 24. Conclusion

The current stage of this project has focused on understanding and preparing the heart disease dataset for future predictive analysis.

The dataset contains **918 observations and 12 columns**, with **11 predictor variables and one binary target variable**.

The data quality assessment found:

* No missing values
* No duplicate records
* Numerical and categorical variables requiring different preprocessing approaches

Categorical variables were identified for appropriate encoding, while numerical variables were assessed for possible scaling. Correlation and outlier analysis were identified as important additional preprocessing steps.

Feature selection was also explored using statistical significance and p-values. The analysis provided useful information about variables that may be associated with heart disease.

Overall, the dataset is **mostly ready for the next stage**, but the identified preprocessing techniques should be finalized and implemented before machine learning modelling begins.

---

# Author

**Gabriel Dzimado**

**BSc Data Science and Analytics**
**Ghana Communication Technology University (GCTU)**
** Data Science Intern

---

# Disclaimer

This project is intended strictly for **educational, research, and portfolio purposes**.

The analysis does not provide medical diagnosis or treatment recommendations. The dataset and any future predictive models should not be used as a substitute for professional medical advice.

---

# Dataset Reference

**Heart Failure Prediction Dataset — Kaggle**

[Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?utm_source=chatgpt.com)
