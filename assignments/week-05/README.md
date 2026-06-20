# MBAI 5310 – Assignment 5: K-Means Clustering Analysis
**SwiftShip Delivery Delay Dataset**

---

## Overview

This assignment applies unsupervised machine learning (K-Means Clustering) to the SwiftShip delivery delay dataset. The goal is to discover natural groupings among shipments based on their operational characteristics, and translate those groups into actionable business insights for SwiftShip's logistics operations.

---

## Repository Contents

| File | Description |
|:-----|:------------|
| `MBAI_5310_Assignment_5_Nhat_Tam_Huynh.ipynb` | Main Jupyter Notebook with all code and outputs |
| `swiftship_delivery_delay_dataset.xlsx` | Raw dataset (355 shipment records, 16 columns) |
| `business_plan_swiftship_delivery_delay.pdf` | Business context document for the dataset |
| `README.md` | This file |

---

## Dataset Summary

- **Source:** SwiftShip Delivery Delay Dataset
- **Records:** 355 rows (350 after cleaning)
- **Columns:** 16 (mix of numerical and categorical)
- **Target variable:** `Delivery_Delayed` — excluded from clustering to avoid label leakage

**Features selected for clustering:**

| Feature | Description |
|:--------|:------------|
| `Shipping_Distance_km` | Distance the shipment travels |
| `Package_Weight_kg` | Weight of the package |
| `Order_Value_CAD` | Monetary value of the order |
| `Carrier_Rating` | Quality score of the assigned carrier (1–5) |
| `Previous_Delivery_Issues` | Count of past delivery problems |
| `Promised_Delivery_Days` | Committed delivery window in days |

---

## How to Run

1. Open `MBAI_3150_Assignment_5_Nhat_Tam_Huynh.ipynb` in Google Colab or Jupyter Notebook.
2. Update the `file_name` path in Cell 1 to point to your local copy of `swiftship_delivery_delay_dataset.xlsx`.
3. Run all cells from top to bottom (`Runtime → Run all` in Colab).
