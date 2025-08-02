# CODEALPHA_3

Task 3: Car Price Prediction using Machine Learning
Predicting the selling price of used cars using regression models with visual analysis and model comparison.

1. Project Structure

```
Car-Price-Prediction/
│
├── README.md
├── car_price_prediction.ipynb
├── requirements.txt
├── dataset/
│   └── car_data.csv
├── visuals/
│   ├── selling_price_distribution.png
│   ├── owner_type_count.png
│   └── ... other plots
└── models/
    ├── linear_regression.pkl
    ├── random_forest.pkl
    └── xgboost.pkl
```

 2. Features Used

* `Car_Name`
* `Year`
* `Selling_Price` (Target)
* `Present_Price`
* `Driven_kms`
* `Fuel_Type`
* `Selling_type`
* `Transmission`
* `Owner`

3. Exploratory Data Analysis (EDA)


 Distribution of Selling Price

![Selling Price Distribution](visuals/selling_price_distribution.png)
**Interpretation:**
The majority of used cars are sold at prices below ₹10 lakhs. There's a strong right skew, with very few cars priced above ₹20 lakhs.

 **Count of Cars by Owner Type**

![Owner Type](visuals/owner_type_count.png)
**Interpretation:**
Most cars are first-hand (Owner = 0). Second-hand and third-hand cars form a small portion, suggesting newer or better-maintained cars are preferred for resale.

 **4. Model Performance Comparison**

| Model                               | R² Score | MSE    | Interpretation                                                                               |
| ----------------------------------- | -------- | ------ | -------------------------------------------------------------------------------------------- |
| **Linear Regression**               | 0.8489   | 3.4813 | Decent baseline model, but struggles with non-linear patterns.                               |
| **Random Forest**                   | 0.9623 ✅ | 0.8689 | Excellent performance. Captures complex relationships and handles categorical features well. |
| **XGBoost**                         | 0.9524   | 1.0956 | Competitive model, slightly underperforms compared to Random Forest.                         |
| **Decision Tree**                   | 0.9449   | 1.2683 | Good performance, but slightly prone to overfitting.                                         |
| **SVR (Support Vector Regression)** | 0.7813   | 5.0372 | Underperforms compared to tree-based models.                                                 |
| **Ridge Regression**                | 0.8484   | —      | Similar to Linear Regression, regularized.                                                   |
| **Lasso Regression**                | 0.6804 ❌ | —      | Performs worst due to feature elimination effect.                                            |

**Best Model: Random Forest Regressor**

 **5. Workflow Steps**

1. **Data Preprocessing**

   * Encoded categorical variables (Fuel\_Type, Selling\_type, Transmission).
   * Created new feature: `Car_Age = 2025 - Year`.

2. **EDA**

   * Distribution plots, count plots, heatmaps to explore relationships.

3. **Model Training**

   * Trained models using `train_test_split`.
   * Used `R² Score` and `MSE` for evaluation.

4. **Model Saving**

   * Saved top models (Random Forest, XGBoost) using `joblib`.

 **6. Final Insights**

*  Most cars are **first-hand** and under ₹10 lakhs.
*  Features like **Present Price**, **Car Age**, and **Fuel Type** are most influential.
*  **Random Forest** is the most accurate and robust model for this task.
*  Data is skewed; log transformations could help for linear models.

 **6. Setup Instructions**

#### Install Requirements

```bash
pip install -r requirements.txt
```

 Run the Jupyter Notebook

```bash
jupyter notebook car_price_prediction.ipynb
```









