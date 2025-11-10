# California Housing Price Prediction
<img width="1000" height="667" alt="image" src="https://github.com/user-attachments/assets/42b87e7d-7714-4459-a6c7-38e57f19720b" />

This project aims to predict median house prices in California using demographic and geographic data.
It demonstrates skills in data preprocessing, exploratory data analysis (EDA), feature engineering, and linear regression modeling using Python and Scikit-learn.

# 1. Project Overview

The dataset contains information about different housing districts in California, including the number of rooms, population, median income, and distance to the ocean.
The objective is to build a regression model that can accurately estimate housing prices based on these features.

# 2. Workflow

**2.1. Data Loading & Cleaning**

- Loaded the dataset (housing.csv) using Pandas
- Checked missing values and dropped rows with nulls
- Split the dataset into training (80%) and testing (20%) sets

**2.2. Feature Engineering**

- Encoded categorical variable ocean_proximity using one-hot encoding
- Applied log transformation on skewed numerical features: total_rooms, total_bedrooms, population, households
- Created new ratio-based features:
    - bedroom_ratio = total_bedrooms / total_rooms
    - household_rooms = total_rooms / households

**2.3. Exploratory Data Analysis (EDA)**

- Visualized feature distributions using histograms
- Created scatter maps (latitude vs longitude) colored by median_house_value
- Used correlation heatmaps to identify strongest predictors

**2.4. Model Training**
- Model: Linear Regression
- Library: scikit-learn
- Achieved an R² score of 0.67 on the test set

**2.5. Visualization**

- Distribution of housing values
- Correlation heatmap
- Geographic scatter plot of predicted prices
  
# 3.Analysis & Insights
**3.1. Geographic Patterns**
- Latitude and longitude strongly influence house value.
- Prices increase toward the coastal regions (west side) - especially San Francisco Bay Area and Los Angeles.
- Proximity to the coast significantly boosts property value - likely due to demand, accessibility, and tourism.
- Inland regions show lower prices and higher population density, possibly due to limited economic opportunities and distance from urban centers.

-> Geography captures hidden regional effects.
  
<img width="1250" height="679" alt="image" src="https://github.com/user-attachments/assets/a1d72a0f-ae61-4ab8-95da-fae6f3f7dab1" />

**3.2. Economic Factors (Median Income)**

 - median_income is the single strongest predictor (correlation ≈ 0.69).
 - Areas with higher income levels consistently exhibit higher house values.
 - Scatter plots between income and house value show an exponential trend, suggesting a non-linear relationship.
 - Using log transformation or polynomial terms for income could capture non-linear effects and improve predictions.
   
   <img width="1247" height="797" alt="image" src="https://github.com/user-attachments/assets/2a95d859-6f73-425f-933c-77ba3098a8d0" />

**3.3. Housing Characteristics**

- Raw features such as total_rooms, total_bedrooms, and households are highly skewed.
- Log transformation made them more normally distributed and reduced the impact of extreme values.
- The ratio household_rooms has a mild positive correlation with price - districts with more rooms per household tend to have more spacious and expensive housing.
  
-> Conversely, bedroom_ratio (bedrooms per room) has a slight negative correlation - suggesting that smaller or older houses with many bedrooms but fewer total rooms (less open space) tend to be less expensive.
  
<img width="1238" height="682" alt="image" src="https://github.com/user-attachments/assets/5e6ddbfc-ea99-4c2d-9033-d4404c1a8dce" />

**3.4. Population Density & Crowding**

- Higher population and household counts generally associate with lower housing prices, especially inland.
- This suggests that densely populated areas may face housing saturation or lower per-household space availability.
- Adding features like “population per household” can capture urban density effects more accurately.

**3.5. Model Evaluation**

- Model: Linear Regression
- R² Score: 0.6716
- Interpretation: The model explains ~67% of the price variance - a strong baseline for a purely linear approach.
  
-> The residual analysis shows that predictions are less accurate for extremely high-value houses.

# 4. Tech Stack
- Category	Tools / Libraries
- Data Handling	pandas, numpy
- Visualization	matplotlib, seaborn
- Machine Learning	scikit-learn
- Environment	Google Colab / Jupyter Notebook

# 5. Results
- Metric Score
- R² (Test Set)	0.6716
-> The model explains around 67% of the variance in housing prices - a solid baseline for further improvement.

# 6. Future Improvements

- Use median imputation instead of dropping missing values
- Apply log transformation on the target variable
- Implement Ridge / Lasso / Random Forest models for better accuracy
- Perform cross-validation and hyperparameter tuning
- Visualize predicted vs actual prices

