## Bankruptcy Prediction Analysis  

### 1. Introduction  
Financial stability is a cornerstone for sustainable economic growth, and the ability to predict bankruptcy at an early stage can significantly reduce financial risk. This project undertakes a data-driven approach to bankruptcy prediction by utilizing machine learning techniques applied to financial ratios derived from corporate financial statements. The goal is to build predictive models that accurately identify companies at risk of bankruptcy, thereby enabling proactive risk management. 
  
This analysis leverages a structured dataset containing multiple financial indicators. The primary objective is to identify patterns within the data that can reliably distinguish between bankrupt and non-bankrupt entities.  

### 2. Dataset Overview  
The dataset comprises financial ratios from a number of companies, including metrics such as profitability, leverage, liquidity, and operational efficiency. Each entry in the dataset is labeled with a binary indicator denoting whether the company is bankrupt (1) or not (0). The financial ratios serve as predictive features.  

**2.1 Features and Target Variable**  
Features: Financial ratios (e.g., ROA, debt-to-equity ratio, current ratio, etc.)  
  
Target: Bankrupt? (Binary classification: 1 = Bankrupt, 0 = Non-bankrupt)  
  
These features were selected based on their relevance in evaluating a firm’s solvency and overall financial health.  
  
### 3. Exploratory Data Analysis (EDA)  
**3.1 Class Distribution**  
One of the first steps in the analysis was to examine the class distribution of the target variable. A significant imbalance was observed, with bankrupt companies forming a small minority. This imbalance poses a challenge for standard classification models, which tend to be biased toward the majority class.  
  
**3.2 Data Preprocessing**  
Handling Imbalance: The SMOTE (Synthetic Minority Over-sampling Technique) method was used to generate synthetic examples of the minority class. This helped to balance the dataset and reduce model bias.  
  
Feature Scaling: Standardization was applied to scale the features, ensuring all variables contribute equally to the model performance.  
  
**3.3 Correlation Analysis**  
A correlation heatmap was constructed to identify multicollinearity and relationships between features. This helped in selecting relevant features and removing redundant ones.  
  
### 4. Feature Selection  
To improve model performance and interpretability, recursive feature elimination (RFE) and tree-based feature importance methods were used. The most influential predictors identified included:  

Net Profit Margin  

Debt to Total Assets Ratio  

Return on Equity  

Operating Profit to Total Assets  

Retained Earnings to Total Assets  

These indicators were retained for model development, as they were most correlated with bankruptcy likelihood.  
  
### 5. Model Development  
Several machine learning algorithms were trained and evaluated on the processed dataset:  
  
**5.1 Logistic Regression**  
Strengths: Simplicity and interpretability.  
  
Performance: Logistic regression provided a baseline model. While it was able to capture some of the trends, it struggled with recall due to the initial class imbalance.  
  
**5.2 Random Forest Classifier**  
Strengths: Handles non-linear relationships, robust to overfitting.  
  
Performance: The random forest model showed improved performance, particularly in recall and F1-score. It also provided insight into feature importance.  
  
**5.3 XGBoost Classifier**  
Strengths: Gradient boosting method with strong predictive power and efficiency.  
  
Performance: XGBoost outperformed other models in terms of precision, recall, and AUC score. It demonstrated the best ability to identify bankrupt firms correctly, making it the final selected model for deployment.  

### 6. Model Evaluation  
Each model was evaluated using the following metrics:  
  
Accuracy: Overall correctness of the model.  

Precision: How many predicted bankruptcies were correct.  

Recall: How many actual bankruptcies were correctly predicted.  
  
F1 Score: Harmonic mean of precision and recall.  
  
ROC-AUC: Probability curve that quantifies the model’s ability to distinguish between classes.  
  
### Summary of Results:
Model	Accuracy	Precision	Recall	F1 Score	AUC Score  
Logistic Regression	Moderate	Moderate	Low	Low	Fair  
Random Forest	High	High	Moderate	Moderate	Good  
XGBoost	Highest	Highest	Highest	Highest	Excellent  

The XGBoost model achieved the best results, particularly in critical areas such as recall and AUC, which are crucial for identifying high-risk (bankrupt) cases.  
  
### 7. Interpretation and Business Implications  
**7.1 Key Drivers of Bankruptcy**  
The analysis revealed several financial ratios that significantly influence bankruptcy risk:  
  
Low profitability and efficiency metrics often precede bankruptcy.  

High leverage (debt relative to assets or equity) strongly correlates with financial distress.  

Poor liquidity and insufficient earnings retention are also major red flags.

7.2 Use Case in Financial Services
Credit Risk Assessment: Financial institutions can deploy the model to assess loan applicants.

Early Warning Systems: Corporations and investors can use the insights to monitor business partners.

Portfolio Management: Asset managers can flag high-risk investments based on financial signals.

### 8. Limitations and Considerations  
Data Size: The dataset is relatively small, and model generalization might be limited.  
  
Imbalanced Labels: Even after using SMOTE, real-world deployment may face natural imbalances.  
  
Temporal Factors: The model doesn’t incorporate time-based financial trends (e.g., seasonality or macroeconomic factors).  
  
### 9. Conclusion  
This project successfully demonstrates the application of machine learning models to predict corporate bankruptcy using financial ratios. Among the tested models, XGBoost stood out in terms of accuracy and reliability. The results underscore the value of predictive analytics in financial risk assessment and highlight the importance of data preprocessing and feature engineering in achieving high performance.  


