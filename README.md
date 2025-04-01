# Multi-Transformer-Fusion-for-Enhanced-Emotion-Classification-Using-Fine-Tuned-Embeddings

# Multi-Transformer Fusion for Enhanced Emotion Classification Using Fine-Tuned Embeddings

## 1. Introduction
Emotion classification in text is a fundamental problem in Natural Language Processing (NLP). Traditional models often struggle to capture nuanced emotional expressions, motivating the use of **transformer-based models** such as **BERT, RoBERTa, and XLNet**. This project explores how **multi-transformer fusion techniques** can enhance classification accuracy.

## 2. Dataset
### Dataset Used: Emotion Dataset
- The dataset consists of text samples labeled with different emotions.
- It has been preprocessed to remove noise and standardize text formatting.
- The dataset is split into **training, validation, and test sets** to ensure robust evaluation.

## 3. Methodology
### Step 1: Fine-Tuning Transformer Models
- Fine-tuned **BERT, RoBERTa, and XLNet** on a subset of the dataset.
- Only the **last three layers** of each model were fine-tuned.
- Individual model accuracies:
  - **BERT:** 92%
  - **RoBERTa:** 92%
  - **XLNet:** 80%

### Step 2: Extracting Embeddings
- Extracted **last-layer embeddings** from each fine-tuned model.
- These embeddings were used as input for subsequent fusion techniques.

### Step 3: Fusion Techniques for Classification
#### Model 1: Stacking Classifier Approach
- Concatenated embeddings from **BERT, RoBERTa, and XLNet**.
- Passed them into a **neural network** for final classification.
- **Accuracy:** 94%

#### Model 2: Attention-Based Fusion
- Used an **attention mechanism** to select important features from each embedding.
- The final embedding had the **same size as a single model’s embedding**.
- Passed the refined embedding into a **neural network** for classification.
- **Accuracy:** 95.6%

## 4. Explainability with SHAP
- Applied **SHAP (SHapley Additive exPlanations)** to Model 1.
- Identified the most influential words in determining predictions.

## 5. Results & Comparison
| Model | Accuracy | Precision | Recall | F1 Score |
|--------|---------|-----------|--------|----------|
| BERT | 92% | 92% | 92% | 92% |
| RoBERTa | 92% | 92% | 92% | 92% |
| XLNet | 80% | 80% | 80% | 80% |
| Stacking Classifier | 94% | 94% | 94% | 94% |
| Attention-Based Fusion | **95.6%** | **95.6%** | **95.6%** | **95.6%** |

- The **attention-based fusion approach outperformed other models**, demonstrating the effectiveness of feature selection.

## 6. Conclusion
- **Key Findings:**
  - Attention-based fusion improves classification accuracy.
  - Combining multiple transformer embeddings enhances performance over individual models.
- **Future Work:**
  - Experimenting with additional transformer models.
  - Exploring other interpretability techniques to enhance explainability.
![image](https://github.com/user-attachments/assets/7b7c6ac9-a9be-49db-9a37-c2745ad74e6f)

---
This project demonstrates the power of **multi-transformer fusion** in emotion classification and provides insights into how explainability can be integrated into modern NLP models.

