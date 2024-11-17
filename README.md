
# Spaceship Titanic - Kaggle Competition

This repository contains the solution for the [Spaceship Titanic Kaggle competition](https://www.kaggle.com/competitions/spaceship-titanic). 
The goal of this competition is to predict whether passengers aboard the Spaceship Titanic were transported to an alternate dimension following a collision with a spacetime anomaly.

## Table of Contents
- [Project Description](#project-description)
- [Dataset Description](#dataset-description)
- [Approach](#approach)
- [Results](#results)
- [How to Run](#how-to-run)
- [Acknowledgements](#acknowledgements)

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
- Addressed missing values through imputation.

### 2. Feature Engineering
- Extracted meaningful features from `Cabin` (Deck, Num, Side).
- Encoded categorical features using one-hot encoding.

### 3. Model Development
- Tried several machine learning models:
  - Logistic Regression
  - Random Forest
  - Gradient Boosting (XGBoost, LightGBM)
- Tuned hyperparameters using GridSearchCV.

### 4. Evaluation
- Evaluated models using accuracy as the metric.
- Selected the best-performing model based on cross-validation results.

---

## Results
The final model achieved:
- **Training Accuracy**: 85%
- **Validation Accuracy**: 83%
- Submission results: Achieved competitive accuracy on the Kaggle leaderboard.

---

## How to Run
### Prerequisites
1. Install Python (>= 3.8) and required libraries.
2. Install dependencies from `requirements.txt`:
   ```bash
   pip install -r requirements.txt
   ```

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/spaceship-titanic.git
   cd spaceship-titanic
   ```
2. Place the datasets (`train.csv`, `test.csv`) in the `data/` folder.
3. Run the Jupyter notebook `spaceship.ipynb` to execute the analysis.

---

## Acknowledgements
- Kaggle for hosting the competition.
- [Spaceship Titanic Competition](https://www.kaggle.com/competitions/spaceship-titanic) for the dataset.
- Machine learning community for publicly shared kernels and insights.

---

## License
This project is licensed under the MIT License.
