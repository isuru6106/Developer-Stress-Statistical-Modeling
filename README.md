# Predicting Software Developer Stress Levels

## 📌 Project Overview

This project investigates the factors associated with software developer stress and develops statistical models to predict stress levels.

The study uses developer workload, wellbeing, and work-environment characteristics to understand how measurable factors contribute to stress. Two complementary statistical approaches are used:

- **Multiple Linear Regression (MLR)** for predicting the continuous stress score.
- **Ordinal Logistic Regression** for predicting ordered stress categories: Low, Moderate, and High.

---

## 🎯 Objectives

The main objectives of this project are to:

1. Identify important factors associated with software developer stress.
2. Examine relationships between stress levels and workload, wellbeing, and workplace factors.
3. Develop a Multiple Linear Regression model for predicting continuous stress levels.
4. Develop an Ordinal Logistic Regression model for predicting ordered stress categories.
5. Evaluate model performance using appropriate statistical diagnostics and prediction metrics.
6. Identify practical factors that may help organizations understand and manage developer stress.

---

## 📊 Dataset

The dataset contains software developer records with variables related to workload, wellbeing, and working conditions.

### Response Variable

- `Stress_Level` — numerical stress score ranging from low to high stress levels.

### Predictor Variables

| Variable | Description |
|---|---|
| `Hours_Worked` | Number of hours worked |
| `Sleep_Hours` | Hours of sleep |
| `Bugs` | Number of software bugs |
| `Deadline_Days` | Deadline-related time pressure |
| `Coffee_Cups` | Number of coffee cups consumed |
| `Meetings` | Number of meetings |
| `Interruptions` | Number of work interruptions |
| `Experience_Years` | Developer experience level |
| `Code_Complexity` | Level of code complexity |
| `Remote_Work` | Whether the developer works remotely |

The dataset originally contains **526 observations**. After data cleaning and preprocessing, **506 observations** were retained for analysis.

---

## 🧹 Data Preparation

The analysis includes:

- Data quality inspection
- Handling missing observations
- Variable type conversion
- Treatment of categorical predictors
- Removal of irrelevant empty columns
- Creation of ordered stress categories for ordinal logistic regression
- Training and testing data partitioning

---

## 📈 Exploratory Data Analysis

Exploratory analysis was conducted to understand:

- Distribution of developer stress levels
- Relationships between numerical predictors
- Correlations among variables
- Potential influential observations
- Differences in stress across relevant variables

The repository contains the generated visualizations and model diagnostic plots in the `plots/` directory.

---

## 📐 Statistical Modeling

### 1. Multiple Linear Regression

Multiple Linear Regression was used with `Stress_Level` as the continuous response variable.

The final model considers:

- `Hours_Worked`
- `Sleep_Hours`
- `Deadline_Days`
- `Meetings`
- `Interruptions`

Model assumptions were assessed using residual and diagnostic plots, including:

- Residuals vs Fitted
- Normal Q-Q
- Scale-Location
- Residuals vs Leverage
- Cook's Distance
- DFBETAS

The analysis found that sleep, working hours, meetings, interruptions, and deadline pressure are important factors in explaining developer stress. However, heteroscedasticity remained an important limitation of the linear model.

---

### 2. Ordinal Logistic Regression

To model stress severity, the continuous stress score was converted into three ordered categories:

- **Low**
- **Moderate**
- **High**

An Ordinal Logistic Regression model was then developed using the same five key predictors:

- `Hours_Worked`
- `Sleep_Hours`
- `Deadline_Days`
- `Meetings`
- `Interruptions`

The ordinal model achieved an overall test-set classification accuracy of approximately **72.38%**.

Model interpretation was supported using:

- Odds ratios
- 95% confidence intervals
- Confusion matrix
- Class-wise precision, recall, and F1-score
- Predicted category probabilities

---

## 🔎 Key Findings

The analysis indicates that:

- **Sleep duration is a major factor associated with stress.**
- Greater **working hours** are associated with increased stress.
- **Interruptions** contribute to higher stress levels.
- **Meetings** and **deadline pressure** also contribute to stress prediction.
- Experience level, code complexity, and remote-work status were not retained in the final selected models.
- The ordinal model provides a useful approach for identifying different levels of developer stress.

The linear regression diagnostics also indicate that the assumptions of constant variance are not fully satisfied, which should be considered when interpreting the MLR results.

---

## 🛠️ Technologies & Tools

- **R**
- **RStudio**
- **R Markdown**
- **Multiple Linear Regression**
- **Ordinal Logistic Regression**
- **ggplot2**
- **dplyr**
- **tidyr**
- **MASS**
- **Statistical diagnostics and visualization**

---

## 📁 Repository Structure

```text
Developer-Stress-Statistical-Modeling/
│
├── data/
│   └── developer_stress (1).csv
│
├── plots/
│   ├── EDA plots
│   ├── MLR diagnostic plots
│   └── Ordinal Logistic Regression plots
│
├── report/
│   └── Predicting Software Developer Stress Levels_Group02.pdf
│
├── Developer_Stress_Project2.Rmd
├── Developer_Stress_Project2.docx
├── Developer_Stress_Project2.tex
├── Developer_Stress_Statistical_Modeling.Rproj
├── .gitignore
└── README.md
