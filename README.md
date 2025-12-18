# Stroke Risk Prediction & Patient Safety Analysis
## Problem Statement
According to the World Health Organization (WHO), stroke is the 2nd leading cause of death globally, responsible for approximately 11% of total deaths. Early detection of high-risk individuals is a major public health priority. This project applies supervised machine learning techniques to predict stroke occurrence using demographic and clinical healthcare data.

## Project Objectives
1. Identify Risk Factors: Determine which variables (e.g., age, hypertension, glucose levels) most strongly correlate with stroke.
2. Optimize for Recall: Achieve a minimum of 90% Recall to minimize false negatives, ensuring that potential stroke victims are not missed during screening.
3. Clinical Utility: Provide a preliminary screening tool to flag patients for further medical review.

## Dataset Overview
The data is obtained from ([kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)).
Dataset contains 5,110 rows with 11 features:
•	Demographics: Gender, Age, Marital Status, Work Type, Residence Type.
•	Clinical Markers: Hypertension, Heart Disease, Average Glucose Level, BMI.
•	Lifestyle: Smoking Status.
•	Target: Stroke (1 if the patient had a stroke, 0 otherwise).

### Attribute Information

1) id: unique identifier
2) gender: "Male", "Female" or "Other"
3) age: age of the patient
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
6) ever_married: "No" or "Yes"
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
8) Residence_type: "Rural" or "Urban"
9) avg_glucose_level: average glucose level in blood
10) bmi: body mass index
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
12) stroke: 1 if the patient had a stroke or 0 if not

## Methodology
1. EDA - Analyzed feature distributions and correlations.
2. Data preprocessing - encoded categorical variables using OneHotEncoding(OHE) and scaled numerical features for model consistency.
3. Model selection - Built and evaluated several models;
   - Baseline Model
   - Regularized Model
   - Decision Tree Classifiers

## Key Results
•	Recall: Achieved 93%, successfully flagging the vast majority of high-risk patients.

•	Feature Insights: Analysis suggests that clinical markers (hypertension, glucose, heart disease) are significantly more critical than demographic factors in predicting risk.

•	Strategic Trade-off: The model prioritizes recall over precision.    While this results in a higher false-positive rate, it serves the project's goal of being a conservative, "safe" screening tool where missing a diagnosis (False Negative) is much costlier than a false alarm(false positive).

## Recommendations
1.	Screening Tool: The model is highly effective as a preliminary screening mechanism for patient intake portals.
2.	Medical Review: Flagged individuals should immediately receive blood pressure and glucose screenings.
3.	Limit on Diagnosis: Because of the high false-positive rate, this tool should be used for risk-flagging only, not as a definitive medical diagnosis.

## Technical Stack
•	Language: Python
•	Libraries: Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn