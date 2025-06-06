# 🐭 Vole Skull Classification

This project explores how to classify vole species (*multiplex* vs *subterraneus*) using skull measurements (length, height, and width). I used logistic regression models and validated their performance using cross-validation and bootstrapping.

## 📊 Tools & Skills
- **Languages**: R
- **Libraries**: ggplot2, GGally, dplyr, boot, data.table
- **Techniques**: Logistic regression, outlier handling, bootstrapping, cross-validation, model comparison

## 🧼 Data Cleaning
- Removed duplicate entries and incomplete rows
- Identified and replaced extreme outliers using column medians

## 🔍 EDA (Exploratory Data Analysis)
- Used boxplots and pairwise plots to explore relationships between features
- Found clear differences in skull height and length across species

## 🧠 Modeling & Evaluation
- Built 7 logistic regression models using different feature sets
- Compared models using LOOCV to identify the one with the lowest error rate
- Used bootstrapping to validate model deviance and test binomial assumptions

## ✅ Results
- The model using skull **height and width** had the best balance of accuracy and simplicity with an error rate of 0.0973.
- The model that utilized all three features and was second best with an error rate of 0.0997
- Confusion matrix showed strong classification ability between species

## 📁 Files
- `vole_skull_classification/Project Code: Full RMarkdown analysis and code
- `README.md`: This file

---


