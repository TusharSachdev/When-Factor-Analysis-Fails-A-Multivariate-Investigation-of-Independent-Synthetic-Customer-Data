# When Factor Analysis Fails  
## A Multivariate Investigation of Independent Synthetic Customer Data

---

## 📌 Project Objective

This project investigates whether latent behavioral structures exist within a large synthetic customer dataset using:

- Principal Component Analysis (PCA)
- Exploratory Factor Analysis (EFA)
- Statistical adequacy tests (KMO & Bartlett)
- Regularized regression (LASSO and Ridge)

Unlike many projects that assume latent factors exist, this study evaluates whether the data actually supports dimensional reduction.

---

## 📊 Dataset Description

The dataset consists of **50,000 synthetic customers** with behavioral, demographic, and engagement variables.

### Variables Included

**Demographics**
- Age
- Income

**Engagement Metrics**
- Website_Visits
- App_Opens
- Support_Tickets
- Avg_Session_Duration_Minutes

**Purchase Behavior**
- Total_Purchases
- Avg_Purchase_Value
- Last_Purchase_Days_Ago

**Feedback Metrics**
- Satisfaction_Score
- Likelihood_to_Recommend

**Target Variable**
- Churn (Binary)

All variables were generated independently using probabilistic distributions.

---

# 🔎 Principal Component Analysis (PCA)

- Data was standardized before analysis.
- 9 principal components were required to explain ~82% of total variance.
- Variance was evenly distributed across components.
- No dominant latent structure emerged.

### Interpretation

The need for a high number of components suggests weak inter-variable correlation and distributed variance structure.

---

# 🧪 Exploratory Factor Analysis (EFA)

Before applying Factor Analysis, statistical suitability tests were conducted.

---

## 1️⃣ Bartlett’s Test of Sphericity

- **p-value = 0.1303**
- Not statistically significant (p > 0.05)

Interpretation:

The correlation matrix is not significantly different from an identity matrix.  
Variables are largely uncorrelated.

---

## 2️⃣ KMO (Kaiser-Meyer-Olkin) Measure

- **KMO = 0.50**

Interpretation scale:
- > 0.90 → Superb
- > 0.80 → Great
- > 0.70 → Good
- > 0.60 → Acceptable
- < 0.60 → Weak

The dataset shows borderline sampling adequacy and weak shared variance.

---

## 3️⃣ Eigenvalue Analysis

Six factors had eigenvalues slightly above 1, but values were marginal (~1.01).

Rotated factor loadings showed:

- Website_Visits loading strongly on one factor
- Avg_Purchase_Value loading on another
- Last_Purchase_Days_Ago loading on another

Most other variables showed negligible cross-loadings.

---

# 📌 Key Statistical Conclusion

Factor Analysis is **not supported** for this dataset.

Reasons:

- Non-significant Bartlett’s test
- Weak KMO score
- Minimal shared variance
- Variables behave as statistically independent features

This outcome is expected because the dataset was generated using independent probabilistic processes.

---

# 🎓 Methodological Insight

This project demonstrates an important principle:

> Dimensionality reduction techniques must be justified by correlation structure.  
> Applying Factor Analysis without verifying assumptions can lead to misleading interpretations.

Rather than forcing latent constructs, this study pivots to predictive modeling.

---

# 📈 Regularized Regression Modeling

Given the independence of predictors, the next phase focuses on:

- LASSO Regression (L1 regularization)
- Ridge Regression (L2 regularization)

Objectives:

- Compare coefficient shrinkage behavior
- Assess predictive stability
- Evaluate multicollinearity impact
- Identify dominant predictors of churn or purchase behavior

Regularization provides a robust alternative when latent factor modeling is unsupported.

---

# 🛠 Tools Used

- Python
- Pandas
- NumPy
- Scikit-learn
- FactorAnalyzer
- Matplotlib / Seaborn

---

# 🚀 Future Extensions

- Bayesian regression with uncertainty quantification
- Synthetic dataset redesign with embedded latent factors
- Comparative study: Independent vs Correlated synthetic data
- Churn classification using SVM and tree-based models

---

# 👨‍💻 Author

Tushar Sachdev  
Data Science & Statistical Modeling  
Machine Learning | Bayesian Inference | Multivariate Analysis
