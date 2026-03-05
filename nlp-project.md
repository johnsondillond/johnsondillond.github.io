---
layout: default
title: Stack Overflow NLP - Question Quality Analysis
---

{% include analytics.html %}

# Exploring Question Quality within CQA Platforms

**Collaborators:** [Dillon Johnson](https://github.com/johnsondillond) | [Reagan Hill](https://github.com/reagb) | [Teancum Price](https://github.com/TeancumDev)  
**Tech Stack:** Python | Scikit-learn | Polars | SQL | BERT | Transformers

---

## The Problem

On platforms like Stack Overflow, many technical questions receive little to no engagement. Our research aimed to identify what makes a question High Quality versus Low Quality and determine if a model trained on one platform could successfully classify questions on another through transfer learning.

## The Solution: Multi-Model Sentiment & Quality Analysis

We developed a pipeline to classify questions into three categories: HQ (High-quality posts without edits), LQ_EDIT (Low-quality but remaining open), and LQ_CLOSE (Low-quality posts closed by the community).

### Data Engineering & Extraction

* **Custom SQL Querying:** I used the StackExchange database to manually query and filter target datasets from five distinct CQA communities: Super User, Ask Ubuntu, Meta Stack Exchange, Mathematics, and Server Fault.
* **High-Speed Processing:** We used the Polars library for its speed in handling big data and reindexing feature columns across millions of rows.
* **Preprocessing:** Text data underwent filtering, tokenization, lemmatization, and stop-word removal, followed by TF-IDF vectorization.

### Modeling Approach

We experimented with several architectures to find the best balance of speed and accuracy:

* **The Ensemble:** A combination of Logistic Regression, Support Vector Classifier (SVC), and Random Forest.
* **Transformers:** We utilized a pretrained BERT model and a custom-trained Transformer model.

## Key Results & Findings

* **Winning Model:** The Transformer model performed best, achieving F1 scores in the high 80s when tested on Stack Overflow data.
* **Transferability:** While the ensemble model was more lightweight, we found that models trained on Stack Overflow could classify data from other CQAs with better-than-random results.
* **HQ Characteristics:** Analysis revealed that high-quality questions often include specific technical keywords like Kotlin, Docker, and Firebase, along with detailed explanations.

### Performance Metrics (Body Text)
| Model | Precision | Recall | F1 Score | AUC-ROC |
| :--- | :---: | :---: | :---: | :---: |
| **Ensemble** | **0.791** | **0.792** | **0.791** | **0.930** |
| Logistic Regression | 0.782 | 0.784 | 0.782 | 0.925 |
| Random Forest | 0.761 | 0.761 | 0.761 | 0.907 |

---

## Full Research Documentation
You can find the comprehensive breakdown of our hyperparameter tuning, CQA counts, and dataset distributions in the embedded report below.

<iframe src="/assets/documents/NLP_Class_Project.pdf" width="100%" height="600px" style="border:none;">
    <p>Your browser does not support PDFs. <a href="/assets/documents/NLP_Class_Project.pdf">Download the NLP Research PDF</a>.</p>
</iframe>

---

[View Source Code on GitHub](https://github.com/johnsondillond/NLPProject)