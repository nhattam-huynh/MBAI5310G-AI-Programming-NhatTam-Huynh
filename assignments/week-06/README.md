# MBAI 5310 – Assignment 6: Model Evaluation, Explainability, and Fairness
**Retail Product Return Dataset**

---

## Overview

This assignment applies supervised machine learning (a Decision Tree classifier) to the retail product return dataset. The goal is to predict whether a customer will request a return after placing an order, evaluate the model honestly using multiple metrics and cross-validation, explain its predictions with feature importance, SHAP, and LIME, and audit the model for fairness across customer subgroups — translating the results into a business-ready recommendation.

> **Key business insight:** the model performs well overall (88.5% recall), but accuracy varies by up to 30 percentage points across customer subgroups (e.g., Basic vs. Gold membership), raising fairness concerns that must be addressed before operational deployment.

---

## Repository Contents

| File | Description |
|:-----|:------------|
| `MBAI_5310_Assignment_6_Nhat_Tam_Huynh.ipynb` | Main Jupyter Notebook with all code, tables, and figures |
| `retail_product_return_dataset.xlsx` | Raw dataset (370 orders, 16 columns) |
| `MBAI_5310_Report_Assignment_6_Nhat_Tam_Huynh.pdf` | Final business report |
| `README.md` | This file |

---

## Dataset Summary

- **Source:** Retail Product Return Dataset
- **Records:** 370 rows, 16 columns
- **Target variable:** `return_requested` — 1 = return requested (70%), 0 = no return (30%); **imbalanced**
- **Identifier column (removed from modeling):** `order_id`
- **Group/fairness columns (excluded from model input, used only in Task 14):** `gender`, `age_group`, `region`, `membership_level`

**Features used for model training:**

| Feature | Description |
|:--------|:-------------|
| `customer_age` | Age of the customer |
| `order_value` | Monetary value of the order |
| `number_of_items` | Number of items in the order |
| `shipping_days` | Days taken for delivery |
| `discount_percent` | Discount applied to the order |
| `previous_returns` | Count of the customer's past returns |
| `customer_rating` | Post-delivery satisfaction rating |
| `product_category` | Category of the purchased product |
| `payment_method` | Payment method used |
| `delivery_issue_reported` | Whether a delivery issue was reported |

---

## Tasks Covered

| # | Task | # | Task |
|:--|:-----|:--|:-----|
| 1 | Load and Understand the Dataset | 9 | Cross-Validation |
| 2 | Define Features and Target Variable | 10 | Overfitting and Underfitting Analysis |
| 3 | Data Preprocessing | 11 | Feature Importance |
| 4 | Train/Test Split | 12 | SHAP Explanation |
| 5 | Train a Classification Model | 13 | LIME Explanation |
| 6 | Evaluate the Model | 14 | Fairness and Bias Reflection |
| 7 | Confusion Matrix | 15 | Final Business Interpretation |
| 8 | Error Analysis | | |

---

## Model and Key Results

- **Algorithm:** Decision Tree Classifier (`max_depth=3`, `random_state=42`)
- **Train/test split:** 80% / 20%, stratified (296 / 74 records)

| Metric | Score |
|:-------|:------|
| Accuracy | 74.3% |
| Precision | 78.0% |
| Recall | 88.5% |
| F1-Score | 82.9% |
| Mean Cross-Validation Accuracy | 75.4% (± 6.2%) |

**Explainability methods applied:** Feature Importance, SHAP (TreeExplainer), LIME (LimeTabularExplainer)

**Fairness columns evaluated:** Gender, Age Group, Region, Membership Level

**Final recommendation:** Suitable as an early prototype only — useful for flagging likely returns and identifying key risk drivers (return history, satisfaction rating, shipping time, discount level), but not yet ready for standalone operational deployment due to fairness gaps across customer subgroups and a meaningful False Negative rate.

---

## Dependencies

pandas

scikit-learn

matplotlib

shap

lime

openpyxl

---

## How to Run

1. Open `MBAI_5310_Assignment_6_Nhat_Tam_Huynh.ipynb` in Google Colab or Jupyter Notebook.
2. Update the dataset path in the first cell to point to your local copy of `retail_product_return_dataset.xlsx`.
3. Install the explainability libraries if not already available: `pip install shap lime`.
4. Run all cells from top to bottom (`Runtime → Run all` in Colab).
