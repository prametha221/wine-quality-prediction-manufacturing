# Quality Prediction of Manufactured Wine Using Physicochemical Properties

## 1. Project Overview

This project focuses on predicting wine quality during the manufacturing process using machine learning techniques. The system uses physicochemical properties of wine as input parameters and classifies the wine into quality categories.

The project uses the UCI Wine Quality dataset and applies data preprocessing, feature engineering, machine learning model development, and model evaluation to develop a quality prediction system.

---

## 2. Problem Statement

Wine quality assessment is an important quality-control activity in the manufacturing process. Traditional quality assessment may depend on laboratory analysis and expert evaluation of physicochemical properties. This project aims to develop a machine learning-based system that can predict wine quality from measurable physicochemical properties and support faster and more consistent quality monitoring during manufacturing.

---

## 3. Objectives

- To analyze physicochemical properties associated with wine quality.
- To preprocess and clean the wine quality dataset.
- To perform exploratory data analysis and data profiling.
- To create meaningful derived features through feature engineering.
- To develop Random Forest and XGBoost classification models.
- To evaluate the models using Accuracy, Precision, Recall, and F1 Score.
- To compare the performance of the machine learning models.
- To identify important features influencing wine quality prediction.
- To develop a final wine quality prediction system.

---

## 4. Domain

**Domain:** Quality and Yield Prediction

**Industry:** Wine Manufacturing / Food and Beverage Manufacturing

**Manufacturing Objective:** Quality monitoring and quality prediction

---

## 5. Dataset

### Dataset Name

Wine Quality Dataset

### Dataset Source

UCI Machine Learning Repository

### Dataset Used

Red Wine Quality Dataset

### Dataset Characteristics

- Samples: 1599
- Original features: 11 physicochemical properties
- Target variable: Quality
- Machine learning task: Binary classification after quality-class transformation
- Feature type: Numerical

### Physicochemical Properties

The dataset contains the following properties:

1. Fixed acidity
2. Volatile acidity
3. Citric acid
4. Residual sugar
5. Chlorides
6. Free sulfur dioxide
7. Total sulfur dioxide
8. Density
9. pH
10. Sulphates
11. Alcohol

---

## 6. Target Variable

The original wine quality score is transformed into a binary classification target called `quality_class`.

The target classes are:

- `0` – Low Quality
- `1` – Good Quality

This transformation allows the project to perform binary classification.

---

## 7. Project Workflow

The project follows the following machine learning workflow:

Dataset
↓
Data Profiling
↓
Data Cleaning
↓
Exploratory Data Analysis
↓
Quality Class Creation
↓
Feature Engineering
↓
Train-Test Split
↓
Random Forest
↓
XGBoost
↓
Model Evaluation
↓
Model Comparison
↓
Feature Importance
↓
Final Quality Prediction

---

## 8. Data Preprocessing

The dataset was analyzed for:

- Missing values
- Duplicate records
- Data types
- Statistical properties
- Class distribution

Duplicate records were removed during preprocessing before model development.

After preprocessing, the cleaned dataset was used for feature engineering and machine learning.

---

## 9. Feature Engineering

Three additional features were created from the original physicochemical properties.

### 9.1 Sulfur Dioxide Ratio

The sulfur dioxide ratio is calculated using:

Free Sulfur Dioxide / (Total Sulfur Dioxide + 1)

This feature represents the relationship between free and total sulfur dioxide.

### 9.2 Acid Balance

The acid balance is calculated as:

Fixed Acidity + Citric Acid - Volatile Acidity

This combines multiple acidity-related properties into a derived feature.

### 9.3 Alcohol-to-Density Ratio

The alcohol-to-density ratio is calculated as:

Alcohol / Density

This represents the relationship between alcohol concentration and wine density.

After feature engineering, the model uses 14 input features.

---

## 10. Machine Learning Models

Two supervised machine learning classification models were developed.

### Random Forest

Random Forest is an ensemble learning algorithm that combines multiple decision trees to make predictions.

It was used to classify wine samples into Low Quality or Good Quality categories.

### XGBoost

XGBoost is a gradient boosting machine learning algorithm that builds a sequence of decision trees to improve predictive performance.

It was used as a second model for comparison with Random Forest.

---

## 11. Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score

### Final Model Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Random Forest | 77.21% | 79.29% | 77.08% | 78.17% |
| XGBoost | 74.26% | 76.81% | 73.61% | 75.18% |

Random Forest achieved better performance than XGBoost across the evaluated metrics and was selected as the final model.

---

## 12. Feature Importance

Feature importance analysis was performed using the Random Forest model to identify the physicochemical and engineered features that contribute most to the model's prediction.

The feature importance visualization is available in:

`results/feature_importance.png`

---

## 13. Model Comparison

The performance comparison between Random Forest and XGBoost is available in:

`results/model_comparison.png`

The comparison shows that Random Forest achieved higher performance than XGBoost on the evaluated metrics.

---

## 14. Final Prediction

The final system accepts the 11 original physicochemical measurements of a wine sample.

The three engineered features are automatically calculated from these measurements.

The final Random Forest model then predicts:

- Good Quality
- Low Quality

Example prediction:

**Predicted Wine Quality: Good Quality**

---

## 15. Manufacturing Use Case

The proposed system can be used as a quality-monitoring support system in wine manufacturing.

During the manufacturing process, physicochemical properties can be measured through laboratory or process-quality measurements. These measurements can be provided to the trained machine learning model to obtain a predicted quality class.

The prediction can support quality-control personnel in identifying samples that may require further inspection or quality evaluation.

---

## 16. Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- Jupyter Notebook
- GitHub

---

## 17. Repository Structure

```text
wine-quality-prediction-manufacturing/
│
├── data/
│   ├── winequality-red.csv
│   └── winequality.names
│
├── notebooks/
│   └── quality_prediction.ipynb
│
├── results/
│   ├── model_comparison.png
│   └── feature_importance.png
│
├── README.md
└── requirements.txt
