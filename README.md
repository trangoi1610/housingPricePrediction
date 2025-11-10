🏡 California Housing Price Prediction

This project aims to predict median house prices in California using demographic and geographic data.
It demonstrates skills in data preprocessing, exploratory data analysis (EDA), feature engineering, and linear regression modeling using Python and Scikit-learn.

📘 Project Overview

The dataset contains information about different housing districts in California, including the number of rooms, population, median income, and distance to the ocean.
The objective is to build a regression model that can accurately estimate housing prices based on these features.

🧩 Key Steps
1️⃣ Data Loading & Cleaning

Loaded the dataset (housing.csv) using Pandas

Checked missing values and dropped rows with nulls

Split the dataset into training (80%) and testing (20%) sets

2️⃣ Feature Engineering

Encoded categorical variable ocean_proximity using one-hot encoding

Applied log transformation on skewed numerical features:
total_rooms, total_bedrooms, population, households

Created new ratio-based features:

bedroom_ratio = total_bedrooms / total_rooms

household_rooms = total_rooms / households

3️⃣ Exploratory Data Analysis (EDA)

Visualized feature distributions using histograms

Created scatter maps (latitude vs longitude) colored by median_house_value

Used correlation heatmaps to identify strongest predictors

4️⃣ Model Training

Model: Linear Regression

Library: scikit-learn

Achieved an R² score of 0.67 on the test set

5️⃣ Visualization

Distribution of housing values

Correlation heatmap

Geographic scatter plot of predicted prices

🧠 Tech Stack
Category	Tools / Libraries
Data Handling	pandas, numpy
Visualization	matplotlib, seaborn
Machine Learning	scikit-learn
Environment	Google Colab / Jupyter Notebook
📊 Results
Metric	Score
R² (Test Set)	0.6716

✅ The model explains around 67% of the variance in housing prices — a solid baseline for further improvement.

🚀 Future Improvements

Use median imputation instead of dropping missing values

Apply log transformation on the target variable

Implement Ridge / Lasso / Random Forest models for better accuracy

Perform cross-validation and hyperparameter tuning

Visualize predicted vs actual prices

