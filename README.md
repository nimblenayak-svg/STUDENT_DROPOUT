# STUDENT_DROPOUT
Education Dropout Prediction
Project Goal
The primary goal of this project is to build and evaluate a Logistic Regression model to predict student dropout (Dropped_Out = 1) based on academic and socio-economic performance metrics. The key features considered are Attendance_Percentage, Previous_Grades, Study_Hours_Per_Week, and Family_Income.

Table of Contents
Data Loading
Checking and Treating Null Values
Visualizing and Treating Outliers
Exploratory Data Analysis & Correlation
Feature Scaling & Data Splitting
Model Training (Logistic Regression)
Model Evaluation
1. Data Loading
The dataset student_dropout_data (1).csv is loaded into a pandas DataFrame.
Initial inspection of the data shape and the first few rows is performed.
2. Checking and Treating Null Values
Null values in Study_Hours_Per_Week and Attendance_Percentage columns are identified.
Missing values are imputed using the median of their respective columns, as the median is robust to outliers.
3. Visualizing and Treating Outliers
Boxplots are used to visualize the distribution of numerical features and identify outliers before treatment.
The IQR (Interquartile Range) method is applied to Study_Hours_Per_Week, Attendance_Percentage, Previous_Grades, and Family_Income to cap outliers and prevent them from unduly influencing the model.
Boxplots are generated again to show the effect of outlier treatment.
4. Exploratory Data Analysis & Correlation
Class Distribution: A countplot visualizes the distribution of the Dropped_Out target variable (0: Retained, 1: Dropped Out).
Feature Correlation Matrix: A heatmap displays the correlation between all numerical features and the target variable, providing insights into potential relationships.
5. Feature Scaling & Data Splitting
The dataset is split into features (X) and the target variable (y).
Data is divided into training (80%) and testing (20%) sets using train_test_split, with stratify=y to maintain the proportion of dropout cases in both sets.
Features are scaled using StandardScaler to ensure that all features contribute equally to the model, as Logistic Regression performs best with scaled features.
6. Model Training (Logistic Regression)
A Logistic Regression model is initialized with class_weight='balanced' to handle potential class imbalance in the Dropped_Out variable and random_state=42 for reproducibility.
The model is trained using the scaled training data (X_train_scaled, Y_train).
7. Model Evaluation
Predictions are made on the scaled test data (X_test_scaled).
The model's performance is evaluated using:
Accuracy Score: The overall correctness of the predictions.
Classification Report: Provides precision, recall, and f1-score for each class.
Confusion Matrix: A heatmap visually represents the true positives, true negatives, false positives, and false negatives, giving a detailed view of the model's predictive capability.
Conclusion
This notebook provides a complete workflow for predicting student dropout using a Logistic Regression model, from data preprocessing to model evaluation. The results show a highly accurate model, which can be further refined with more advanced techniques or additional features if available.

