#  Bike Rental Demand Prediction (Time Series ML Project)

##  Project Overview
This project analyzes and predicts bike rental demand using the `hour.csv` dataset. The goal is to understand time-based patterns in bike usage and build a machine learning model that can accurately forecast the number of bikes rented per hour.

---

##  Exploratory Data Analysis (EDA)

###  Trend Analysis
- Rentals were lowest in **2011** and highest in **2012**, showing growth over time.
- Rentals are generally lower at the **beginning of the year** and higher during the **middle months**, indicating seasonality.

###  Hourly Pattern
- Lowest rentals around **4 AM**
- Peak rentals around **5 PM**
- Reflects daily commuting behavior

###  Weekly Pattern
- Lowest rentals on **Sunday**
- Highest on **Thursday and Friday**
- Indicates higher usage during working days

###  Monthly Pattern
- Lowest in **January**
- Highest in **June and September**
- Likely influenced by weather conditions

---

##  Time Series Analysis

###  Autocorrelation (ACF)
- Peaks at every **24 lags**
- Confirms strong **daily repeating patterns**

###  Seasonal Decomposition
- Data shows both:
  - **Trend** (increase over time)
  - **Seasonality** (daily patterns)

---

##  Feature Engineering

The following features were created to capture temporal patterns:

- `hour` → Hour of the day  
- `day` → Day of the week  
- `month` → Month of the year  
- `lag1` → Previous hour rentals  
- `lag24` → Same hour previous day rentals  
- `rolling_mean` → Average rentals over last 24 hours  

---

##  Model Used

###  Random Forest Regressor
- Handles **non-linear relationships**
- Works well with **time-based features**
- Requires minimal preprocessing

---

##  Model Performance

###  Random Forest
|  Metric   |  Value |
|-----------|--------|
| Test MAE  |  ~49   |
| Test RMSE |  ~84   |

###  Baseline Models

#### Lag 1 (Previous Hour)
| Metric | Value |
|--------|-------|
|   MAE  |  ~85  |
|   RMSE |  ~129 |

#### Lag 24 (Previous Day)
| Metric | Value |
|--------|-------|
|   MAE  |  ~80  |
|  RMSE  | ~134  |

---

##  Key Insights

- Strong **daily and seasonal patterns** exist in the data  
- Lag features significantly improve model performance  
- Random Forest captures patterns better than simple baselines  

---

##  Conclusion

The model successfully learns:
- Time-based trends  
- Daily seasonality  
- Historical dependencies  

It performs significantly better than baseline approaches, making it a reliable model for predicting bike rental demand.

---

## Tech Stack

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Scikit-learn  
- Statsmodels  

---

##  Future Improvements

- Hyperparameter tuning  
- Try advanced models like XGBoost  
- Include weather-related features  
- Deploy as a web application  

---

##  Dataset

- File used: `hour.csv` (Bike Sharing Dataset)

---

##  Author

Heerak Tiwari
