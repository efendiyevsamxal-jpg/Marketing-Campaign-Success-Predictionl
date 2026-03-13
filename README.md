Marketing Campaign Success Prediction
Project Overview

The goal of this project is to build a Machine Learning model that predicts whether a marketing campaign will be successful or not.

In real-world marketing campaigns, not every customer responds positively to promotional offers. Companies need to identify the customers who are more likely to respond in order to reduce marketing costs and increase the effectiveness of their campaigns.

In this project, a machine learning pipeline was developed to analyze customer data and predict the outcome of a marketing campaign.

The project includes several important stages such as:

Data exploration

Data preprocessing

Feature engineering

Model training

Model evaluation

Feature importance analysis

The final model predicts whether a customer will respond positively to a marketing campaign based on their personal and financial information.

Random Forest Classification Model

This project focuses on building a Random Forest classification model to predict the target class using structured dataset features.

The objective of the project is to apply a complete machine learning workflow including data analysis, preprocessing, model training, optimization, and prediction on new data.

The model learns patterns from historical data and classifies observations into their respective categories.

Exploratory Data Analysis (EDA)

The first step of the project involved analyzing the dataset to understand its structure and characteristics.

During this stage:

dataset columns and data types were inspected

missing values were checked

feature distributions were analyzed

potential relationships between variables were explored

Exploratory analysis helps identify relevant variables and prepares the dataset for machine learning modeling.

Data Preprocessing

Before training the model, several preprocessing steps were performed:

cleaning and preparing the dataset

selecting relevant features

separating input variables and the target variable

The dataset was structured into:

X (input features)

y (target variable)

This step ensures that the dataset is properly prepared for the machine learning algorithms.

Model Development

The classification model was built using the scikit-learn library.

Random Forest was chosen because it is an ensemble learning algorithm that combines multiple decision trees to improve prediction accuracy and model stability.

Default Random Forest Model

Initially, a default Random Forest model was trained using the standard parameters provided by the library.

This baseline model helps understand the initial performance of the algorithm before optimization.

The model was trained on the training dataset and evaluated using the testing dataset.

Optimized Random Forest Model

After evaluating the default model, the Random Forest classifier was further improved through hyperparameter tuning.

Model parameters such as:

number of trees

tree depth

minimum samples per split

minimum samples per leaf

were adjusted to improve model performance and reduce potential overfitting.

This optimized model provides better predictive performance compared to the default configuration.

Train-Test Split

To evaluate the model properly, the dataset was divided into training and testing subsets.

80% Training Data

20% Testing Data

Model Evaluation

Both the default and optimized models were evaluated using classification metrics.

Evaluation metrics included:

Accuracy – overall prediction correctness

Precision – accuracy of positive predictions

Recall – ability to correctly identify positive cases

F1 Score – balance between precision and recall

Confusion Matrix – detailed view of prediction results

These metrics allow comparison between the default and optimized models.

Model Deployment (Prediction on New Data)

After training and evaluating the optimized model, it was used to generate predictions for new data.

In this stage:

new observations are provided to the model

the trained model processes the input features

the model outputs predicted class labels

This step demonstrates how the trained model can be applied to classify unseen data in real-world scenarios.
