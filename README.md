# 💰 Salary Prediction: Machine Learning Analysis

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Regression-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## Project Overview
The purpose of this project is to assist the HR team and the company in determining a reasonable, data-driven salary standard. By utilizing **Machine Learning**, this system predicts an employee's salary estimation based on their *Years of Experience* and other demographic factors.

**Dataset:** Sourced from Kaggle, consisting of **6,705 rows** and **6 features** (Age, Gender, Education Level, Job Title, Years of Experience, Salary).

## Methodology & Experiments

We adopted a **Staged Modelling Approach**, starting from a simple baseline to complex ensemble methods to find the most accurate predictor.

### 1. The Baseline: Linear Regression
We started with **Linear Regression** to establish a benchmark.
* **Goal:** To observe simple linear trends between Experience and Salary.
* **Result:** It captured the general trend well but struggled with non-linear variations in the data.

### 2. The Challengers: Tree-Based Ensembles
To capture complex patterns that a straight line cannot see, we deployed two powerful ensemble models:
* **Random Forest Regressor:** Uses "Bagging" technique (multiple decision trees voting together) to ensure stability and reduce variance.
* **Gradient Boosting:** Uses "Boosting" technique (correcting previous errors iteratively) to maximize accuracy.

## Model Performance

The table below summarizes the evaluation results. We used **R-Squared ($R^2$)** to measure accuracy and **MAE (Mean Absolute Error)** to measure the average prediction deviation in currency units.

| Experiment Name | Model Architecture | R-Squared | MAE | Status |
| :--- | :--- | :--- | :--- | :--- |
| **Baseline** | Linear Regression | `0.84` | 15,048.94 | Good Baseline |
| **Challenger 1** | **Random Forest Regressor** | **`0.98`** | **3,030.29** | **Winner** |
| **Challenger 2** | Gradient Boosting | `0.91` | 12,044.99 | High Variance |

> *Note: Higher R-Squared and Lower MAE indicate better performance.*

## The Champion Model: Random Forest

After rigorous benchmarking, **Random Forest Regressor** has been selected as the final model for deployment.

* **Why it won:** It achieved near-perfect accuracy ($R^2 \approx 0.98$) with the lowest error. The "Bagging" mechanism proved to be extremely robust for this specific dataset size, effectively handling outliers better than the aggressive Gradient Boosting.
* **Strategic Value:** It provides the HR team with a highly precise benchmark for salary negotiations, with an average error margin of only ~$3,030.

## Key Insights
1.  **Experience is King:** Exploratory Data Analysis (EDA) confirmed a **very strong positive correlation** between *Years of Experience* and *Salary*.
2.  **Complexity $\neq$ Superiority:** A crucial finding from this experiment is that the theoretically more advanced **Gradient Boosting** did *not* outperform Random Forest.
    * *Fit to Purpose:* For this specific dataset structure, the stability of Random Forest was superior to the hyper-sensitive error correction of Boosting.
    * *Lesson:* Always benchmark; never assume the most complex model is the best.
3.  **Non-Linearity Matters:** At certain seniority levels, salary increases are not linear. Tree-based models captured these "plateaus" and "jumps" much better than Linear Regression.

## How to Run
1.  Clone the repository.
2.  Install dependencies:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn
    ```
3.  Run the Jupyter Notebook `Salary_Prediction.ipynb`.

## Future Improvements
* **Feature Engineering:** Create new features like *Age-to-Experience Ratio* to detect rapid career climbers.
* **Hyperparameter Tuning:** Use GridSearch CV to further optimize the Gradient Boosting parameters to see if it can match Random Forest.
* **Web Deployment:** Deploy the Random Forest model using Streamlit or Flask for easy access by HR users.

---
**Created by Wyena Suilianty**
