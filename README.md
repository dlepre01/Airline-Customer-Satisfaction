
# Airline Passenger Satisfaction Analysis
![Airline](https://nmgprod.s3.amazonaws.com/media/files/60/6d/606d1f5063c95e0252650d864029ea93/cover_image_1682513560.jpeg.760x400_q85_crop_upscale.jpg)


# Airline Passenger Satisfaction Analysis

## Overview

This project presents an explanatory and predictive analysis of airline passenger satisfaction using a large-scale customer dataset.

The objective is to identify the key factors influencing customer satisfaction and to develop classification models capable of predicting whether a passenger is satisfied or neutral/dissatisfied.

The project was implemented through a structured KNIME workflow integrating data preprocessing, feature engineering, dimensionality reduction, and multiple supervised learning models.

---

## Business Context

In the aviation industry, customer experience is a strategic asset.

Passenger satisfaction directly impacts:

- customer loyalty
- brand perception
- competitive positioning
- long-term revenue stability

Understanding which variables most strongly influence satisfaction allows airlines to implement targeted service improvements.

---

## Dataset

The dataset is sourced from Kaggle (Airlines Customer Satisfaction Dataset) and contains approximately 130,000 records.

The data were collected by a company with a fictitious name (“Invistico”) to preserve passenger privacy.

### Feature Categories

**Flight-related variables**
- Seat Comfort
- Departure/Arrival Time Convenience
- Gate Location
- Baggage Handling
- Check-in Service
- Online Boarding
- Ease of Online Booking

**Service-related variables**
- Food and Drink
- Inflight Wi-Fi Service
- Inflight Entertainment
- Inflight Service
- On-board Service
- Leg Room
- Cleanliness

**Timing-related variables**
- Departure Delay
- Arrival Delay
- Flight Distance

**Passenger characteristics**
- Gender
- Customer Type (Loyal / Disloyal)
- Age
- Type of Travel (Business / Personal)
- Class (Business / Eco / Eco Plus)

**Target variable**
- Satisfaction (Satisfied / Neutral-Dissatisfied)

---

## Data Preprocessing

Key preprocessing steps included:

- Replacement of “0” values in ordinal features with missing values
- Conditional mean imputation based on Satisfaction class
- Feature engineering:
  - In-flight Delay (Arrival - Departure delay)
  - Arrival Delay per Distance ratio
- Removal of Arrival Delay due to high correlation with Departure Delay (ρ ≈ 0.97)
- Train/Test split (75% / 25%)
- Principal Component Analysis (PCA) for feature structure evaluation

Despite PCA explaining 86% of variance with 8 components, original features were retained to preserve interpretability.

---

## Models Implemented

The following supervised classification models were trained and compared:

- Multilayer Perceptron (MLP)
- K-Nearest Neighbors (KNN)
- Logistic Regression
- Random Forest

### Model Performance (Accuracy)

| Model               | Accuracy |
|---------------------|----------|
| Multilayer Perceptron | 0.925 |
| K-Nearest Neighbors | 0.914 |
| Logistic Regression | 0.892 |
| Random Forest       | 0.965 |

The Random Forest classifier achieved the best overall performance, with:

- Accuracy: 0.965
- AUC: 0.995
- High robustness and computational efficiency

---

## Feature Importance

Permutation-based feature importance analysis highlighted the most influential variables:

- Customer Type
- In-flight Wi-Fi Service
- Online Boarding
- Type of Travel

Key insight:
Passengers traveling for personal reasons and first-time customers show significantly higher dissatisfaction rates.

From a strategic standpoint, digital service quality (Wi-Fi, online boarding, booking experience) appears to be a decisive factor.

---

## Methodology Workflow

The KNIME workflow includes:

1. Data cleaning and preprocessing
2. Feature engineering
3. Train/test splitting
4. Model training and evaluation
5. Cross-validation comparison
6. Global feature importance analysis

---

## Key Insights

- Random Forest provides the best trade-off between interpretability, accuracy, and computational efficiency.
- KNN shows competitive accuracy but high computational cost.
- Logistic Regression underperforms compared to tree-based models.
- Digital service-related variables are stronger predictors than many physical service variables.

---

## Strategic Recommendations

Airlines should prioritize:

- Investment in high-quality in-flight Wi-Fi
- Optimization of online boarding and booking systems
- Targeted loyalty strategies for first-time customers
- Segmented service design based on type of travel

---

## Authors

Daniele Lepre  
Alice Anna Maria Brunazzi  
Alessandro Della Beffa
