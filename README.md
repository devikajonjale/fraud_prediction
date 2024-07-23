# Fraud_Prediction
This project was made as an INSAID task/ assignment for Accredian Internship.

## Business Context:
This case requires trainees to develop a model for predicting fraudulent transactions for a financial company and use insights from the model to develop an actionable plan. Data for the case is available in CSV format having 6362620 rows and 10 columns. 

## Data Dictionary & Source Acquisition:
- Data Dictionary: https://drive.google.com/uc?id=1VQ-HAm0oHbv0GmDKP2iqqFNc5aI91OLn&export=download
- Dataset:  https://drive.google.com/uc?export=download&confirm=6gh6&id=1VNpyNkGxHdskfdTNRSjjyNa5qC9u0JyV

## Expectations:
The task is to execute the process for proactive detection of fraud while answering following questions.
1. Data cleaning including missing values, outliers and multi-collinearity.
   - The process is decribed in detail in the jupyter notebook (please check there)
  
2. Describe your fraud detection model in elaboration.
   - ML Models used in this Fraud Detection Model that are best suited for handling imbalanced datasets and maintaining high accuracy:
   - - Decision Tree
     - Random Forest Classifer
     - XGBoost Classifier
  
3. How did you select variables to be included in the model?
   - The variables were selected using variance inflation factor and correlation heatmap.
   - I only had to check if there are any two attributes highly correlated to each other and then drop the one which is less correlated to the isFraud Attribute.

4. Demonstrate the performance of the model by using best set of tools.
   - Here for odel evaluation metrics like accuracy, precision, recall, F1-score and AUC-ROC were used due to imbalanced datset
   - Classification report, confusion matrices and ROC curves are also created for visualization
  
5. What are the key factors that predict fraudulent customer?
   - Location mismatch: When transaction location is significantly different from the usual location.
   - Unusual time: When transactions are made at an unusual time of day or night.
   - Large transaction amount: When the transaction amount exceeds a user's typical spending patterns.
   - New device: When transaction is made from a new device not previously used by the user.
   - Multiple failed login attempts: When there is recent history of failed login attempts from unknown locations.

6. Do these factors make sense? If yes, How? If not, How not?
   - Yes, these factors can be indicative of fraud:
   - - Location mismatch: Suggests someone else might be using the account.
     - Unusual time: Fraudsters might exploit times when users are less likely to be active.
     - Large transaction amount: A significant change from normal spending patterns could be a red flag.
     - New device: Using a new device increases the risk of unauthorized access.
     - Multiple failed login attempts: Suggests someone might be trying to gain unauthorized access.

7. What kind of prevention should be adopted while company update its infrastructure?
   - Multi-factor Authentication: Requires a second factor (e.g., password) for login, making it harder for unauthorized users.
   - Device Fingerprinting: Track user devices and flag transactions from unrecognized devices.
   - Transaction Monitoring: Flag transactions that deviate from user's typical spending patterns.
   - Geolocation Verification: Verify that the transaction location aligns with user's expected location.

8. Assuming these actions have been implemented, how would you determine if they work?
   - Monitor Fraud Rates: Track the number of fraudulent transactions after implementing the new measures.
   - False Positives: Measure the rate of legitimate transactions flagged as fraudulent (reduce if too high).
   - False Negatives: Monitor the rate of fraudulent transactions missed by the system (reduce if possible).
   - Alert Tuning: Adjust alert thresholds based on changes in fraud patterns.

## Conclusion:
In this project we see that the Accuracy of Random Forest, Decision Tree and XGBoost is equal, although the precision of XGBoost is higher.
In a fraud detection model, Precision is highly important because rather than predicting normal transactions correctly we want to know about the Fraud transactions to be predicted correctly.
This is also one of the reason why we used Ensemble techniques here instead of other algorithms.
Another reason for why I have chosen XGBoost is because of the highly unbalanced dataset. XGBoost builds a predictive model by combining the predictions of multiple individual models, often decision trees, in an iterative manner.
