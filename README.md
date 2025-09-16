# Engage2Value: From Clicks to Conversions (MLP Project T22025)

## Overview

This repository contains code and documentation for the Engage2Value Kaggle competition, focused on predicting **purchase value** from multi-session digital behavior using machine learning. The dataset includes anonymized user interactions such as session metrics, device details, marketing sources, and geography. The project aims to model these behaviors to estimate customer purchase potential[attached_file:1].

## Competition Details

- **Host:** IITM / Kaggle (MLP Project T22025)
- **Dates:** April 23, 2025 – July 28, 2025
- **Objective:** Forecast `purchaseValue` (total spend in a session) using digital touchpoint features
- **Metric:** `r2_score()` ([scikit-learn docs](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html))

## Repository Contents

- **Model.ipynb**  
  The main Jupyter Notebook containing data exploration, preprocessing steps, model selection, training, validation, and test prediction code. All core analysis is documented with outputs, plots, and commentary.

- **Train_data.gz**  
  The compressed training dataset used for building and validating regression models. It includes features and target variable to learn the relationship and train predictive algorithms.

- **test_data.csv**  
  The test dataset for which the target predictions are required. Models trained on the training data should generate predictions for this file; the true labels are not provided.

- **submission.csv**  
  The final submission file containing predicted target values for the test set, formatted as required by the competition (usually with columns like `id` and `target`). This is uploaded for scoring on the competition platform.

- **README.md**  
  This document, providing a summary of the repository contents, model workflow, and usage instructions.


## Dataset Description

### Key Feature Categories

- **User Behavior & Session Metrics:**  
  `totalHits`, `pageViews`, `totals.bounces`, `new_visits`, `totals.visits`, `sessionNumber`, `sessionStart`
- **Device & Technical Attributes:**  
  `deviceType`, `os`, `browser`, `screenSize`, `device.browserSize`, `device.language`, `browserMajor`
- **Traffic & Marketing Source:**  
  `userChannel`, `trafficSource`, `trafficSource.medium`, `trafficSource.keyword`, `trafficSource.campaign`, `trafficSource.adwordsClickInfo.*`, `trafficSource.adContent`, `trafficSource.referralPath`, `trafficSource.isTrueDirect`
- **Geographical Context:**  
  `geoNetwork.city`, `locationCountry`, `geoNetwork.continent`, `geoNetwork.subContinent`, `geoNetwork.metro`, `geoNetwork.region`, `geoCluster`, `locationZone`
- **Identifiers:**  
  `userId`, `sessionId`

**Target variable:** `purchaseValue` — total spend per session

## Workflow

 **Exploratory Data Analysis (EDA):**  
   Analyze session metrics, device features, channels, locations.
   
 **Feature Engineering:**  
   Prepare the features for regression tasks.
   
 **Model Building:**  
   - Start with a dummy baseline.
   - Experiment with regression models (Linear Regression, Random Forest, XGBoost, etc).
   - Tune and validate models.
 **Prediction:**  
   Generate predictions for the test set.
 **Submission:**  
   - Submit CSV in Kaggle format:  
     Columns: `id`, `target` (where target = predicted `purchaseValue`)
 **Evaluation:**  
   - Ranked using R² Score:
     \[
       R^2 = 1 - \frac{\sum_{i}(y_i - \hat{y}_i)^2}{\sum_{i}(y_i - \bar{y})^2}
     \]
