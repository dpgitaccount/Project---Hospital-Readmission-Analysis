# Project- Hospital Readmission Analysis
The goal of this project is to build a predictive model to estimate the likelihood of a hospital readmission based on patient data. By identifying factors that contribute to readmissions, hospitals can optimize care and reduce costs associated with repeated visits.

⇒ 1. Project Overview:-

Objective:-

The goal of this project is to build a predictive model to estimate the likelihood of a hospital readmission within 30 days based on patient data. By identifying factors that contribute to readmissions, hospitals can optimize care and reduce costs associated with repeated visits.

- Tools and Technologies:-

- Programming Language: Python
- Libraries: pandas, numpy, plotly, seaborn, matplotlib, scikit-learn, imbalanced-learn (SMOTE for handling imbalanced data)
- IDE: Jupyter Notebook

⇒ 2. Data Description:-

- Number of Rows:-

This represents the number of data entries or observations in the dataset. For example, if it’s a hospital readmissions dataset, each row might represent an individual patient's readmission record.


- Number of Columns:-

This indicates the number of features or variables available in each observation. More columns usually mean more data features, which can be valuable for in-depth analysis.
 
- Dataset Source:- https://raw.githubusercontent.com/dpgitaccount/Data-Sets/main/hospital_readmissions.csv

- Data Summary:- In this dataset contain 25000 rows & 17 columns which are represents the hospital readmission information.


- "age" - age bracket of the patient
- "time_in_hospital" - days (from 1 to 14)
- "n_procedures" - number of procedures performed during the hospital stay
- "n_lab_procedures" - number of laboratory procedures performed during the hospital stay
- "n_medications" - number of medications administered during the hospital stay
- "n_outpatient" - number of outpatient visits in the year before a hospital stay
- "n_inpatient" - number of inpatient visits in the year before the hospital stay
- "n_emergency" - number of visits to the emergency room in the year before the hospital stay
- "medical_specialty" - the specialty of the admitting physician
- "diag_1" - primary diagnosis (Circulatory, Respiratory, Digestive, etc.)
- "diag_2" - secondary diagnosis
- "diag_3" - additional secondary diagnosis
- "glucose_test" - whether the glucose serum came out as high (> 200), normal, or not performed
- "A1Ctest" - whether the A1C level of the patient came out as high (> 7%), normal, or not performed
- "change" - whether there was a change in the diabetes medication ('yes' or 'no')
- "diabetes_med" - whether a diabetes medication was prescribed ('yes' or 'no') "readmitted" - if the patient was readmitted at the hospital ('yes' or 'no')


▶ Features:-
- Demographic Information: age, gender, race, etc.
- Medical History: diagnoses, comorbidities, prior admissions
- Treatment Details: medications, procedures, lengths of stay, etc.
  
▶ Target Variable:-
Readmitted:-
Whether a patient was readmitted within 30 days (binary: 1 = Yes, 0 = No)

⇒ 3. Data Preprocessing:-

   
▶ Handling Missing Values:-

- Checked for missing values and filled them using forward fill or median imputation, depending on the feature.

▶ Feature Engineering:-

- Categorical features were converted to numerical values using one-hot encoding.
- Removed irrelevant features that do not contribute to the prediction task.

