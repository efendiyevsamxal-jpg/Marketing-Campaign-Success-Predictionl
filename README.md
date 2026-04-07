📊 Marketing Campaign Success Prediction
📌 Project Overview

This project focuses on predicting the success of a marketing campaign using various machine learning models.

The main objective is to classify whether a customer will respond positively (result) to a marketing campaign based on demographic, financial, and campaign-related features.

The project includes a complete end-to-end machine learning pipeline, starting from data preprocessing to model optimization and interpretation.


📚 Libraries Used

The following Python libraries were used throughout the project:

Data Manipulation & Analysis
pandas
numpy
Data Visualization
matplotlib
seaborn
Machine Learning Models
scikit-learn
xgboost
lightgbm
catboost
Model Evaluation
roc_auc_score
confusion_matrix
classification_report
Feature Engineering & Statistics
scipy
statsmodels (VIF)
Hyperparameter Optimization
optuna

⚙️ Data Preprocessing

All preprocessing steps were carefully applied to improve model performance:

1. Data Cleaning
Dropped unnecessary columns:
ID, pdays, previous
Converted target variable:
"yes" → 0
"no" → 1
2. Feature Engineering

New features were created:

Age Group
Binned age into:
Young
Middle-Aged
Senior
Elderly
Job Average Balance
Mean balance per job category
Balance Difference
Difference between individual balance and job average
3. Encoding
Applied Label Encoding to categorical variables for general models
Used:
One-Hot Encoding (for KNN)
Raw categorical features (for CatBoost)
4. Outlier Treatment (KNN dataset)
Used IQR method
Applied capping instead of removing outliers
5. Distribution Check
Used Kolmogorov-Smirnov test to check normality
6. Feature Selection
Correlation Analysis
Spearman correlation used
Selected features based on correlation with target
Multicollinearity Check
Used:
Correlation filtering
VIF (Variance Inflation Factor)
7. WOE Transformation (for Logistic Regression)
Numerical variables converted into categories using quantiles
Weight of Evidence (WOE) applied
Selected variables based on correlation

8. Dataset Splitting

Created multiple datasets:

inputs → general models
inputs_knn → KNN
inputs_lr → Logistic Regression (WOE)
inputs_cat → CatBoost (categorical)

Split into:

Train (70%)
Test (30%)

 Default Models

The following baseline models were trained:

Logistic Regression
KNN (K-Nearest Neighbors)
Random Forest
XGBoost
LightGBM
CatBoost
CatBoost (with categorical features)

Each model was evaluated using:

ROC-AUC
Gini coefficient

Model Optimization with Optuna

Hyperparameter tuning was performed using Optuna for 5 models:

KNN
Random Forest
XGBoost
LightGBM
CatBoost

Each model was optimized using:

Cross-validation
ROC-AUC as scoring metric

Model Selection

The best model was not selected based on a single metric. Instead, multiple evaluation criteria were considered:

Test Gini score (overall model performance on unseen data)
Train Gini score (model learning capacity)
Gini Gap (difference between Train and Test scores)

👉 The Gini Gap indicates the level of overfitting.

The goal of the selection process was to achieve:

High test performance
Low overfitting (small Gini Gap)

All models were compared based on these criteria, and the final selection was made by choosing the model that provided the best balance between performance and generalization.

➡️ As a result, the Optimized XGBoost model (tuned with Optuna) was selected as the best-performing model.

Feature Importance

Using the best model:
importances = best_xgb_model.feature_importances_
Normalized feature importance calculated
Features with importance > 1% selected

Model Interpretation (SHAP Analysis)

To understand how our XGBoost model makes decisions, we utilized the SHAP (SHapley Additive exPlanations) methodology. The SHAP Summary Plot highlights the following key insights:

Housing: Interestingly, customers with an existing housing loan (value=1, red) show a higher probability of responding positively to the campaign compared to those without one.

Balance: Higher account balances are positively correlated with campaign success, indicating that financial stability is a key driver for customer engagement.

Final Model Building

Selected most important features:

important_features_df['Feature'].tolist()

Created final dataset:
X_train_fin, X_test_fin, y_train_fin, y_test_fin = train_test_split(...)

Final Model (Optimized XGBoost)

Best parameters obtained via Optuna:

best_xgb_model_fin = XGBClassifier(**best_params, random_state=42)
Final evaluation:
train_and_evaluate_model(
    'XGB optimized for selected features',
    best_xgb_model_fin,
    X_train_fin,
    y_train_fin,
    X_test_fin,
    y_test_fin
)

Conclusion
Multiple ML models were tested and compared
Hyperparameter tuning significantly improved performance
XGBoost achieved the best results
SHAP provided strong interpretability
Feature selection improved model efficiency and generalization
optuna
Model Explainability
shap
