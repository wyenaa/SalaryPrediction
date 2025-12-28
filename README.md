# Salary Prediction
#### Project Status : Completed
---
### Project Overview
The purpose of this project is to assist the HR team and the company in determining a reasonable salary standard. By utilizing **Machine Learning (Linear Regression)**, this system can predict an employee's salary estimation based on their *Years of Experience*.
### Dataset 
The dataset used is from Kaggle. Consisting of **6,705 rows** and **6 features** including:
- Age
- Gender
- Education Level
- Job Title
- Years of Experience
- Salary
### Tech Stack
* Language: Python 3.12
* Data Manipulation : Pandas, NumPy
* Modelling : Scikit-learn (Linear Regression, Random Forest, Gradient Boosting)
* Visualization : Matplotlib, Seaborn
### Key Insight
From the results of Exploratory Data Analysis (EDA), it was found that: 
1. There is a **very strong positive correlation** between work experience and salary.
   ![alt text](https://github.com/wyenaa/SalaryPrediction/blob/main/Notebook/Correlation_Matrix.png?raw=true)
2. At a certain level of experience, salary increases are not always perfectly linear, but rather have variations that are better captured by tree-based models.
### Model Performance
We developed and compared three Machine Learning algorithm approaches to predict salary estimates based on years of experience:
1. Linear Regression: As a baseline model for observing simple linear trends.
2. Random Forest Regressor: As a challenger model based on decision trees to capture more complex non-linear patterns.
3. Gradient Boosting: As an advanced model that uses boosting techniques to iteratively improve prediction errors in order to achieve maximum accuracy.
### Model Performance
| Model | R-Squared | MAE | Description |
|-------|-----------|-----|-------------|
|Linear Regression | 0.84 | 15048.94 | Model Baseline | 
|Random Forest Regressor | 0.98 | 3030.29 | Ensemble Model based on bagging for stability |
|Gradient Boosing | 0.91 | 12044.99 | Advanced model based on boosting for iterative error optimization |
### Final Conclusion 
**1. The Champion: Random Forest**
   
   After rigorous testing and benchmarking, **Random Forest Regressor** has been selected as the final model for deployment. It achieved the highest accuracy (R-Squared ~0.98) and the lowest prediction error, outperforming both the baseline Linear Regression and the advanced Gradient Boosting model.
   
**2. Critical Insight**

   A key finding from this experiment involves the Gradient Boosting model. Despite being theoretically more "advanced" and complex, it did not surpass Random Forest in this specific scenario.This validates a crucial data science principle: Complexity $\neq$ Superiority.
   * Fit to Purpose: For this specific dataser size and structure, the stability offered by Random Forest's bagging technique proved superior to the aggressive error-correction of *boosting*.
   * Robustness : Random Forest demonstrated better generalization with default parameters, making it more realiable choice for production compared to the hyper-sensitive Gradient Boosting.
     
**3. Strategic Decision**

   I strongly recommend deploying the Random Forest model. It offers the perfect balance of high precision and reliability, providing the HR team with a trustworthy benchmark for salary negotiations.
