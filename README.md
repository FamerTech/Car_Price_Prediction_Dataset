## Project Overview
This project aims to build a machine learning model to predict the selling price of used cars based on various features. The primary objective is to provide an online car marketplace with a tool to estimate car prices, aiding both sellers and buyers.

## Engineering Workflow - Steps Taken
1.  **Problem Understanding:** Defined the business problem, identified 'Selling_Price' as the target variable, and other relevant car attributes as features.
2.  **Data Exploration (EDA):**
    *   Checked for missing values (no significant missing values were found).
    *   Generated summary statistics for both numerical and categorical features.
    *   Visualized relationships between 'Selling_Price' and other features through various plots (histograms, scatter plots, box plots) to understand data distribution and correlations.
3.  **Data Preprocessing:**
    *   **Handling Missing Values:** Although the dataset provided did not have missing values, a robust imputation strategy (median for numerical, mode for categorical) was outlined and implemented in earlier code cells for generalizability.
    *   **Feature Engineering:** Created a new feature 'car_age' from 'Year' (2026 - Year) and subsequently dropped the original 'Year' column.
    *   **Categorical Variable Encoding:** Dropped the 'Car_Name' column due to high cardinality. One-hot encoded 'Fuel_Type', 'Seller_Type', and 'Transmission' columns using `pd.get_dummies` with `drop_first=True` to avoid multicollinearity.
    *   **Feature Scaling:** Applied `StandardScaler` to all numerical features (excluding the target 'Selling_Price') to standardize their ranges, which is beneficial for many machine learning algorithms like Linear Regression.
4.  **Model Building:**
    *   Split the preprocessed data into training (80%) and testing (20%) sets.
    *   Trained a Linear Regression model on the training data.
5.  **Model Evaluation:**
    *   Made predictions on the test set.
    *   Evaluated the model's performance using standard regression metrics:
        *   Mean Absolute Error (MAE): 1.22
        *   Root Mean Squared Error (RMSE): 1.87
        *   R-squared (R² Score): 0.85
6.  **Prediction:** Demonstrated how to predict prices for sample cars from the test set, comparing actual vs. predicted values.
7.  **Insights:**
    *   Analyzed the coefficients of the Linear Regression model to identify the most influential factors on car price. `Present_Price` was identified as the strongest positive predictor, while `car_age`, `Kms_Driven`, `Seller_Type_Individual`, and `Transmission_Manual` showed negative correlations.
    *   Discussed unexpected observations or confirmations of common knowledge regarding car pricing.

## Replication Guide
To replicate this analysis and run the notebook:

1.  **Download the Dataset:** Obtain the `Car_Price_Prediction_Dataset.csv` file. This is typically available in the resource section of your LMS or provided alongside the project.
2.  **Setup Environment:** Ensure you have Python installed, along with the necessary libraries. You can install them using pip:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```
3.  **Launch Environment:**
    *   **Google Colab:**
        1.  Upload the `car_price_prediction_notebook.ipynb` file to your Google Drive.
        2.  Open the notebook in Google Colab.
        3.  Upload the `Car_Price_Prediction_Dataset.csv` file directly to your Colab environment (e.g., to the `/content/` directory if you're using the provided file path).
        4.  Run all the code cells sequentially from top to bottom.
    *   **Jupyter Notebook (or JupyterLab):**
        1.  Place the `car_price_prediction_notebook.ipynb` file and `Car_Price_Prediction_Dataset.csv` in the same directory.
        2.  Launch Jupyter Notebook/Lab from your terminal in that directory (`jupyter notebook` or `jupyter lab`).
        3.  Open the `car_price_prediction_notebook.ipynb` file.
        4.  Run all the code cells sequentially from top to bottom.

