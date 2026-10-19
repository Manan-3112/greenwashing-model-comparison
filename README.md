# Greenwashing Detection: Transformer Model Comparison

A comparative NLP study evaluating multiple transformer-based language models for detecting greenwashing in corporate sustainability reports.

## Overview

This project compares the performance of four transformer models for binary greenwashing classification:

- BERT Base
- BERT Mini
- RoBERTa Base
- DistilBERT

All models are trained and evaluated using the same dataset, label-generation strategy, data split, and evaluation metrics to provide a fair comparison.

## Objective

The objective is to determine which transformer architecture provides the best performance for detecting greenwashing in corporate sustainability report text.

## Dataset & Labeling

The project uses a preprocessed corporate sustainability report dataset.

A binary `greenwashing_label` is created using the median of the `total_score` column:

- `0` → Non-Greenwashing
- `1` → Greenwashing

The dataset is split using stratified sampling:

- 80% Training
- 10% Validation
- 10% Testing

## Models Compared

### 1. BERT Base
`bert-base-uncased`

### 2. BERT Mini
`prajjwal1/bert-mini`

### 3. RoBERTa Base
`roberta-base`

### 4. DistilBERT
`distilbert-base-uncased`

## Training Configuration

The models use a common training configuration to make the comparison consistent:

- Learning Rate: `2e-5`
- Batch Size: `16`
- Maximum Sequence Length: `512`
- Maximum Epochs: `15`
- Early Stopping Patience: `2`
- Model Selection Metric: Validation Accuracy

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

## Model Comparison

The notebook compares the four models across multiple performance metrics and generates visualizations including:

- Overall model performance comparison
- Per-class F1-score comparison
- Confusion matrices
- Dataset class distribution
- Radar chart of model performance

The comparison values reported in the notebook are:

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| BERT Base | 0.7471 | 0.75 | 0.75 | 0.75 |
| BERT Mini | 0.50 | 0.25 | 0.50 | 0.33 |
| RoBERTa Base | 0.74 | 0.75 | 0.74 | 0.74 |
| DistilBERT | 0.78 | 0.78 | 0.78 | 0.78 |

Based on the comparison values included in the notebook, DistilBERT achieves the highest overall performance among the four evaluated models.

## Technologies

- Python
- PyTorch
- Hugging Face Transformers
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Repository Structure

```text
greenwashing-model-comparison/
│
├── greenwashing_model_comparison.ipynb
├── README.md
└── requirements.txt
