# YT-shorts-virality-prediction-Comparison-of-machine-learning-models

**Overview**

This project researches the performance of three different machine learning models to predict the early stages of YouTube Shorts virality based on engagement data collected during the first 6 hours after upload. 
The three models being compared are:

- Logistic Regression
- Random Forest
- eXtreme Gradient Boosting
- 
The goal is to determine whether early engagement signals can be used to identify Shorts that are likely to achieve high engagement within the first 24 hours.

**Dataset**

The dataset consists of 856 YouTube Shorts, collected using the YouTube Data API v3. Each video was monitored during the first 6 hours after upload to collect early engagement metrics.

**Main Features**

- views_6h — views during the first 6 hours
- likes_6h — likes during the first 6 hours
- comments_6h — comments during the first 6 hours
- engagement_rate_6h — engagement rate based on likes and comments
- views_velocity — average views gained per hour
The target label is determined from the video's 24-hour performance using a virality score.

**Workflow**
YouTube Data API v3 -> Data Collection -> Data Cleaning -> Feature Engineering -> Virality Labeling -> Stratified K-fold Cross Validation -> Model Training -> Evaluation

**Virality Definition**
A virality score is calculated using:

V = 0.6 × views_24h
  + 0.3 × likes_24h
  + 0.1 × comments_24h

Videos above the selected percentile threshold are labeled as viral, while the remaining videos are labeled as non-viral.

**Machine Learning Models**
Three classification algorithms are evaluated:

1. Logistic Regression
Used as a linear baseline model for binary classification.

2. Random Forest
An ensemble of decision trees used to capture nonlinear relationships between early engagement features and virality.

3. XGBoost
A gradient boosting algorithm used to model more complex relationships in the engagement data.

**Evaluation Metrics**

The models are evaluated using:
- Accuracy
- Precision
- Recall
- F1-Score
- AUC-ROC

Stratified K-Fold Cross-Validation is used to maintain the proportion of viral and non-viral samples across folds.

**Result**

The models achieved the following performance:
                 Model  Accuracy  Precision  Recall  F1-Score  AUC-ROC
0  Logistic Regression     0.947      0.951   0.784     0.854    0.979
1        Random Forest     0.940      0.888   0.807     0.842    0.971
2              XGBoost     0.943      0.871   0.836     0.852    0.971

**Model Comparison (Bar Chart)**
<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/50c6ade1-63ef-4d48-a98b-0b0485f161f4" />

