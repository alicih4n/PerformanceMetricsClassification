# Performance Metrics Classification Workshop

## Use Case: MNIST Image Classification

This repository contains the completed workshop for the Performance Metrics Classification activity. The project focuses on evaluating binary classifiers (specifically differentiating the digit '5' from other digits) using the MNIST dataset.

## Workshop Overview

The primary goal of this workshop is to understand and implement various performance metrics for classification problems, moving beyond simple accuracy to more robust measures like Precision, Recall, F1 Score, and ROC/AUC.

**Key Activities:**
1.  **Data Preparation**: Loading the MNIST dataset and converting it into a binary classification problem ("Is this a 5?").
2.  **Model Training**: Training a Stochastic Gradient Descent (SGD) classifier.
3.  **Evaluation**:
    -   **Accuracy**: Analyzing why accuracy can be misleading on skewed datasets.
    -   **Confusion Matrix**: Visualizing True Positives, False Positives, True Negatives, and False Negatives.
    -   **Precision & Recall**: Understanding the trade-off between exactness and completeness.
    -   **F1 Score**: Calculating the harmonic mean of precision and recall.
    -   **Precision-Recall Curve**: Visualizing the trade-off at different thresholds.
    -   **ROC Curve & AUC**: Evaluating the true positive rate vs. false positive rate.
4.  **Model Comparison**: Comparing SGD with a RandomForestClassifier.

## Summary of Insights (Talking Points)

Based on the "To the student" sections in the notebook:

-   **Classification Problem**: Defined as identifying which category an observation belongs to. A **Classifier** is the algorithm performing this mapping.
-   **Preprocessing**: We converted the multiclass target vector (`y`) into a boolean vector (`y_train_5`). `True` represents the digit 5, and `False` represents all other digits. The feature matrix `X` remained unchanged as the pixel data is the same for binary or multiclass tasks.
-   **Cross-Validation**: Used `cross_validate` with `cv=3` to split the training data into 3 folds, training the model 3 times and testing on the held-out fold each time. This provides a more robust estimate of model performance than a single train/test split.
-   **The Accuracy Trap**:
    -   The SGD classifier achieved ~95-96% accuracy.
    -   However, since only ~10% of the images are '5's, a naive classifier that *always* predicts "Not-5" would achieve ~90% accuracy.
    -   This highlights that accuracy is a poor metric for imbalanced datasets (skewed classes).
-   **F1 Score**: Calculated manually using TP, FP, and FN. The harmonic mean (F1) is preferred over the arithmetic mean because it penalizes extreme values (e.g., if Recall is very low, F1 will be low, unlike the arithmetic mean).
-   **Random Forest Superiority**: The Random Forest classifier significantly outperformed the SGD classifier, achieving an AUC of ~0.99 compared to SGD's ~0.96, demonstrating the power of ensemble methods for this task.

## Repository Contents

-   `PerformanceMetricsClassification.ipynb`: The main workshop notebook with code, visualizations, and answers to student questions.
-   `requirements.txt`: Python dependencies.

## Team Members

-   **Name**: [Student Name]
-   **Student ID**: [Student ID]
-   **GitHub Repo**: https://github.com/alicih4n/PerformanceMetricsClassification
