#  Heart Disease Analysis Dashboard in Power BI
An interactive Power BI dashboard designed to analyze and visualize patient survival rates based on clinical factors such as age, serum creatinine, ejection fraction, and lifestyle comorbidities.


<img width="1300" height="677" alt="Screenshot 2026-03-27 124509" src="https://github.com/user-attachments/assets/0d18709b-f240-492d-9b67-805578eaefd1" />

# Project Overview

This project aims to provide actionable insights into the factors influencing heart disease survival. By analyzing a clinical dataset, the dashboard highlights how age groups and medical conditions (Anemia, Diabetes, High Blood Pressure, and Smoking) impact patient outcomes.

### Key Metrics Tracked

Overall Survival Rate: Currently at 32% for the analyzed cohort.

Average Age of Survival: 58.83 years.

Survival vs. Death Count: Total survival (132) vs. Total death (62).


### 📈 Dashboard Features

1. Demographics & Survival Trends
   
       .Survival Rate by Age Group: High-level area chart showing survival peaks among different age demographics (highest in the 71+ category for this specific view).

        . Gender Filtering: Interactive toggle to switch between Female and Male patient data.

2. Clinical Factor Analysis

       .Serum Creatinine Levels: A dual-axis chart tracking the average serum creatinine against survival counts across age brackets.
  
         .Ejection Fraction Performance: Visualizes the average heart pumping efficiency (Ejection Fraction) across different age groups.

3. Comorbidity Impact (Sankey/Stream Chart)


         .An "Impact of Smoking, High Blood Pressure, Anemia, and Diabetes" chart that visualizes the distribution of these risk factors across different age groups to identify high-risk clusters.


   ##    🛠️ Tools Used

- Power BI Desktop: For data modeling, DAX calculations, and visualization.

- Power Query: For data cleaning and transformation (ETL).

- DAX: Used for custom measures like Survival Rate % and Average Age.


##  🔢 Technical DAX Measures

  1. Survival Rate %

           .Survival_Rate = DIVIDE(SUM(heart_Disease_clinical_records_[DEATH_EVENT]),COUNT(heart_Disease_clinical_records_[count]))

  2. Average Age of Survival

          .Average_Age _suivival = CALCULATE(AVERAGE(heart_Disease_clinical_records_[age]),heart_Disease_clinical_records_[DEATH_EVENT]=0)

  3. Total Death Count

           .Total_DEATH = CALCULATE( COUNT(heart_Disease_clinical_records_[count]),heart_Disease_clinical_records_[DEATH_EVENT])

##  Data Cleaning & Modeling

     
Data Source:  Heart Failure Clinical Records – UCI Machine Learning Repository Authors: Davide Chicco and Giuseppe Jurman Sourcee.https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records 

Age Binning: Created a conditional column to group ages into 10-year brackets (40-50, 51-60, etc.) for better trend visualization.

Normalization: Adjusted Serum Creatinine and Ejection Fraction units for consistent plotting on dual-axis charts.


## 🎯 Conclusion & Future Work
This dashboard successfully identifies that the 51-60 age group carries the highest volume of cases, while the 71+ group surprisingly shows a high survival rate in this specific cohort, likely due to clinical intervention or sample size. The correlation between Serum Creatinine and survival suggests it is a primary biomarker for patient prognosis.

## Future Enhancements:
Predictive Modeling: Integrate a Machine Learning model (e.g., Logistic Regression or Random Forest) to predict the probability of a DEATH_EVENT based on user-inputted clinical factors.


