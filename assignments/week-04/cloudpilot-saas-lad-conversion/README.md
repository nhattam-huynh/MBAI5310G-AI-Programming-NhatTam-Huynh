# Week 04 – Decision Tree Model and Business Interpretation
## Task Overview
Build a Decision Tree classification model to predict lead conversion for a fictional B2B SaaS company (CloudPilot CRM Solutions), and interpret the model results in a business context.

## Structure
```
week-04/
├── README.md
├── MBAI_5310_Assignment_4_Nhat_Tam_Huynh.ipynb
├── MBAI_5310_Assignment_4_Report_Nhat_Tam_Huynh.pdf
├── cloudpilot_saas_lead_conversion_dataset.xlsx
└── cloudpilot_saas_lead_conversion_business_plan.docx
```

## Files in This Folder

- MBAI_5310_Assignment_4_Nhat_Tam_Huynh.ipynb: main notebook for the task
- cloudpilot_saas_lead_conversion_dataset.xlsx: main dataset for the task
- cloudpilot_saas_lead_conversion_business_plan.docx: business plan document describing CloudPilot CRM Solutions

## Dataset or Input Source
The dataset used for this assignment was cloudpilot_saas_lead_conversion_dataset.xlsx, which contains 380 lead records for a fictional B2B SaaS company. Features include lead source, company profile information (industry, region, company size), budget and plan preferences, engagement signals (email engagement score, product demo attendance, trial activity), and sales signals (sales calls, decision-maker involvement, pain point fit score), along with a binary label indicating whether the lead ultimately converted to a paying customer.

## Methods Used
The assignment followed 4 main tasks:

- Understand the business problem — identify the prediction goal, target variable, and input features
- Prepare the data — inspect, clean, encode categorical variables, and split into training/testing sets
- Train a Decision Tree classification model — configure, fit, and evaluate the model using a confusion matrix and classification report
- Interpret the results in a business context — explain model performance, overfitting, feature importance, and limitations

## Key Results
The Decision Tree model (max_depth=4) achieved a training accuracy of 96.05% and a testing accuracy of 90.79%. The model demonstrated strong recall (97.18%) for the positive class, meaning it correctly identified nearly all leads that would convert. However, the dataset's severe class imbalance (355 "Yes" vs. 25 "No") caused the model to score zero true negatives, highlighting a structural weakness in identifying non-converting leads. The top predictive features were Trial_Days_Active, Email_Engagement_Score, and Pain_Point_Fit_Score.
Limitation
The dataset is heavily imbalanced toward the positive class, which inflates accuracy and prevents the model from learning to identify non-converting leads. Additionally, the data is synthetically generated and may not reflect real-world sales pipeline complexity.

## How to Run or Review
To review the notebook, follow the steps below:

- Download the files in this folder: [1] MBAI_5310_Assignment_4_Nhat_Tam_Huynh.ipynb [2] cloudpilot_saas_lead_conversion_dataset.xlsx
- Make sure to upload the dataset to the software you use to review this notebook
- Run the cells from top to bottom, consecutively
