# Fair Salary Prediction Model for Delta Ltd.: Eliminating Bias in Compensation

This project develops a fair, data‑driven salary prediction model for Delta Ltd. to support transparent and unbiased compensation decisions. It uses employee‑level HR data to estimate **Expected CTC** from factors such as experience, current CTC, education, industry, role, and performance, and translates the results into business recommendations for HR.

## Project overview

- **Goal:** Build a predictive model for Expected CTC that HR can use as a benchmark for offers and revisions, reducing subjectivity and potential bias.
- **Artifacts in this repo:**
    - `Capstone_Project_Salary_Prediction.ipynb` – end‑to‑end notebook with EDA, feature engineering, modeling, and evaluation.
    - `Business Report Capstone Project Final.pdf` – business‑focused report and recommendations for Delta Ltd.

## Data and features

The dataset contains employee‑level records with both numerical and categorical variables that influence salary expectations.

- **Key numerical variables**
    - Total Experience (Years)
    - Current CTC
    - Expected CTC (target)
    - Number of Publications
    - Number of Certifications
- **Key categorical variables**
    - Education (Bachelor’s, Master’s, PhD, etc.)
    - Industry (IT, Finance, Healthcare, etc.)
    - Role (e.g., Data Scientist, Software Engineer, Manager)
    - Department (HR, Sales, Engineering, etc.)
    - Last Appraisal Rating

The target **Expected_CTC** is right‑skewed: most expectations are in the 5–20 million range, with a small set of very high outliers that are carefully treated before modeling.

## Methodology

1. **Data cleaning and preprocessing**
    - Dropped columns with more than 30% missing values.
    - Imputed remaining missing values (mode for categoricals).
    - Capped extreme salary outliers using Winsorization to stabilize training.
2. **Feature engineering**
    - Created **Experience Level** buckets from Total Experience.
    - Computed **Salary Increment Percentage** between Expected and Current CTC.
    - Built an **Achievement Score** from publications, certifications, and appraisal rating.
3. **Exploratory Data Analysis (EDA)**
    - Studied distributions and relationships between salary and profile variables.
    - Identified patterns such as low‑experience employees with unusually high expectations and industry imbalance in the sample.
4. **Model development and tuning**
    - Trained multiple regression models and compared performance using MAE/RMSE and R².
    - Used `RandomizedSearchCV` to tune the best‑performing model and avoid overfitting.
5. **Interpretation and business insights**
    - Analyzed feature importances and effects to understand how experience, current CTC, education, certifications, and performance influence fair salary bands.
    - Converted technical results into concrete HR actions: defining salary ranges by role/experience, flagging outlier expectations, and using the model as decision support rather than a black box.

## How to use this repository

1. Clone the repo and open `Capstone_Project_Salary_Prediction.ipynb` in Jupyter / VS Code.
2. Run the notebook cells in order to reproduce EDA, model training, and evaluation.
3. Refer to `Business Report Capstone Project Final.pdf` for the executive‑level narrative, insights, and recommendations.
