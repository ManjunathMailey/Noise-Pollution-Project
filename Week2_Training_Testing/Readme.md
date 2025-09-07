# Week 2: Model Training and Testing

## Objective

The goal of this week is to build a predictive model using the cleaned data from Week 1. We will train a Linear Regression model to predict the daytime noise levels in 2020 based on the city, location type, noise limits, and 2019 noise levels.

## Model

-   **Model**: Linear Regression
-   **Target Variable**: `Noise_Day_2020` (Daytime noise level in 2020)
-   **Features**:
    -   `City` (Categorical)
    -   `Location_Type` (Categorical)
    -   `Limit_Day_dB` (Numerical)
    -   `Noise_Day_2019` (Numerical)

## Steps

1.  **Load Cleaned Data**: The `cleaned_noise_data.csv` file from Week 1 is loaded.
2.  **Define Features and Target**: The dataset is split into feature variables (X) and the target variable (y).
3.  **Data Preprocessing Pipeline**:
    -   Categorical features (`City`, `Location_Type`) are transformed using `OneHotEncoder` to convert them into a numerical format.
    -   A `ColumnTransformer` is used to apply this transformation only to the categorical columns.
4.  **Train-Test Split**: The data is divided into training (80%) and testing (20%) sets.
5.  **Model Training**: A `Pipeline` is created that combines the preprocessing steps and the `LinearRegression` model. This pipeline is then trained on the training data.
6.  **Model Evaluation**:
    -   The trained model makes predictions on the unseen test data.
    -   The model's performance is evaluated using two metrics:
        -   **Mean Squared Error (MSE)**: Measures the average squared difference between the actual and predicted values.
        -   **R-squared ($R^2$) Score**: Indicates the proportion of the variance in the target variable that is predictable from the features. An $R^2$ of 1 indicates a perfect prediction.

## Results

The evaluation metrics (MSE, $R^2$) are printed to assess the model's accuracy. A scatter plot is also generated to visually compare the `Actual Values` vs. `Predicted Values`.