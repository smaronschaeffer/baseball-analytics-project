# Predicting MLB Pitcher Performance with Machine Learning

## Project Overview

How well can a pitcher's future performance be predicted from historical statistics?

This project explored that question using Major League Baseball pitching data from FanGraphs. The analysis compared machine-learning approaches for predicting Fielding Independent Pitching (FIP), an advanced metric designed to evaluate pitching performance based on outcomes pitchers have greater control over.

The project also investigated whether pitch selection and pitch-arsenal combinations were associated with pitcher effectiveness.

**Tools:** R, LASSO regression, Random Forest, ensemble modeling, hierarchical clustering, principal component analysis (PCA), data visualization

## Research Questions

- Which modeling approaches best predict a pitcher's next-season FIP using historical statistics?
- Which variables contribute most to predictive performance?
- Are particular pitch-arsenal combinations associated with lower FIP?
- What patterns distinguish groups of pitchers based on pitch usage?

## Data

The analysis used FanGraphs data collected through web scraping.

- **Training data:** 302 pitchers using statistics from the 2022–2024 seasons
- **Held-out test data:** 174 pitchers from the 2025 regular season
- **Predictors:** 31 variables covering performance statistics, pitcher characteristics, and pitch usage

Pitchers averaging fewer than 50 innings across the training period were excluded, as were variables with more than 50% missing data.

## Methodology

### 1. Exploratory Data Analysis

Used correlation matrices, histograms, and scatter plots to investigate relationships between pitching statistics and FIP and to guide feature selection.

### 2. Predictive Modeling

Compared three modeling approaches:

- **LASSO regression:** Used regularization and cross-validation to identify influential predictors while maintaining interpretability.
- **Random Forest:** Examined nonlinear relationships and variable importance.
- **Ensemble model:** Combined predictions from LASSO and Random Forest using multiple linear regression.

Models were evaluated on an internal 60/40 split and a separate held-out dataset from the 2025 season.

### 3. Pitch-Arsenal Analysis

Applied hierarchical clustering to six pitch-usage variables to group pitchers by pitch mix. Used PCA to explore the main dimensions of variation in pitch arsenals and their relationship with FIP.

## Key Findings

### Ensemble modeling achieved the lowest reported prediction error

The ensemble model outperformed LASSO and Random Forest on both evaluation sets. On the held-out 2025 data, the report recorded an MSE of 0.001 and an RMSE of 0.0301.

LASSO provided a more interpretable alternative, retaining predictors including AVG, WHIP, K-BB%, and BABIP. Random Forest highlighted additional potentially useful features, including WAR, wFB, and Stuff+.

### Pitch mix alone was not a strong predictor of effectiveness

Clustering did not reveal a strong overall relationship between pitch-arsenal diversity and FIP. PCA suggested that combinations of pitch types captured more variation in pitching styles than any single pitch type.

### Pitcher roles helped contextualize the results

Clusters with smaller pitch arsenals tended to contain more relievers and showed higher strikeout and walk rates. This suggests that pitching strategy and player role are important context when interpreting pitch-usage patterns.

## Limitations and Future Work

The training dataset was relatively small, and some predictors were correlated with components of FIP or with one another. The 50-inning eligibility threshold may also limit how well findings generalize to all pitchers.

Future work could explore additional seasons, incorporate more pitch-quality and batted-ball metrics, and investigate how pitcher characteristics and role affect predictive performance.

## Materials

- **Final report:** `baseball-analytics-report.pdf`
- **Code:** 'Final Project MATH-342 Statistical Machine Learning (2).qmd'

This project was completed as a collaborative final project for MATH-342: Statistical Machine Learning at Vassar College.
