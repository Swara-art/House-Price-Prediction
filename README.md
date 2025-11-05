# House-Price-Prediction
This is an end-to-end machine learning project that predicts house prices in Bangalore, India. The project uses the Bangalore House Price Data from Kaggle and follows the complete data science pipeline from data cleaning and feature engineering to model building and evaluation. 


Bangalore House Price Prediction
This is an end-to-end machine learning project that predicts house prices in Bangalore, India. The project uses the Bangalore House Price Data from Kaggle and follows the complete data science pipeline from data cleaning and feature engineering to model building and evaluation.
The goal of this project is to build a regression model that can accurately estimate the price of a house based on its key features, such as location, square footage, number of bedrooms, and bathrooms.
Project Workflow:
This project is broken down into 5 key stages:
      1. Data Cleaning & Preprocessing:
       Loaded the raw CSV data into a pandas DataFrame. Handled missing values (NaN) by dropping rows with unavailable data. Cleaned and transformed messy text-based   columns:size: Converted entries like "2 BHK" and "4 Bedroom" into a numerical bhk column.total_sqft: Wrote a custom function to handle non-standard entries, including ranges (e.g., "2100 - 2850") and different units (e.g., "34.46Sq. Meter"). Ranges were converted to their average.
      2. Feature Engineering:
      Created a new, more predictive feature:price_per_sqft: This feature was engineered by dividing the total price (converted from Lakhs) by total_sqft. It served as a crucial tool for identifying and removing outliers.
      3. Outlier Removal:
      Cleaned the dataset of statistically absurd and illogical data points to improve model accuracy.
      Domain-based Outliers: 
      Removed properties that were logically impossible (e.g., apartments with 10 bedrooms but only 1000 sqft, or 3-bedroom houses with 6 bathrooms).
      Statistical Outliers: For each location, we removed properties that were beyond one standard deviation of the average price_per_sqft. This removed extreme anomalies and data-entry errors.
      4. Feature EncodingPrepared the data for modeling by converting all features to a numerical format.
      One-Hot Encoding: The location column, which had over 240 unique categories, was converted into 240+ binary (0/1) columns using pandas.get_dummies(). This is essential to prevent the model from learning a false ordinal relationship between locations.
      5. Model Building & EvaluationSplit the final, clean data into training (80%) and testing (20%) sets.Model 1: Linear Regression: As a baseline, a simple LinearRegression model was trained.
      Model 2: Random Forest Regressor: 
      A more advanced RandomForestRegressor model was trained to handle the non-linear complexities of the data.
      Evaluation: Models were compared using K-Fold Cross-Validation (k=5). The Random Forest proved to be the more stable and robust model, achieving an $R^2$ score of ~65%. The Linear Regression model failed catastrophically during cross-validation, showing it was not suitable for this dataset's high dimensionality.
      Technologies Used: PythonPandas: For data manipulation and cleaning.NumPy: For numerical operations.Scikit-learn (sklearn): For model building (LinearRegression, RandomForestRegressor), data splitting (train_test_split), and evaluation (cross_val_score, r2_score).
      How to Use: To run this project, download the Bengaluru_House_Data.csv file and run the project's Jupyter Notebook or Python script from start to finish. The notebook is structured to follow the 5-step workflow described above.
