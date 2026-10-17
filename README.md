# Inventory Management AI 📦
### ML-Based Inventory Waste Risk Prediction

## About the Project

This project focuses on using machine learning to understand and predict inventory waste risk in retail businesses. The idea was to explore how factors like inventory levels, sales, demand, pricing, promotions, and seasonality can help identify products that may be at risk of excess inventory or inefficient stock management.

I worked on building a complete machine learning workflow, starting with data cleaning and exploratory data analysis and moving towards feature engineering, model training, evaluation, and business insights.

## Problem Statement

How can historical retail inventory and sales data be used to classify inventory waste risk as Low, Medium, or High?

## Dataset

The project uses a retail inventory and sales dataset containing **76,000 records and 16 columns**.

Some of the variables used in the analysis include:

- Inventory Level
- Units Sold
- Units Ordered
- Demand
- Price and Discount
- Competitor Pricing
- Product Category and Region
- Weather Condition
- Promotion and Seasonality

The dataset also contains date information, which helps in understanding sales patterns and creating time-based features.

## What I Worked On

### 1. Data Cleaning and Exploration

I started by checking the dataset structure, data types, missing values, and consistency. I also explored sales trends, inventory distribution, and other business patterns using visualizations.

### 2. Feature Engineering

I created additional features to capture useful patterns in the data, including calendar features, inventory-to-demand ratios, previous-day values, and rolling averages.

I also created a future-based waste risk target using the following seven-day period. This target was used to classify records into Low, Medium, and High risk categories.

### 3. Data Preprocessing

The preprocessing pipeline handles missing values in numerical and categorical features. Numerical variables are imputed and scaled, while categorical variables are imputed and one-hot encoded.

The preprocessing steps are fitted on the training data to help avoid data leakage.

### 4. Model Training and Comparison

I compared multiple classification approaches to understand how they perform on the inventory waste risk prediction task.

The models include:

- Dummy Classifier as a baseline
- Logistic Regression
- Decision Tree
- Random Forest
- Extra Trees
- XGBoost

### 5. Model Evaluation

I evaluated the models using accuracy, precision, recall, macro F1-score, and weighted F1-score. I also explored feature importance, an ablation study, and robustness across different data subgroups.

### 6. Business Insights and Dashboard

The notebook includes visualizations and a business insights dashboard covering inventory levels, sales, demand, and predicted risk categories. The goal is to connect model outputs with information that could help support inventory planning decisions.

## Model Results

The selected model in the notebook is **Extra Trees**.

Its recorded evaluation results on the chronological test set are:

| Metric | Result |
|---|---:|
| Accuracy | 81.74% |
| Macro F1-score | 56.25% |
| Weighted F1-score | 83.45% |

These results show that the model performs reasonably well overall, but performance across the individual risk classes needs attention.

The dataset is imbalanced, with Low Risk records making up the majority of the target. This is why I also considered macro F1-score instead of relying only on accuracy.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- XGBoost
- SHAP-related tooling and model explainability libraries

## How to Run the Project

The notebook was designed to run in Google Colab.

1. Open the notebook in Google Colab.
2. Run the environment setup and import cells.
3. Upload the retail inventory/sales dataset ZIP file when prompted.
4. Make sure the expected sales CSV file is available and correctly named.
5. Run the notebook cells in order, from data loading through model evaluation and the final dashboard.

The dataset is not included in this repository by default, so you will need to provide the corresponding dataset before running the analysis.

## What I Learned

This project helped me understand how a machine learning problem can be approached from both a technical and a business perspective. I learned how feature engineering, preprocessing, chronological data splitting, and model comparison affect the overall workflow.

I also understood why accuracy alone is not enough when working with imbalanced classes and why it is important to look at additional evaluation metrics.

Another important part of the project was connecting model predictions with business insights, rather than treating model performance as the only outcome.

## Limitations and Future Scope

The model's performance is affected by the imbalance between the risk categories, especially the smaller High Risk class. The risk labels are also derived from future inventory and sales patterns, so they represent the project's chosen definition of waste risk rather than independently verified real-world waste.

In the future, I would like to improve minority-class performance, explore additional forecasting approaches, and evaluate how the predictions could be used in a practical inventory planning system.

---

This project was a step towards applying machine learning to a real business problem and understanding how data-driven insights can support better inventory management.
