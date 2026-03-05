# House Price Prediction with Gradient Boosting

This project explores the **Ames Housing dataset** and builds a machine learning pipeline to predict house prices using **Gradient Boosting models**.

The workflow follows a typical tabular ML pipeline including:

- Exploratory Data Analysis (EDA)
- Missing value handling
- Feature engineering
- Encoding of categorical variables
- Model training and evaluation
- Comparison of gradient boosting algorithms

## Dataset

The dataset used is the **Ames Housing dataset**, which contains detailed information about residential homes in Ames, Iowa.  

It includes **2930 observations and 80+ features**, describing structural characteristics, quality indicators, and location-related attributes of houses.

The target variable is the **house sale price (`SalePrice`)**.

Because the price distribution is highly skewed, a **log transformation** is applied:

\[
y = \log(1 + SalePrice)
\]

This transformation stabilizes variance and improves model performance.

## Data Preprocessing

Several preprocessing steps are applied before modeling:

- **Missing value handling**
  - Some missing values represent the absence of a feature (e.g. no pool, no garage) and are filled with `"None"` or `0`.
  - Other variables are imputed using median or mode.

- **Outlier removal**
  - Houses with extremely large living areas but unusually low prices are removed.

- **Feature engineering**

New features are created to better represent the structure of the house:

- `TotalSF` – total house area
- `HouseAge` – relationship between sale year and construction year
- `YearsSinceRemod` – years since last renovation
- `TotalBath` – total number of bathrooms
- Binary indicators such as `HasGarage`, `HasBasement`, `HasFireplaces`

- **Categorical encoding**

Categorical variables are transformed using **One-Hot Encoding**, resulting in a dataset with ~320 features.

## Models

The project focuses on **Gradient Boosting algorithms**, which are among the most effective methods for tabular datasets.

Three models are trained and compared:

- XGBoost
- LightGBM
- CatBoost

Model performance is evaluated using **5-fold cross-validation** with the **Root Mean Squared Error (RMSE)** metric.

## Results

Cross-validation results:

| Model | RMSE |
|------|------|
| XGBoost | 0.1227 |
| LightGBM | 0.1265 |
| CatBoost | **0.1211** |

The best-performing model is **CatBoost**, which is then trained on the training set and evaluated on the test set.

Final test performance: RMSE ≈ 0.088


## Feature Importance

The most influential features for predicting house prices include:

- **Overall Qual** – overall material and finish quality
- **TotalSF** – total house area
- **TotalBath** – total number of bathrooms
- **Gr Liv Area** – above-ground living area
- **Overall Cond** – overall condition of the house

These features confirm that **house quality, size, and amenities are the strongest drivers of property value**.

