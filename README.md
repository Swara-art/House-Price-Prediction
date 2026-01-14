# 🏠 Bangalore House Price Predictor — Real Estate Intelligence

### 📌 Problem Statement: The Real Estate "Data Noise" Crisis

Bangalore's housing market is one of the most complex in India, yet digital listings are often cluttered with **"Data Noise"** — inconsistent units, illogical outliers, and fragmented location tagging.
 
#### 🚨 Why this is a serious problem
* **Price Ambiguity:** Homebuyers struggle to find the "Fair Market Value" due to extreme price variance.
* **Non-Standard Units:** Listings mix Square Yards, Acres, and Sq. Meter, leading to calculation errors.
* **Data Anomalies:** "Ghost listings" with 10 bedrooms in 500 sqft distort average market trends.
* **High Dimensionality:** With 1,300+ unique locations, simple averages fail to provide granular accuracy.

### 💡 Our Solution: Predictive Price Engine

This project acts as an **intelligence layer** for the Bangalore property market. We transform raw, messy data into a clean, structured pipeline that provides high-confidence price estimations.

At its core, the engine uses **Statistical Scrubbing** and **Regression Modeling** to make property data:
✅ Standardized
✅ Outlier-Free
✅ Location-Aware
✅ Predictive



---

### 🧠 How It Works

**1️⃣ Data Sanitization**
* **Custom Tokenization:** Converts range-based strings (e.g., "2100 - 2850") into numerical averages.
* **Unit Conversion:** Normalizes various area metrics into a single standard: **Square Feet**.

**2️⃣ Autonomous Outlier Removal**
The system logic removes "statistically absurd" data points:
* **Business Logic:** Prunes houses where sqft per bedroom is below 300 (unrealistic living space).
* **Standard Deviation Filtering:** Removes properties whose price per sqft deviates significantly from the mean of their specific location.

**3️⃣ High-Dimensional Encoding**
* Uses **One-Hot Encoding** for the location feature. 
* **Dimensionality Reduction:** Locations with <10 listings are grouped as "Other" to prevent the model from overfitting on noise.



---

### 🏗️ System Architecture

The project follows a modular, 5-stage data science pipeline:

1.  **Data Ingestion:** Loading raw CSV data into Pandas.
2.  **Cleaning & Preprocessing:** Handling nulls and formatting text features.
3.  **Feature Engineering:** Calculating `price_per_sqft` as a core validation metric.
4.  **Transformation:** Converting categorical text into numerical sparse matrices.
5.  **Model Evaluation:** Using K-Fold Cross-Validation to test stability across different data segments.

---

### 🛠️ Tech Stack

**🔹 Data Manipulation**
* **Pandas:** For structural cleaning and data wrangling.
* **NumPy:** For numerical operations and array handling.

**🔹 Machine Learning**
* **Scikit-learn:** * `LinearRegression`
    * `RandomForestRegressor`
    * `ShuffleSplit` (For Randomized Cross-Validation)

**🔹 Reporting & Visualization**
* **Matplotlib:** For outlier detection and distribution analysis.

---

### 📊 Model Performance

| Model | Technique | Result ($R^2$ Score) | Status |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | Ordinary Least Squares | Failed (Unstable) | ❌ Rejected |
| **Random Forest** | Ensemble Learning | **~65% Accuracy** | ✅ Selected |

> **Key Insight:** The Random Forest Regressor handled the non-linear relationship between premium locations and property size far better than the baseline linear model.

---

### 🚀 Impact & Benefits

* ⏱️ **Efficiency:** Instant price estimates based on historical neighborhood trends.
* 💰 **Financial Protection:** Prevents buyers from overpaying for properties in "outlier" zones.
* 📊 **Clean Data:** Provides a standardized dataset ready for further deep learning applications.

---

### 🔮 Future Enhancements

* **Geospatial Intelligence:** Integration with Google Maps API for "Distance to Tech Park" features.
* **Deployment:** Building a Flask/React web interface for end-users.
* **Real-time Scraping:** A pipeline to pull live listings from property portals.

---

### 📄 License
This project is for academic and demonstration purposes using the Kaggle Bangalore House Price dataset.

✨ **Envisioning a future where every homebuyer has the power of data at their fingertips.**
