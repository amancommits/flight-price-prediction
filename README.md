# flight-price-prediction
End-to-end flight price prediction using EDA, feature engineering, ensemble regression, XGBoost tuning, and model blending.

# ✈️ Flight Price Prediction

A machine learning project for predicting flight ticket prices using flight-related features such as airline, route, departure time, stops, class, duration, and days remaining before departure.

This project was developed as part of a **private Kaggle competition conducted through the IIT Madras BS in Data Science program**.

## 🏆 Results

* **Validation R²:** 0.979
* **Leaderboard Rank:** 158 / 1,237
* **Evaluation Metric:** R² (coefficient of determination)

## 📊 Dataset

The training dataset contained **40,000 records and 12 columns**, including:

* Airline
* Flight
* Source
* Destination
* Departure time
* Arrival time
* Number of stops
* Travel class
* Duration
* Days left before departure
* Price (target)

The dataset used for the competition is **not included in this repository** because the competition was private.

## 🔎 Exploratory Data Analysis

The analysis investigated:

* Missing values and data types
* Target-price distribution
* Airline-wise price patterns
* Effect of number of stops on price
* Departure-time price patterns
* Economy vs Business class prices
* Duration and price relationships
* Route-level price patterns
* Descriptive statistics and potential outliers

A notable finding was the strong difference in price between **Economy and Business class**, while airline and route also showed substantial variation in ticket prices.

## ⚙️ Feature Engineering & Preprocessing

The project included:

* Missing-value handling
* Creation of a combined **route** feature from source and destination
* Categorical feature encoding
* Numerical feature preprocessing
* Train-validation splitting with `random_state=42`
* Separate preparation of training and test features

The engineered `route` feature produced **30 unique source-destination combinations** in the training data.

## 🤖 Models & Experiments

Several regression approaches were explored, including:

* Linear Regression
* Ridge Regression
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor
* Bagging Regressor
* Voting/ensemble approaches

The experiments were evaluated primarily using **R²**, matching the competition's evaluation metric.

## 🚀 Final Approach

The final solution focused on **XGBoost**, with hyperparameter experimentation around:

* Number of estimators
* Learning rate
* Maximum tree depth
* Minimum child weight
* Subsampling
* Column subsampling
* L1/L2 regularization

The final prediction used a weighted blend of the XGBoost and Random Forest predictions:

```text
Final Prediction = 0.9 × XGBoost + 0.1 × Random Forest
```

This ensemble approach was used for the final competition submission.

## 🛠️ Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Matplotlib
* Seaborn
* Jupyter / Google Colab
* Kaggle

## 📁 Repository Contents

```text
flight-price-prediction/
│
├── flight_price_prediction.ipynb
├── README.md
└── requirements.txt
```

### Notebook

`flight_price_prediction.ipynb` contains the complete exploratory analysis, preprocessing, feature engineering, model experiments, validation, and final prediction workflow.

## 🔒 Dataset & Competition Note

This project was developed for a **private competition**. The original training/test datasets and other restricted competition files are intentionally not included in this repository.

The notebook is provided as a record of the analysis and modeling workflow.

## 📌 Key Takeaway

The project demonstrates an end-to-end tabular regression workflow, from exploratory data analysis and feature engineering to model comparison, hyperparameter tuning, ensemble modeling, and competition submission.

