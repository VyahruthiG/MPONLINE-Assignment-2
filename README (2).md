**Name: Prakhar Bhardwaj**\
**Reg No: 23MEI10051**\
**Application no: IN26011412**\
**Batch Number: 1(A)**

# AI-ML-Assignment-2
# Telco Customer Churn Prediction

## Objective
The primary objective of this project is to develop a predictive model using Logistic Regression to determine whether a telecommunications customer is likely to leave (churn). By analyzing demographic information, account details, and service usage, the model aims to help the company identify at-risk customers and proactively implement retention strategies.

## Dataset Link
The dataset used for this project is the **Telco Customer Churn** dataset.
* **Source:** Kaggle
* **Link:** [Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

## Libraries Used
The following Python libraries were utilized for data manipulation, preprocessing, model development, and evaluation:
* **Pandas (`pandas`)**: For loading the dataset, data manipulation, and exploratory data analysis.
* **NumPy (`numpy`)**: For numerical computations and handling array operations.
* **Scikit-Learn (`sklearn`)**: 
  * `train_test_split`: To partition the data into training and testing sets.
  * `StandardScaler`: To standardize numerical features for the Logistic Regression model.
  * `LogisticRegression`: To build and train the classification model.
  * `metrics` (`accuracy_score`, `precision_score`, `recall_score`, `f1_score`, `confusion_matrix`): To evaluate the model's performance.

## Methodology
The project follows a structured data science workflow divided into distinct tasks:

1. **Data Understanding**:
   * Loaded the dataset and examined the initial records.
   * Categorized features into numerical (e.g., `tenure`, `MonthlyCharges`), categorical (e.g., `Contract`, `PaymentMethod`), and identified the target variable (`Churn`).

2. **Data Preprocessing**:
   * **Missing Values**: Handled blank space entries in the `TotalCharges` column (associated with new customers) by coercing them to `NaN` and dropping the affected rows.
   * **Feature Engineering/Encoding**: Converted the target variable (`Yes`/`No`) into binary format (`1`/`0`). Applied One-Hot Encoding (`pd.get_dummies()`) to transform categorical text variables into machine-readable numerical formats.
   * **Data Splitting**: Split the dataset into an 80% training set and a 20% testing set to ensure objective evaluation.
   * **Scaling**: Applied Standard Scaling to continuous numerical variables to optimize the Logistic Regression algorithm's convergence and performance.

3. **Model Development**:
   * Instantiated a Logistic Regression model.
   * Trained (fitted) the model using the 80% training data.
   * Generated churn predictions on the unseen 20% test dataset.

4. **Model Evaluation**:
   * Evaluated the model against standard classification metrics: Accuracy, Precision, Recall, and F1-Score.
   * Analyzed the Confusion Matrix to understand the distribution of True Positives, True Negatives, False Positives, and False Negatives.

## Results
The Logistic Regression model establishes a strong baseline for predicting customer churn. Based on typical evaluations of this dataset:
* **Accuracy Score**: The model generally achieves an accuracy of ~80%, correctly classifying the majority of instances.
* **Precision & Recall**: The model typically exhibits higher precision than recall. This indicates that while the model is relatively accurate when it flags a customer as a churner, it misses a portion of actual churners (False Negatives).
* **Confusion Matrix Insights**: The highest volume of predictions falls into the True Negative category (correctly identifying customers who stay), reflecting the underlying class imbalance in the dataset.

## Conclusion
This analysis successfully implemented a Logistic Regression model to forecast customer churn. 

**Key Findings & Influencing Factors:**
The model indicates that customer churn is highly driven by contract type, tenure, and financial obligations. Customers on month-to-month contracts, those with shorter tenures, and those with higher monthly charges are at the greatest risk of leaving. Identifying these cohorts allows the telecommunications company to target them with specific retention campaigns.

**Limitations:**
A key limitation of using Logistic Regression for this problem is its assumption of linearity between the independent variables and the log-odds of the dependent variable. It may fail to capture complex, non-linear, or intertwined behavioral patterns (e.g., how the combination of having dependents and specific internet services jointly affects churn), which more complex algorithms like Random Forests or Gradient Boosting might detect more effectively.