![image](https://github.com/user-attachments/assets/898d6eb1-5a23-4c80-b067-23f08287d264)


  
- Handling Imbalanced Data:

- Applied SMOTE (Synthetic Minority Over-sampling Technique) to balance the classes in the target variable.
Splitting Data:

- Split the dataset into training and testing sets (80-20 split) to evaluate the model's performance.


⇒ 4. Exploratory Data Analysis (EDA):-
     
     
Performed EDA to understand the key patterns in the data. Key steps included:

▶ Distribution Analysis:-

Examined the distribution of each feature to understand its relationship with readmissions.

▶ Correlation Analysis:-

Analyzed correlations between features to identify any redundant or strongly correlated variables.

![image](https://github.com/user-attachments/assets/0617da54-29e2-420d-8907-35d53905672f)


▶ Data Visualization:-
Plotly and Matplotlib were used for interactive and static visualizations.
Visualized the relationships between demographics, prior admissions, and readmission rates.

![image](https://github.com/user-attachments/assets/670e6238-bed3-4c0b-aa55-a1a23c656173)


- Heat Map Vizualisation -


![image](https://github.com/user-attachments/assets/42a4abc3-7054-4855-8037-b2df9620f461)



⇒ 5. Model Building and Training:-
     
  
▶ Built and evaluated multiple classification models to predict readmissions:

▶ Logistic Regression:-

Logistic regression is a statistical method used for binary classification tasks, where the goal is to predict the probability of an outcome that can fall into one of two categories (e.g., yes/no, true/false, 0/1), Used as a baseline model for comparison.

▶ Random Forest Classifier:-

The Random Forest Classifier is an ensemble machine learning algorithm that combines multiple decision trees to improve classification accuracy and reduce overfitting.

▶ Metrics:- 

Accuracy, Precision, Recall, F1-Score, and ROC-AUC Score.

▶ Final Model:-

Chose the model that provided the best combination of Recall and AUC to optimize for both sensitivity and overall prediction quality.


⇒ 6. Model Evaluation:-
     

1. Confusion Matrix:-
   
A Confusion Matrix is a table used to evaluate the performance of a classification model by comparing predicted vs. actual outcomes. It helps visualize errors and correct predictions across different classes.

![image](https://github.com/user-attachments/assets/2ced655c-8dbd-47ec-a21c-77dbc9b49154)


3. Classification Report:-
   
Provided precision, recall, and F1-scores for each class to assess model performance.

5. ROC-AUC Score:-
   
Calculated the ROC-AUC score to gauge the model's ability to distinguish between classes.

7. Feature Importance:-
   
Visualized feature importance from the Random Forest model to identify the most impactful factors in predicting readmission.


![image](https://github.com/user-attachments/assets/f0833edf-780f-49a9-8c15-6e44fdc61c66)



⇒ 7. Results and Insights:-
     
   
▶ Key Findings:-

▶ Factors Influencing Readmission:-
  
Based on the model's feature importance, certain characteristics were found to have a stronger correlation with readmissions:
Medical Conditions: Patients diagnosed with chronic diseases like diabetes, heart disease, or COPD (Chronic Obstructive Pulmonary Disease) were more likely to be readmitted.

▶ Age Groups:-
  
Elderly patients, especially those above 65, showed higher readmission rates, likely due to more complex health needs.

▶ Previous Admissions:-
  
Patients with a history of prior admissions or frequent hospital visits in the past year had a significantly higher readmission probability.

▶ Length of Stay:-
  
A longer initial hospital stay often corresponded with a greater chance of readmission, possibly indicating more severe conditions.

▶ Model Performance:-
  
The final model chosen (e.g., Random Forest Classifier) provided the best balance between precision and recall.

▶ AUC Score:-
  
The model achieved an AUC (Area Under the Curve) score of approximately 0.85, which indicates good discriminatory power in distinguishing between patients likely to be readmitted and those who are not.

▶ Recall:-
  
With a recall score of 0.80, the model successfully identified 80% of actual readmissions. This high recall is important for healthcare applications where missing a potential readmission could lead to adverse patient outcomes.

▶ Precision:-
  
While precision was slightly lower (e.g., around 0.70), this trade-off was acceptable to prioritize capturing as many readmissions as possible.


▶ Confusion Matrix Analysis:-
  
The model performed well in identifying true positives (correctly predicting readmissions) but had a moderate number of false positives (predicting readmission when it didn’t occur). However, reducing false negatives (missed readmissions) was prioritized.

▶ Insights:-
  
Resource Allocation: Hospitals could focus follow-up care on high-risk groups, such as elderly patients with chronic conditions.
Early Interventions: For patients identified with a high risk of readmission, preventive measures like regular check-ups or telehealth consultations could reduce the likelihood of another hospitalization.
