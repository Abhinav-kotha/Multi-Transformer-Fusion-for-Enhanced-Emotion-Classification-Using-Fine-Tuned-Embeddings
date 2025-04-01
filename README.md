# Multi-Transformer-Fusion-for-Enhanced-Emotion-Classification-Using-Fine-Tuned-Embeddings

## 1. Introduction
Emotion classification in text is a fundamental problem in Natural Language Processing (NLP). Traditional models often struggle to capture nuanced emotional expressions, motivating the use of **transformer-based models** such as **BERT, RoBERTa, and XLNet**. This project explores how **multi-transformer fusion techniques** can enhance classification accuracy.

## 2. Dataset
### Dataset Used: Emotion Dataset
![image](https://github.com/user-attachments/assets/e6daff42-cb74-42bf-92f7-07f2f9e012be)

- The dataset consists of 20000 text samples labeled with different emotions(sadness, joy, love, anger, fear, suprise).
- It has been preprocessed to remove noise and standardize text formatting.
- The dataset is split into **training, validation, and test sets** to ensure robust evaluation.
- The training dataset contains 16,000 samples, structured for diversity:
  - BERT: 1-8000 indexed samples
  - RoBERTa: 2001-10,000 indexed samples
  - XLNet: 4001-12,000 indexed samples

## 3. Methodology
### Step 1: Fine-Tuning Transformer Models
- Fine-tuned **BERT, RoBERTa, and XLNet** on a subset of the dataset.
- Only the **last three layers** of each model were fine-tuned.
- Individual model accuracies:
  - **BERT:** 92.95%
  - **RoBERTa:** 92.45%
  - **XLNet:** 80.55%

### Step 2: Extracting Embeddings
- Extracted **last-layer embeddings** from each fine-tuned model.
- These embeddings were used as input for subsequent fusion techniques.

### Step 3: Fusion Techniques for Classification
#### Model 1: Stacking Classifier Approach
- Concatenated embeddings from **BERT, RoBERTa, and XLNet**.
- Passed them into a **neural network** for final classification.
- **Accuracy:** 94.01%

#### Model 2: Attention-Based Fusion
- Used an **attention mechanism** to select important features from each embedding.
- The final embedding had the **same size as a single model’s embedding**.
- Passed the refined embedding into a **neural network** for classification.
- **Accuracy:** 95.67%

## 4. Explainability with SHAP
- Applied **SHAP (SHapley Additive exPlanations)** to Model 1.
- Identified the most influential words in determining predictions.

## 5. Results & Comparison
| Model | Accuracy | Precision | Recall | F1 Score |
|--------|---------|-----------|--------|----------|
| BERT | 92.95% | 93.04% | 92.95% | 92.98% |
| RoBERTa | 92.45% | 92.67% | 92.45% | 92.46% |
| XLNet | 80.55% | 80.61% | 80.55% | 80.51% |
| Stacking Classifier | 94.01% | 94.05% | 94% | 94.02% |
| Attention-Based Fusion | **95.67%** | **95.38%** | **94.94** | **95.16%** |

- For detailed information you can see Per Class Metrics for each model
- The **attention-based fusion approach outperformed other models**, demonstrating the effectiveness of feature selection.

## 6. Conclusion
- **Key Findings:**
  - Attention-based fusion improves classification accuracy.
  - Combining multiple transformer embeddings enhances performance over individual models.
- **Future Work:**
  - Experimenting with additional transformer models.
  - Exploring other interpretability techniques to enhance explainability.

---
This project demonstrates the power of **multi-transformer fusion** in emotion classification and provides insights into how explainability can be integrated into modern NLP models.

