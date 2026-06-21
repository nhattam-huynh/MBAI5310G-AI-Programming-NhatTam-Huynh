# MBAI 5310G – Assignment 8: NLP Pipeline and Text Classification
**Customer Review Sentiment Classification for MapleMart**

---

## Overview

This assignment builds a complete Natural Language Processing pipeline in Python to classify customer review sentiment for a Canadian retailer, MapleMart. The work covers loading and inspecting a labeled review dataset, cleaning and normalizing raw text, exploring word frequency patterns, extracting linguistic structure with POS tagging and Named Entity Recognition, converting text into TF-IDF numeric features, and training and evaluating a Naive Bayes sentiment classifier — translating the results into a business-ready recommendation.

> **Key business insight:** the model achieves 100% accuracy on the held-out test set, but this reflects the templated, repetitive nature of the dataset (21 of 24 test reviews were near-duplicates of training reviews) rather than true generalization. The pipeline and business framing are sound, but the model needs validation on a larger, more naturally written dataset before production use.

---

## Repository Contents

| File | Description |
|:-----|:------------|
| `MBAI_5310G_Assignment_8_Nhat_Tam_Huynh.ipynb` | Main Jupyter Notebook with all code, tables, and figures |
| `NLP_Dataset_1_Customer_Review_Sentiment.xlsx` | Raw dataset (120 customer reviews, 8 columns) |
| `MBAI_5310_Report_Assignment_8_Nhat_Tam_Huynh.pdf` | Final business report |
| `README.md` | This file |

---

## Dataset Summary

- **Source:** MapleMart Customer Review Sentiment Dataset
- **Records:** 120 rows, 8 columns
- **Target variable:** `SentimentLabel` — Positive, Neutral, or Negative; **perfectly balanced** (40/40/40)
- **Identifier column:** `ReviewID`
- **Metadata columns (not used as model input):** `ReviewDate`, `Channel`, `City`, `ProductCategory`, `CustomerSegment`

**Main text column:**

| Feature | Description |
|:--------|:-------------|
| `ReviewText` | Raw customer review text used for classification |
| `CleanedText` | Lowercased, punctuation-stripped, stopword-removed, lemmatized version of `ReviewText` (created during preprocessing) |

---

## Tasks Covered

| # | Task | # | Task |
|:--|:-----|:--|:-----|
| 1 | Load and Inspect the Dataset | 5 | Feature Extraction (TF-IDF) |
| 2 | Text Preprocessing | 6 | Build a Text Classification Model |
| 3 | Exploratory Text Analysis | 7 | Model Evaluation |
| 4 | POS Tagging and Named Entity Recognition | 8 | Business Interpretation |

---

## Pipeline and Key Results

- **Preprocessing steps:** lowercasing, hashtag/punctuation/number removal, tokenization, stopword removal, lemmatization (NLTK)
- **Feature extraction:** TF-IDF, max 200 features → resulting matrix shape (120, 119)
- **Algorithm:** Multinomial Naive Bayes
- **Train/test split:** 80% / 20%, stratified (96 / 24 records)

| Metric | Score |
|:-------|:------|
| Accuracy | 100% |
| Precision (all classes) | 1.00 |
| Recall (all classes) | 1.00 |
| F1-Score (all classes) | 1.00 |

**Explainability methods applied:** Word frequency analysis, POS tagging, Named Entity Recognition (NLTK `pos_tag`, `ne_chunk`)

**Top frequent words:** item, maplemart, product, arrived, order, price, accessory, delivery, quality — centered on brand, product, and delivery/quality experience

**Final recommendation:** The pipeline and business framing (monitoring delivery and quality complaints) are directly transferable to MapleMart's real review stream, but the model's perfect test accuracy is inflated by near-duplicate reviews between train and test sets. Before production deployment, validate on a larger, more naturally written dataset with no train/test phrasing overlap.

---

## Dependencies

pandas

nltk

scikit-learn

matplotlib

openpyxl

---

## How to Run

1. Open `MBAI_5310G_Assignment_8_Nhat_Tam_Huynh.ipynb` in Google Colab or Jupyter Notebook.
2. Update the dataset path in the first cell to point to your local copy of `NLP_Dataset_1_Customer_Review_Sentiment.xlsx`.
3. Install NLTK and download required corpora if not already available: `pip install nltk scikit-learn` then run the `nltk.download(...)` calls in the notebook (punkt, stopwords, wordnet, averaged_perceptron_tagger_eng, maxent_ne_chunker_tab, words).
4. Run all cells from top to bottom (`Runtime → Run all` in Colab).
