# Customer Churn Prediction & Business Dashboard

A machine learning and business intelligence project that predicts customer churn, identifies customers at risk of leaving, and visualizes actionable insights using Power BI.

## 📌 Project Overview

Customer churn occurs when customers stop using a company's products or services. Understanding churn helps businesses identify retention problems and make better decisions.

This project uses the Telco Customer Churn dataset to analyze customer behavior, train machine learning classification models, estimate churn probabilities, and build an interactive Power BI dashboard.

The project combines **Data Analytics, Machine Learning, and Business Intelligence** in one end-to-end workflow.

## 🎯 Project Objectives

- Analyze customer churn patterns using Exploratory Data Analysis (EDA).
- Clean and prepare customer data for machine learning.
- Perform feature engineering to create useful customer attributes.
- Train and compare multiple classification algorithms.
- Evaluate models using accuracy, precision, recall, F1-score, and cross-validation.
- Predict customer churn probabilities and categorize customers by risk.
- Develop a Power BI dashboard to communicate business insights.
- Demonstrate how machine learning predictions can support customer retention strategies.

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Python | Data analysis and machine learning |
| Pandas | Data cleaning and manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Exploratory data analysis |
| Scikit-learn | Preprocessing, model training, and evaluation |
| Kaggle Notebooks | Development and experimentation |
| Microsoft Power BI | Interactive business dashboard |
| GitHub | Project documentation and version control |

## 📂 Dataset

**Dataset:** Telco Customer Churn

The dataset contains customer information such as tenure, contract type, payment method, monthly charges, services subscribed to, and churn status.

**Target variable:** `Churn`

- `0` — Customer did not churn
- `1` — Customer churned

The original dataset contains 7,043 customer records. The exported prediction file used for the Power BI dashboard contains 1,409 test customers.

Dataset source: [Telco Customer Churn on Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

Please refer to the dataset page for its terms and licensing information.

## 🔄 Project Workflow

### 1. Data Cleaning

- Converted `TotalCharges` to a numeric data type.
- Handled missing values using a preprocessing pipeline.
- Removed `customerID` from the machine learning features because it is an identifier rather than a meaningful predictive attribute.
- Converted the target variable into binary values.

### 2. Exploratory Data Analysis (EDA)

Visualizations were used to investigate customer behavior and churn patterns, including:

- Overall churn distribution.
- Churn rate by contract type.
- Churn rate by customer tenure group.
- Monthly charges compared between churned and retained customers.
- Correlation analysis of numerical features.

### 3. Feature Engineering

Additional features were created to represent customer behavior more effectively:

- **TenureGroup:** Groups customers by the length of their relationship with the company.
- **MonthlyChargesGroup:** Categorizes customers based on monthly charges.
- **TotalServices:** Counts selected services subscribed to by each customer.
- **IsLongTermCustomer:** Identifies customers with at least 24 months of tenure.

### 4. Data Preprocessing

A Scikit-learn preprocessing pipeline was used to prepare the data:

- Median imputation for missing numerical values.
- Standard scaling of numerical features.
- Most-frequent imputation for missing categorical values.
- One-hot encoding for categorical features.
- ColumnTransformer to apply suitable transformations to each feature type.

The dataset was split into training and testing sets using an 80:20 split, with stratification to preserve the target class proportions.

### 5. Machine Learning Models

Four classification models were trained and compared:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier
4. AdaBoost Classifier

The models were evaluated using the same train-test split and preprocessing workflow.

## 📊 Model Evaluation Results

The following results were obtained from the test set:

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 79.8% | 65.1% | 51.9% | 57.7% |
| Decision Tree | 71.8% | 46.9% | 48.9% | 47.9% |
| Random Forest | 77.4% | 59.6% | 46.5% | 52.3% |
| AdaBoost | 79.3% | 63.3% | 52.7% | 57.5% |

**Best model by test F1-score: Logistic Regression**

Logistic Regression achieved an F1-score of approximately 57.7%, with an accuracy of approximately 79.8%. AdaBoost achieved a similar F1-score of approximately 57.5%.

Five-fold cross-validation was also performed using F1-score to assess model performance across different data splits.

These results show that accuracy alone is not sufficient for churn prediction. Precision, recall, and F1-score are also important because businesses need to identify customers who may leave.

## 📈 Power BI Dashboard

The Power BI dashboard translates the analysis and prediction outputs into business-friendly visuals.

### Dashboard Features

- Key performance indicator (KPI) cards.
- Customer churn and retention analysis.
- Churn rate by customer tenure group.
- Customer risk distribution.
- Monthly charges analysis.
- Churn probability analysis.
- Customer-level prediction table.

### Dashboard Preview

![Customer Churn Prediction and Business Dashboard](dashboard_overview.png)

To explore the editable dashboard, download `Customer_Churn_Dashboard.pbix` from this repository and open it using Microsoft Power BI Desktop.

## 📁 Repository Structure

```text
customer-churn-prediction-dashboard/
│
├── Customer_Churn_Prediction.ipynb
├── Customer_Churn_Dashboard.pbix
├── customer_churn_predictions.csv
├── dashboard_overview.png
└── README.md
```

## 💡 Business Insights & Applications

The project demonstrates how customer churn analysis can help businesses:

- Identify customer groups with higher churn rates.
- Understand how contract type, tenure, and monthly charges relate to churn.
- Prioritize high-risk customers for retention campaigns.
- Explore customer behavior through an interactive dashboard.
- Use model predictions to support data-driven retention decisions.

The model identifies patterns in historical customer data. Its predictions are estimates and should be combined with business knowledge before taking action.

## 🚀 How to Use This Project

1. Open `Customer_Churn_Prediction.ipynb` on GitHub to review the notebook code and saved outputs.
2. Download the notebook to run or modify the machine learning workflow in Kaggle or Jupyter, using the appropriate dataset path.
3. Open `Customer_Churn_Dashboard.pbix` in Power BI Desktop to explore the report.
4. If you want to refresh the dashboard using the exported predictions, download `customer_churn_predictions.csv` and update the file source in Power BI if necessary.

## 📚 Key Learning Outcomes

Through this project, I practiced:

- Data cleaning and preprocessing.
- Exploratory data analysis and visualization.
- Feature engineering.
- Building Scikit-learn pipelines.
- Training and comparing classification models.
- Evaluating machine learning performance.
- Generating churn probabilities and customer risk categories.
- Creating a business-focused Power BI dashboard.
- Presenting an end-to-end analytics project using GitHub.

## 🔮 Future Improvements

- Tune model hyperparameters and evaluate additional classification approaches.
- Improve churn recall while monitoring precision and false positives.
- Add model explainability to identify the factors driving individual predictions.
- Publish an interactive dashboard through an appropriate Power BI sharing option.
- Monitor model performance as new customer data becomes available.



## ⭐ Acknowledgements

Thanks to the creators of the Telco Customer Churn dataset and the open-source Python and Scikit-learn communities for the resources used in this project.

---

*This project was developed for learning and portfolio purposes. Model results are specific to the dataset split and evaluation procedure used in this notebook.*
