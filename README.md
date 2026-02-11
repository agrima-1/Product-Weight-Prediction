# SmartBuild Weight & Error Prediction (Academic Project)

This repository contains an end-to-end machine learning workflow to predict manufacturing outcomes using SmartBuild’s data.

---

## Objective
Build predictive models using **pre-production machine settings and raw material measurements** to:
- Predict final product **weight (`weight_in_kg`)**
- Predict **production errors** before machine execution

---

## Project Structure
- `Task1_Weight_FINAL.ipynb` – Weight prediction (Regression)
- `Task2_Error_Prediction.ipynb` – Error prediction (Classification)
- `Machine_Settings_Log_01.csv` – Raw machine settings dataset
- `Production_Log_01.csv` – Raw production output dataset

---

## Data Processing & Scope
This repository reflects **individual academic work**. While part of a broader assignment, only the notebooks and analyses personally implemented by me are included here.

**Core Preprocessing:**
- **Cleaning:** Missing value inspection and column name standardization.
- **Outlier Removal (Weight):** Applied IQR-based method to `weight_in_kg` using a `Q3 + (5 × IQR)` threshold to remove extreme upper-tail outliers.
- **Encoding:** One-hot encoding for nominal categorical variables.
- **Leakage Prevention:** All features used are **pre-production**, ensuring the model does not rely on post-production data.

---

## Task 1 – Weight Prediction (`weight_in_kg`)

### Modeling Approach
A **Random Forest Regressor** was selected to handle nonlinear relationships and provide resistance to multicollinearity.
- **Configuration:** 80/20 train-test split, 200 trees, and a maximum depth of 15.
- **Evaluation:** R² Score, MAE, MSE, and RMSE.
- **Results Summary:** The model demonstrates a strong predictive signal, indicating that input material properties and machine settings are reliable predictors of final weight.

---

## Task 2 – Error Prediction

### Modeling Approach
A **Random Forest Classifier** was implemented to identify binary outcomes (**Error** vs. **No Error**).
- **Feature Analysis:** EDA identified **Ionization Class B** as a primary risk factor for failure, whereas **Flux Compensation** classes showed a uniform error distribution across the dataset.
- **Methodology:** 80/20 train-test split using pre-production features to support proactive decision-making.
- **Evaluation:** Confusion Matrix (focusing on reducing False Negatives), Precision, Recall, and F1-Score.

---

## Technologies Used
- **Python 3.11.7**
- pandas, NumPy
- scikit-learn
- matplotlib, seaborn

---

## Future Improvements
- **Automated Tuning:** Use of **GridSearchCV** to systematically find optimal hyperparameters.
- **Validation:** Implementing **Cross-validation** to ensure model stability across different data folds.
- **Pipelines:** Transitioning to Pipeline-based preprocessing to automate the process

---

## Note
This project was completed for educational purposes. The dataset and methods are intended for academic demonstration and may require further refinement for real-world production environments.
