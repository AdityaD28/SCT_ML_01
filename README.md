# House Price Prediction 

A beginner-friendly machine learning project that uses a linear regression model to predict house prices based on features like living area, number of bedrooms, and bathrooms. This repository includes the full Python code in a Jupyter Notebook, from data preprocessing to model training and prediction.

##  Introduction

The primary goal of this project is to build a simple yet effective machine learning model to predict the sale price of houses. We use a dataset containing various features of residential homes. The final model is a linear regression algorithm trained on a select set of features.

##  Dataset

The project uses two primary data files:

* `train.csv`: Contains the training data with features and the target variable, `SalePrice`.
* `test.csv`: Contains the test data with the same features as the training set, but without the `SalePrice`.

The model is built using the following key features:
* `GrLivArea`: Above ground living area in square feet.
* `BedroomAbvGr`: Number of bedrooms above ground.
* `FullBath`: Full bathrooms above grade.
* `HalfBath`: Half baths above grade.

## Methodology

The entire process is detailed in the `House_Price_Prediction.ipynb` Jupyter Notebook. Here's a step-by-step breakdown:

### 1. Data Loading and Initial Exploration

* The training and testing datasets are loaded using the pandas library.
* An initial inspection of the first few rows of the training data is performed to understand its structure.

### 2. Feature Engineering and Preprocessing

A function named `preprocess_data` is defined to handle feature engineering and selection. This function performs the following actions:
* **Creates a new feature `TotalBath`**: This is a combination of the `FullBath` and `HalfBath` features to represent the total number of bathrooms (`TotalBath = FullBath + 0.5 * HalfBath`).
* **Selects the final features**: The model uses `GrLivArea`, `BedroomAbvGr`, and the newly created `TotalBath` as the final set of features for prediction.
* **Handles missing values**: Any missing values in the test dataset's selected feature columns are filled with the mean of the corresponding column from the training dataset to prevent data leakage.

### 3. Model Training

* A **Linear Regression** model from the `scikit-learn` library is used for this prediction task.
* The model is trained on the processed training features (`X_train`) and the `SalePrice` target variable (`y_train`).
* The final model coefficients and intercept are as follows:
    * **Coefficients**: `[107.04, -27861.46, 26337.6]`
    * **Intercept**: `52305.36`

### 4. Prediction

* The trained linear regression model is used to predict the sale prices for the processed test data (`X_test`).

##  How to Run the Code

To run this project, you'll need to have Python and the required libraries installed.

### Prerequisites

Make sure you have the following Python libraries installed:
* pandas
* numpy
* scikit-learn

You can install them using pip:
```bash
pip install pandas numpy scikit-learn
```
### Running the Notebook
1. Clone the repository:
   
   ```bash
   git clone https://github.com/AdityaD28/SCT_ML_01
   ```
2. Navigate to the project directory:
   
    ```bash
   cd SCT_ML_01
   ```
3. Ensure you have the dataset files `train.csv` and `test.csv` in the same directory.

4. Launch Jupyter or Colab Notebook

5. Open `House_Price_Prediction.ipynb` and run the cells sequentially.

## Results

The final predictions are saved in a CSV file named `House_Price_Prediction.ipynb`. This file contains two columns:

* `Id`: The unique identifier for each house in the test set.

* `SalePrice`: The predicted sale price for that house.

Here is a preview of the first 5 predictions:

| Id   | SalePrice     |
| :--- | :------------ |
| 1461 | 118828.82     |
| 1462 | 150484.93     |
| 1463 | 208934.84     |
| 1464 | 206258.82     |
| 1465 | 186270.18     |

## File Structure

The repository is structured as follows:
```
.
├── House_Price_Prediction.ipynb
├── train.csv
├── test.csv
└── house_price_predictions.csv
```
