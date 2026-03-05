---
layout: default
title: March Madness Predictor - Machine Learning Analysis
---

{% include analytics.html %}

# The Ultimate March Madness Bracket

**Project Members:** * <img src="/assets/imgs/ehthemoohtoo.png" width="50" style="border-radius:50%; vertical-align:middle;"> [Eh The Moo Htoo](https://github.com/sawthai)
* <img src="/assets/imgs/ryangrotzky.png" width="50" style="border-radius:50%; vertical-align:middle;"> [Ryan Grotzky](https://github.com/grotzkyryan)
* <img src="/assets/imgs/dillonjohnson.png" width="50" style="border-radius:50%; vertical-align:middle;"> [Dillon Johnson](https://github.com/johnsondillond)

**Tech Stack:** Python | PyCaret | Scikit-learn | Matplotlib | Seaborn

---

## The Problem

Developing a reliable NCAA tournament prediction system is difficult because basketball is a momentum-based sport with high volatility. Traditional expert picks and eye-test methods often fail to capture complex patterns across decades of historical data. Furthermore, the one-week window between team selection and the tournament start makes real-time data collection and projection extremely challenging.

## The Solution: Data-Driven Prediction System

We developed a framework that leverages over 25 seasons of historical tournament data to identify consistent patterns in team success.

### Data Engineering and Methodology

* **Dataset Integration:** I integrated multiple NCAA datasets covering tournament results, team seeds, and matchup statistics.
* **Feature Engineering:** We implemented seed number normalization and created matchup features by calculating the differences in team statistics.
* **Three-Fold Analysis:** The project utilized a phased modeling approach:
  * **Early Phase:** Focuses on Round of 64 and Round of 32 games using seed win percentages.
  * **Middle Phase:** Targets Sweet 16 and Elite 8 matchups.
  * **Final Phase:** Covers Final Four and Championship matches.

### Model Benchmarking

We evaluated multiple machine learning models including Random Forest and XGBoost using PyCaret to quickly benchmark performance. Logistic Regression emerged as our most consistent model.

[Image of a machine learning model comparison chart]

## Key Results and Takeaways

* **Predictive Accuracy:** Our models achieved a consistent accuracy range of 65-70%. 
* **Performance Baseline:** Our system successfully outperformed the 50% accuracy typical of random or personal eye-test brackets.
* **Winning Projections:** In simulations, the model correctly identified high-seed winners such as Houston and Purdue for deep tournament runs.
* **Efficiency:** While sophisticated deep learning models may reach higher accuracy, our Logistic Regression model provided superior accuracy over traditional methods while remaining computationally efficient.

### Performance Summary (Logistic Regression)

| Metric | Score |
| :--- | :---: |
| **Accuracy** | **0.70** |
| Precision | 0.69 |
| Recall | 0.65 |
| F1-Score | 0.67 |

---

## Full Presentation Documentation

The following PDF contains our visual data analysis, tournament matchup win probabilities, and full simulation outputs.

<iframe src="/assets/documents/March_Madness_Predictor_Presentation.pdf" width="100%" height="600px" style="border:none;">
    <p>Your browser does not support PDFs. <a href="/assets/documents/March_Madness_Predictor_Presentation.pdf">Download the March Madness Presentation PDF</a>.</p>
</iframe>

---

[View Source Code on GitHub](https://github.com/johnsondillond/MarchMadnessPredictor)