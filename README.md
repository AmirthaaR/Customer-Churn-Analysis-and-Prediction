# Customer Churn Analysis and Prediction

## Project Overview

Customer Churn Analysis is a machine learning project that predicts whether a telecom customer is likely to leave a service provider.

The project uses customer demographic information, account details, service subscriptions, and billing information to identify customers who may be at risk of churning.

A **Gradient Boosting Classifier** is used as the final prediction model. An interactive web interface built with Gradio allows users to enter customer details and receive churn predictions along with estimated churn probabilities.

## Objectives

- Analyze customer data to identify churn patterns.
- Perform data cleaning and exploratory data analysis.
- Preprocess numerical and categorical features.
- Train and compare multiple machine learning models.
- Evaluate model performance using classification metrics.
- Build an interactive customer churn prediction interface.

## Dataset

**Dataset:** IBM Telco Customer Churn

- Total records: 7,043
- Total features after removing customer ID: 20, including the target variable.
- Target variable: `Churn`
- Churn categories: `Yes` and `No`

The dataset contains customer information such as:
- Gender, senior citizen status, partner and dependents.
- Tenure and subscribed services.
- Internet service and additional features.
- Contract type and payment method.
- Monthly charges and total charges.

**Dataset source:** [IBM Telco Customer Churn Dataset](https://github.com/IBM/telco-customer-churn-on-icp4d)

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Gradio
- Joblib
- Google Colab

## Project Workflow

### 1. Data Cleaning
- Loaded and inspected the dataset.
- Removed the `customerID` column.
- Converted `TotalCharges` into numeric format.
- Handled 11 missing values in `TotalCharges` by replacing them with zero because those customers had zero tenure.
- Checked for duplicate records.

### 2. Exploratory Data Analysis
Analyzed customer churn patterns based on:
- Contract type.
- Customer tenure.
- Monthly charges.
- Internet service.
- Payment method.
- Senior citizen status.

### 3. Data Preprocessing
- Separated input features and target variable.
- Applied StandardScaler to numerical features.
- Applied OneHotEncoder to categorical features.
- Used stratified train-test splitting (80:20).

### 4. Model Training

Three machine learning algorithms were trained and compared:

- Logistic Regression
- Random Forest Classifier
- Gradient Boosting Classifier

### 5. Model Evaluation and Threshold Tuning

Models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

The classification threshold was tuned using validation data to improve the balance between precision and recall for churn predictions.

### 6. Final Model

**Selected Model:** Gradient Boosting Classifier

The final model achieved the following test results:

| Metric | Score |
|---|---:|
| Accuracy | 78% |
| Churn Precision | 58% |
| Churn Recall | 69% |
| Churn F1-score | 63% |

Selected prediction threshold: **0.37**

### 7. Interactive Prediction Interface

A Gradio-based interface was developed to allow users to:

- Enter customer information.
- Submit customer details for prediction.
- View whether the customer is likely to churn or stay.
- View the estimated churn probability.

## Sample Prediction

Example output for a sample customer:

```text
Prediction: Likely to Churn
Churn Probability: 74.00%
```

## Project Structure

```text
Customer-Churn-Analysis/
│
├── Customer_Churn_Analysis.ipynb
├── customer_churn_model.pkl
├── screenshots/
│   └── churn_prediction.png
│
└── README.md
```

## How to Run

1. Download or clone this repository.
2. Open `Customer_Churn_Analysis.ipynb` using Google Colab.
3. Upload the dataset `Telco-Customer-Churn.csv`.
4. Run the notebook cells in order.
5. Install Gradio if it is not already available:

```python
!pip install gradio
```

6. Run the Gradio interface cell to launch the prediction application.

## Key Learnings

- Data cleaning and preprocessing.
- Exploratory data analysis.
- Handling imbalanced classification datasets.
- Feature scaling and categorical encoding.
- Training and comparing machine learning algorithms.
- Model evaluation and threshold optimization.
- Building interactive ML applications using Gradio.

## Limitations

- The model is trained on a historical telecom benchmark dataset.
- Predictions are estimates and do not guarantee actual customer behavior.
- Model performance may vary when applied to real-world telecom datasets.

## Author

**Amirthaa R.**

B.Tech Computer Science and Engineering
