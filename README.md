# Predicting Customer Spending Using Nested Cross-Validation

This project explores numeric prediction models to estimate customer spending behavior in response to a marketing catalog campaign. The dataset includes both whether a purchase was made (`Purchase`) and the amount spent (`Spending`), allowing us to train models under two setups: full dataset and a restricted dataset with only purchasing customers.

---

## Dataset Overview

- **Attributes**: Includes consumer demographics and behavioral variables
- **Target Variables**:
  - `Spending`: Continuous variable (amount spent in dollars)
  - `Purchase`: Binary variable (1 = made a purchase, 0 = did not)

---

## Project Tasks

### Task (a): Predict Spending (All Records)

- Built regression models excluding the `Purchase` field
- Techniques used:
  - **Linear Regression**
  - **k-NN Regression**
  - **Regression Tree**
  - **SVM Regression**
  - **Neural Network Regression**
  - **Ensembling models**
- **Nested Cross-Validation** was used to select hyperparameters and reduce overfitting
- Evaluated based on RMSE
- Compared performance across techniques and preprocessing strategies (e.g., normalization)

### Task (b): Predict Spending (Purchase = 1 Only)

- Subsetted dataset to only include records where `Purchase = 1`
- Re-trained the same models and repeated evaluation using **nested CV**
- This approach focused on improving predictive accuracy where a purchase was actually made

### Task (c): Model Comparison Between (a) and (b)

- Compared predictive performance across tasks for each model
- Found that models in **task (b)** performed better due to:
  - Reduced noise from `Spending = 0` entries
  - Clearer signal from purchasing customer behavior

---

## Key Takeaways

- **Nested cross-validation** played a key role in unbiased model selection and generalization
- **SVM and Tree-based models** showed strong performance after tuning
- **Neural networks** performed well but required careful regularization and normalization
- **Restricted dataset (task b)** generally led to more stable and accurate models

---

## Best Model Summary

| Dataset       | Model           | RMSE   |
|---------------|------------------|--------|
| Full (a)      | Neural Network   | 149.37  |
| Restricted (b)| XGBoost    | 125.32  |

---
