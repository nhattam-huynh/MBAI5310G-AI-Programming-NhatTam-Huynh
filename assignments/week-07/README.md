# MBAI 5310 – Assignment 7: Applied Deep Learning
**Image Classification, Convolution, Pooling, and Validation**

---

## Overview

This assignment explores the foundational concepts behind convolutional neural networks (CNNs) and image classification. It answers ten short-answer questions drawn from the assigned readings, covering how CNNs process images differently from dense networks, the mechanics of convolution and pooling, activation functions, and the principles of model validation and overfitting — each explained in plain language with an original, realistic example.

> **Key concept:** CNNs outperform dense networks on image data because they preserve spatial relationships between pixels and reuse filters across positions (weight sharing), drastically reducing the number of parameters needed while still detecting patterns like edges, curves, and textures wherever they appear in an image.

---

## Repository Contents

| File | Description |
|:-----|:------------|
| `MBAI_5310_Report_Assignment_7_Nhat_Tam_Huynh.pdf` | Final report with all ten question answers, tables, and figures |
| `README.md` | This file |

---

## Topics Covered

| # | Question |
|:--|:---------|
| 1 | What does image classification mean? |
| 2 | Why is using a Dense Network not always a suitable choice for images? |
| 3 | In a CNN, what is convolution, and what does a filter or kernel do? |
| 4 | What is a feature map in a convolutional neural network? |
| 5 | Why is weight sharing used in CNNs? |
| 6 | How does the ReLU activation function work? |
| 7 | What is max pooling, and why is it used in CNNs? |
| 8 | Why are Fashion-MNIST images reshaped from 28×28 to 28×28×1? |
| 9 | What is the difference between training, validation, and test data? |
| 10 | What is overfitting, and what does a high training / low validation accuracy gap indicate? |

---

## Key Concepts and Results

- **Dense vs. Convolutional networks:** dense layers flatten images and lose spatial structure, forcing the network to relearn the same pattern at every position; CNNs preserve spatial layout and reuse filters, cutting parameter count significantly.
- **Convolution & filters:** a small kernel slides across the image, producing strong responses where its target pattern (e.g., edges) appears.
- **ReLU activation:** negative values are zeroed out, positive values pass through unchanged — example: `[-3, 0, 2, 5] → [0, 0, 2, 5]`.
- **Max pooling:** shrinks feature maps by keeping only the strongest value in each window, reducing computation and adding tolerance to small positional shifts.
- **Channel dimension:** grayscale images are reshaped to 28×28×1 (vs. 28×28×3 for RGB) so Conv2D layers know how many channels to expect.
- **Training/validation/test split:** training data updates model weights, validation data guides tuning and stopping decisions, test data gives a final unbiased performance estimate.
- **Overfitting:** a widening gap between rising training accuracy and flattening/declining validation accuracy signals the model has memorized training data rather than learned generalizable patterns.

---

## Dependencies

None — this is a conceptual short-answer report with illustrative tables and figures (no code execution required).

---

## How to Use

1. Open `MBAI_5310_Report_Assignment_7_Nhat_Tam_Huynh.pdf` to read the full set of answers, tables, and figures.
2. Each question is self-contained and can be referenced independently as a study guide for CNN fundamentals.
