# Week 04 Part 2 – Decision Tree Model and Business Interpretation
## Task Overview
Build a Decision Tree classification model to predict support ticket escalation for a fictional B2B health technology company (CareFirst Health Solutions), and interpret the model results in a business context.
## Structure
```
week-04-part-2/
├── README.md
├── MBAI_5310_Assignment_4_Part_2_Nhat_Tam_Huynh.ipynb
├── MBAI_5310_Assignment_4_Part_2_Report_Nhat_Tam_Huynh.pdf
└── carefirst_support_escalation_dataset.xlsx
```
## Files in This Folder

- MBAI_5310_Assignment_4_Part_2_Nhat_Tam_Huynh.ipynb: main notebook for the task
- MBAI_5310_Assignment_4_Part_2_Report_Nhat_Tam_Huynh: the report for the output
- carefirst_support_escalation_dataset.xlsx: main dataset for the task

## Dataset or Input Source
The dataset used for this assignment was carefirst_support_escalation_dataset.xlsx, which contains 253 support ticket records for a fictional B2B health technology company. Features include customer profile information (customer tier, business size, subscription plan), ticket details (support channel, issue category, product type), engagement and history signals (prior tickets in the last 90 days, days since purchase, last CSAT score), and operational signals (response time, customer value, sentiment score, agent workload, resolution estimate), along with a binary label indicating whether the ticket was ultimately escalated.
Methods Used
## The assignment followed 4 main tasks:

- Understand the business problem — identify the prediction goal, target variable, and input features
- Prepare the data — inspect, remove duplicates, clean missing values, encode categorical variables using OneHotEncoder via ColumnTransformer, and split into training/testing sets
- Train a Decision Tree classification model — configure, fit, and evaluate the model using a confusion matrix and classification report; demonstrate overfitting with an unconstrained tree
- Interpret the results in a business context — explain model performance, overfitting, feature importance, and limitations

## Key Results
The Decision Tree model (max_depth=4) achieved a training accuracy of 82% and a testing accuracy of 60%. While the model correctly identified non-escalated tickets reasonably well (recall of 84% for the "No" class), it struggled significantly with the positive class, capturing only 17% of actual escalations (recall for "Yes"). The confusion matrix shows 15 false negatives out of 18 actual escalations, making false negatives the primary concern for this business problem. The unconstrained tree confirmed severe overfitting with 100% training accuracy but only 40% testing accuracy. Top predictive features included Sentiment_Score, Agent_Workload, Response_Time_Hours, and Prior_Tickets_90D.
## Limitation
The dataset contains a moderate class imbalance (162 "No" vs. 88 "Yes") and a small training set of only 200 records, which limits the model's ability to learn the escalation boundary reliably. Additionally, the data is synthetically generated and may not reflect real-world support ticket complexity.
## How to Run or Review
To review the notebook, follow the steps below:
- Download the files in this folder: [1] MBAI_5310_Assignment_4_Part_2_Nhat_Tam_Huynh.ipynb [2] carefirst_support_escalation_dataset.xlsx
- Make sure to upload the dataset to the software you use to review this notebook
- Run the cells from top to bottom, consecutively
