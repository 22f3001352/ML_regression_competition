# Engage2Value: From Clicks to Conversions (MLP Project T22025)

## Overview

This repository contains code and documentation for the Engage2Value Kaggle competition, focused on predicting **purchase value** from multi-session digital behavior using machine learning. The dataset includes anonymized user interactions such as session metrics, device details, marketing sources, and geography. The project aims to model these behaviors to estimate customer purchase potential[attached_file:1].

## Competition Details

- **Host:** IITM / Kaggle (MLP Project T22025)
- **Dates:** April 23, 2025 – July 28, 2025
- **Objective:** Forecast `purchaseValue` (total spend in a session) using digital touchpoint features
- **Metric:** `r2_score()` ([scikit-learn docs](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html))

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

**Target variable:** `purchaseValue` — total spend per session[attached_file:1].

## Workflow

1. **Fork the repository** and work in your own notebook.
2. **Name notebook:** `<YourRollNo>-notebook-t22025` (eg: `22f3001352-notebook-t22025`).
3. **Share notebook** (view access, private) with: `iitmbscs2008p`.
4. **Exploratory Data Analysis (EDA):**  
   Analyze session metrics, device features, channels, locations.
5. **Feature Engineering:**  
   Prepare the features for regression tasks.
6. **Model Building:**  
   - Start with a dummy baseline.
   - Experiment with regression models (Linear Regression, Random Forest, XGBoost, etc).
   - Tune and validate models.
7. **Prediction:**  
   Generate predictions for the test set.
8. **Submission:**  
   - Submit CSV in Kaggle format:  
     Columns: `id`, `target` (where target = predicted `purchaseValue`)
9. **Evaluation:**  
   - Ranked using R² Score:
     \[
       R^2 = 1 - \frac{\sum_{i}(y_i - \hat{y}_i)^2}{\sum_{i}(y_i - \bar{y})^2}
     \]

## Usage

1. Clone/download the repository.
