# YuvaIntern-Week-3
This project uses R to analyze the Pima Indians Diabetes Dataset and predict diabetes outcomes using logistic regression. It includes data cleaning, hypothesis testing, correlation analysis, cross-validation, and model evaluation using accuracy, precision, recall, F1-score, and ROC-AUC.
# Diabetes Prediction Using Logistic Regression in R

##  Project Overview

This project focuses on **Statistical Analysis and Predictive Modeling using R**. It uses the **Pima Indians Diabetes Dataset** to analyze clinical factors related to diabetes and develop a classification model for predicting diabetes outcomes.

The project implements **Logistic Regression**, which is suitable because the target variable contains two classes: **negative (neg)** and **positive (pos)** diabetes outcomes. The complete workflow includes data preprocessing, exploratory analysis, hypothesis testing, correlation analysis, model training, cross-validation, performance evaluation, and diagnostic analysis.

---

##  Objectives

* Analyze the Pima Indians Diabetes Dataset.
* Identify relationships between clinical variables and diabetes outcomes.
* Handle missing values using median imputation.
* Perform statistical hypothesis testing.
* Analyze correlations and data distributions.
* Build a Logistic Regression classification model.
* Apply an 80:20 train-test split.
* Perform 10-fold cross-validation.
* Evaluate model performance using multiple metrics.
* Analyze model diagnostics and identify possible improvements.

---

##  Dataset

The project uses the **PimaIndiansDiabetes2** dataset available through the `mlbench` package in R.

### Dataset Details

* **Observations:** 768
* **Predictor Variables:** 8
* **Target Variable:** Diabetes
* **Classes:** `neg` and `pos`

### Features

| Feature     | Description                  |
| ----------- | ---------------------------- |
| Pregnancies | Number of pregnancies        |
| Glucose     | Plasma glucose concentration |
| Pressure    | Blood pressure               |
| Triceps     | Skin thickness               |
| Insulin     | Insulin level                |
| Mass        | Body Mass Index (BMI)        |
| Pedigree    | Diabetes pedigree function   |
| Age         | Age of the individual        |
| Diabetes    | Diabetes outcome             |

The dataset contains 500 negative and 268 positive observations.

---

##  Data Preprocessing

Several numerical variables contain missing values. Missing values are replaced using the **median** of the corresponding variable.

Median imputation is used because it allows all observations to be retained and is less affected by extreme values than mean imputation.

The target variable is converted into a factor with two levels:

```text
neg
pos
```

---

##  Exploratory Data Analysis

Initial analysis is performed to understand:

* Dataset dimensions
* Data structure
* Summary statistics
* Missing values
* Diabetes outcome distribution

The project also examines the distribution and relationships of important numerical variables.

---

##  Statistical Analysis

### Hypothesis Testing

Two major hypotheses are examined:

### 1. BMI and Diabetes

**Null Hypothesis (H₀):**
The mean BMI is the same for negative and positive diabetes groups.

**Alternative Hypothesis (H₁):**
The mean BMI differs between the two groups.

An independent two-sample **t-test** is used.

### 2. Glucose and Diabetes

**Null Hypothesis (H₀):**
The mean glucose level is the same for negative and positive groups.

**Alternative Hypothesis (H₁):**
The mean glucose level differs between the groups.

An independent two-sample **t-test** is used.

---

##  Correlation and Distribution Analysis

Pearson correlation tests are performed to examine relationships between:

* Glucose and BMI
* Glucose and Age

Shapiro-Wilk tests, histograms, and Q-Q plots are used to examine data distributions and normality.

---

##  Machine Learning Model

### Logistic Regression

Logistic Regression is used because diabetes outcome is a binary classification problem.

The model uses the following predictors:

```text
Pregnancies
Glucose
Pressure
Triceps
Insulin
Mass
Pedigree
Age
```

The model estimates the probability that an individual belongs to the positive diabetes class.

---

## Train-Test Split and Cross-Validation

The dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

Stratified sampling is used to preserve the outcome proportions in both datasets.

Within the training data, **10-fold cross-validation** is performed to estimate how consistently the model performs across different training and validation subsets.

---

## 📊 Model Evaluation

The trained model is evaluated on the held-out test dataset.

The project uses the following evaluation metrics:

* Accuracy
* Sensitivity / Recall
* Specificity
* Precision
* F1-Score
* ROC-AUC

A **confusion matrix** is used to identify:

* True Positives
* True Negatives
* False Positives
* False Negatives

ROC-AUC is also calculated to evaluate the model's ability to distinguish between the two diabetes classes.

---

## 🔬 Model Diagnostics

Deviance residuals are plotted against fitted probabilities to identify unusual observations or systematic patterns that may indicate model limitations.

Possible improvements include:

* Checking influential observations
* Checking multicollinearity
* Evaluating calibration
* Comparing alternative classification algorithms

---

##  Strengths

* Logistic Regression is appropriate for binary classification.
* The model is relatively easy to interpret.
* 10-fold cross-validation provides a more reliable performance estimate.
* A separate test set is used for final evaluation.
* Multiple performance metrics are considered.
* Statistical analysis is integrated with predictive modeling.

---

##  Limitations

* Median imputation does not represent uncertainty in missing values.
* The dataset is relatively small.
* Logistic Regression assumes a linear relationship between predictors and log-odds.
* Class imbalance makes accuracy alone insufficient.
* External validation and calibration could improve the model assessment.

Future work can compare **Random Forest, Gradient Boosting, and SVM** models using the same cross-validation procedure.

---

## Technologies Used

* **R**
* **RStudio**
* **mlbench**
* **caret**
* **pROC**
* **ggplot2**
* Logistic Regression
* Statistical Hypothesis Testing
* Cross-Validation
* Data Visualization

---

##  Project Structure

Diabetes-Prediction/
│
├── week3_diabetes_predictive_modeling.R
├── README.md
├── cleaned_data.csv
├── model_performance.csv
└── plots/
```

> File names may vary depending on the files included in the repository.

---

##  How to Run

### 1. Install R and RStudio

Download and install R and RStudio on your system.

### 2. Open the R Script

Open:

```text
week3_diabetes_predictive_modeling.R
```

in RStudio.

### 3. Install Required Packages

Install the required packages if they are not already installed:

```r
install.packages(c("mlbench", "caret", "pROC", "ggplot2", "dplyr"))
```

### 4. Run the Script

Execute the R script in RStudio.

The script loads the dataset, performs preprocessing and statistical analysis, trains the Logistic Regression model, performs 10-fold cross-validation, evaluates the test set, generates diagnostic plots, and saves relevant output files.

---

##  Conclusion

This project demonstrates an end-to-end workflow for **statistical analysis and predictive modeling in R**. The Pima Indians Diabetes Dataset is cleaned and analyzed using statistical techniques, followed by the development of a Logistic Regression classification model.

The model is evaluated using multiple performance measures, including confusion matrix, accuracy, sensitivity, specificity, precision, F1-score, and ROC-AUC. Cross-validation and diagnostic analysis are also included to improve the reliability and understanding of the model.

---

## Future Scope

Future improvements can include:

* Comparing Logistic Regression with Random Forest, SVM, and Gradient Boosting.
* Using advanced missing-value imputation techniques.
* Performing feature selection.
* Handling class imbalance using resampling or class weights.
* Performing calibration analysis.
* Using external datasets for validation.
* Exploring nonlinear relationships using transformations or splines.

---

##  References

1. R `mlbench` package documentation – PimaIndiansDiabetes2 dataset.
2. R documentation for `glm()`, `t.test()`, `cor.test()`, `shapiro.test()`, and model diagnostics.
3. `caret` package documentation for training, cross-validation, data partitioning, and confusion matrix.
4. `pROC` package documentation for ROC curves and AUC analysis.
