
# Spaceship Titanic - Kaggle Competition

This repository contains the solution for the [Spaceship Titanic Kaggle competition](https://www.kaggle.com/competitions/spaceship-titanic).  
The goal of this competition is to predict whether passengers aboard the Spaceship Titanic were transported to an alternate dimension following a collision with a spacetime anomaly.

## Table of Contents
- [Project Description](#project-description)
- [Dataset Description](#dataset-description)
- [Approach](#approach)
- [Results](#results)
---

## Project Description
The Spaceship Titanic was carrying approximately 13,000 passengers when it encountered a spacetime anomaly. This project leverages machine learning techniques to analyze passenger data and predict who was transported to another dimension.

---

## Dataset Description
The dataset includes personal records retrieved from the ship's damaged computer system.

### Files:
- `train.csv`: Training data (~8700 passengers).
- `test.csv`: Test data (~4300 passengers).
- `sample_submission.csv`: Sample submission format.

### Key Columns:
- **PassengerId**: Unique ID in the format `gggg_pp` (group and person).
- **HomePlanet**: Passenger's home planet.
- **CryoSleep**: Whether the passenger was in cryosleep.
- **Cabin**: Cabin details (`deck/num/side` format).
- **Destination**: Passenger's destination.
- **Age**: Passenger's age.
- **VIP**: Whether the passenger paid for VIP service.
- **RoomService, FoodCourt, ShoppingMall, Spa, VRDeck**: Billing amounts for luxury amenities.
- **Name**: Passenger's name.
- **Transported**: Target variable indicating if the passenger was transported.

---

## Approach
The solution involves the following steps:

### 1. Data Exploration
- Analyzed distributions and correlations in the training dataset.
- Visualized patterns and trends using Python libraries such as Matplotlib and Seaborn.

### 2. Handling Missing Values
- **CryoSleep**: Imputed missing values based on `RoomService` expenditure (likely in cryosleep if no expenditure).
- **HomePlanet**: Filled with the most frequent value within passenger groups.
- **Cabin**: Split into `Deck`, `Num`, and `Side`. Missing values were inferred based on group associations where possible.
- **Age**: Filled using the median value within each `HomePlanet`.
- **Expenditure Columns (RoomService, FoodCourt, ShoppingMall, Spa, VRDeck)**: Missing values were treated as zero, assuming no expenditure.

### 3. Feature Engineering
- Extracted meaningful features from `Cabin` (Deck, Num, Side).
- Created new features such as total expenditure and expenditure-to-age ratio.
- Encoded categorical features using one-hot encoding.

### 4. Model Development
- Tried several machine learning models, including:
  - Logistic Regression
  - Random Forest
  - Gradient Boosting (XGBoost, LightGBM)
- **XGBoost** was selected as the final model based on its superior performance.
- Tuned hyperparameters using GridSearchCV for optimal results.

### 5. Evaluation
- Evaluated models using accuracy as the metric.
- Validated models with cross-validation to ensure generalization.

---

## Results
The final model (XGBoost) achieved:
- **Training Accuracy**: 83%
- **Validation Accuracy**: 82%
- **Kaggle Submission Accuracy**: Competitive accuracy on the leaderboard.
