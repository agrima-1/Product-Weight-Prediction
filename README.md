# SmartBuild Weight Prediction (Task 1 – Academic Project)

This repository contains my student project developed as part of an academic assignment. The goal is to build a machine learning model that predicts the final product weight (`weight_in_kg`) using SmartBuild’s manufacturing data. The project demonstrates a complete end-to-end workflow, including data cleaning, preprocessing, feature engineering, model training, evaluation, and visualization.

---

## Project Structure
- **Task1_Q1.ipynb** – Main notebook containing all steps: data exploration, feature engineering, encoding, model training, and evaluation.
- **Machine_Settings_Log_01.csv** – Raw machine settings dataset.
- **Production_Log_01.csv** – Raw production output dataset.

---

## Data Processing Overview
Key data preparation tasks included:

- Inspecting and handling missing values  
- Removing irrelevant or low-quality variables  
- Correcting inconsistent column names  
- Detecting and removing outliers from the target variable (`weight_in_kg`) using a 5-sigma threshold (values beyond five standard deviations from the mean were excluded)  
- Conducting exploratory analysis and feature investigation  
- Applying ordinal encoding to ordered categories  
- Applying one-hot encoding to nominal categorical variables  
- Producing the final cleaned and fully encoded dataset for model training  

---

## Modeling Approach
A **Random Forest Regressor** was selected due to its robustness and ability to model nonlinear relationships and handle multicollinearity.

Main configurations:
- Train–test split: 80% training, 20% testing  
- `RandomForestRegressor` with default parameters and a fixed `random_state`  
- Evaluation metrics:
  - R² Score  
  - Mean Absolute Error (MAE)  
  - Mean Squared Error (MSE)  
  - Root Mean Squared Error (RMSE)

---

## Evaluation and Visualizations
The notebook includes:
- Actual vs. Predicted values plot  
- Residual analysis plot  
- Feature importance visualization  
- Bar chart of evaluation metrics  

These visualizations help assess model performance beyond numerical scores.

---

## Results Summary
The Random Forest model produced strong predictive performance across multiple train–test splits, where the split ratio remained constant but the underlying samples varied due to different random seeds. Metrics indicate a high degree of variance explained and relatively low error values, demonstrating that the model fits the provided data well.

---

## Next Steps / Improvements
Future improvements I could implement: 

- Hyperparameter tuning for optimized model performance  
- Cross-validation for more stable evaluation  
- Experimenting with boosting-based algorithms  
- Pipeline-based preprocessing for reproducibility  
- Alternative outlier detection methods (e.g., IQR-based filtering)  

**Technologies used:**  
Python 3.12.5, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn

---

## Note
This project was completed solely for educational purposes within the scope of a student assignment. The dataset and methods are not intended for real-world use or production predictions. The dataset and methods may be further refined.
