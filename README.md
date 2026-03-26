# Titanic-Survival-Analysis
Titanic Data Cleaning in Python and Power BI Dashboard
🚢 Titanic Survival Analysis
Data Cleaning · Dashboard · Insight Report
Easy Technologies Academy — Capstone Project
📌 Project Overview
This project takes on the role of a data analyst working with the famous Titanic passenger dataset. The goal was to simulate a real industry workflow — starting from a raw, messy dataset and ending with a cleaned dataset, an interactive dashboard, and a professional insight report with business recommendations.
The central question driving the analysis:
What factors determined whether a Titanic passenger survived?
The project was completed in three phases:
Phase 1 — Data Cleaning in Python
Phase 2 — Dashboard in Power BI
Phase 3 — Insight Report with Recommendations
🗂️ Dataset
Detail
Info
Source
Titanic passenger records
Rows
891 passengers
Original Columns
12
Final Columns
15 (after feature engineering)
Missing Values
Resolved in all columns
Duplicates
None detected
Original columns:
PassengerId, Survived, Pclass, Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked
Engineered columns added:
age_group, family_size, title
🛠️ Tools Used
Tool
Purpose
Python (Pandas)
Data cleaning and feature engineering
Power BI
Interactive dashboard and visualisations
DAX
Calculated measures in Power BI
Git & GitHub
Version control and project sharing
📁 Project Files
titanic-survival-analysis/
│
├── titanic_cleaning.py              # Python data cleaning script
├── titanic_clean_for_powerbi.csv    # Cleaned dataset (Power BI ready)
├── titanic_insight_report.docx      # Full 5-section insight report
├── titanic_dashboard.html           # Interactive dashboard mockup
└── README.md                        # Project documentation
⚙️ Phase 1 — Data Cleaning in Python
Issues Found in the Raw Dataset
Issue
Column
Detail
Missing values
Age
177 nulls — 20% of records
Missing values
Cabin
687 nulls — 77% of records
Missing values
Embarked
2 nulls
Wrong data types
Survived, Pclass
Stored as float instead of integer
Inconsistent text
Sex, Embarked
Mixed capitalisation
Buried information
Name
Titles hidden in free-text name field
Missing dimensions
Whole dataset
No age bands, family size, or title column
Cleaning Steps Applied
1. Handle Missing Values
Age → filled with median (28) — chosen over mean because the distribution is right-skewed
Cabin → filled with "Unknown" — 77% missing made imputation unreliable
Embarked → filled with mode ("S") — Southampton accounted for 72% of embarkations
2. Fix Data Types
Survived, Pclass → converted to integer
Age, Fare → confirmed as float
Sex, Embarked → converted to category dtype
3. Remove Duplicates
Full row-level check performed
Result: zero duplicates found — dataset remained at 891 rows
4. Standardise Data
All column names → lowercase
All string columns → stripped of leading/trailing whitespace
Sex → standardised to lowercase (male, female)
Embarked → standardised to uppercase (S, C, Q)
5. Feature Engineering — 3 New Columns
New Column
Logic
Purpose
age_group
Child / Teen / Young Adult / Adult / Senior
Age cohort analysis
family_size
SibSp + Parch + 1
Measure travelling group size
title
Extracted from Name via regex, rare titles grouped as "Other"
Social status indicator
Output: titanic_clean_for_powerbi.csv — 891 rows · 15 columns · 0 nulls
📊 Phase 2 — Power BI Dashboard
DAX Measures Created
Survival Rate = DIVIDE(SUM('titanic_clean_for_powerbi'[survived]),
               COUNT('titanic_clean_for_powerbi'[passengerid])) * 100

Total Passengers = COUNT('titanic_clean_for_powerbi'[passengerid])

Total Survivors = SUM('titanic_clean_for_powerbi'[survived])
Visuals Built
Visual
Type
Insight Shown
Survival Rate
KPI Card
38.4% overall survival rate
Survival by Gender
Bar Chart
Female 74.2% vs Male 18.9%
Class Distribution
Donut Chart
55% of passengers were 3rd class
Survival by Age Group
Line Chart
Children highest (58%), Seniors lowest (23%)
Class × Gender
Grouped Bar Chart
1st class female = 97%, 3rd class male = 14%
Fare vs Survival
Bar Chart
Survivors paid £48.4 avg vs £22.1
Slicers added for: Passenger Class · Gender
All charts filter simultaneously when a slicer is selected.
🔍 Phase 3 — Key Insights
Insight 1 — Gender Was the Strongest Survival Predictor
Women survived at 74.2%, men at 18.9% — a gap of 55 percentage points.
The "women and children first" evacuation protocol is clearly visible in the data.
Insight 2 — Passenger Class Determined Your Chances
Class
Survival Rate
1st Class
63.0%
2nd Class
47.3%
3rd Class
24.2%
Third class made up 55% of all passengers but received the worst outcomes — due to cabin location, distance from lifeboats, and evacuation barriers.
Insight 3 — Children Had the Best Survival Rate
Age Group
Survival Rate
Child (0–12)
58.0%
Teen (13–17)
42.9%
Young Adult (18–35)
35.8%
Adult (36–60)
38.4%
Senior (61+)
22.7%
Children were prioritised during evacuation. Seniors had the worst outcomes, likely due to reduced mobility.
Insight 4 — Fare Paid Correlated with Survival
Survivors paid an average of £48.4
Non-survivors paid an average of £22.1
Fare captures socioeconomic status at a finer level than class alone — even within the same class, higher-paying passengers had better outcomes.
Insight 5 — Small Family Groups Outperformed Solo Travellers
Passengers in groups of 2–4 had better survival rates than solo travellers.
Very large groups (7+) had the worst outcomes — coordinating many people in a crisis was impractical.
💼 Business Recommendations
#
Recommendation
Based On
1
Equalise lifeboat access across all deck levels
39pp gap between 1st and 3rd class survival
2
Assign dedicated crew to assist elderly passengers
Seniors had the lowest survival rate at 22.7%
3
Provide multilingual safety briefings
3rd class passengers were largely non-English emigrants
4
Introduce buddy or escort system for solo travellers
Solo travellers had below-average survival outcomes
5
Use fare and class data for risk-based drill scheduling
Socioeconomic status strongly predicted evacuation success
📈 Results Summary
Metric
Value
Total passengers analysed
891
Overall survival rate
38.4%
Highest survival group
1st class females — 96.8%
Lowest survival group
3rd class males — 13.5%
Biggest survival factor
Gender (55pp gap)
Cleaned dataset columns
15
New features engineered
3
Dashboard visuals
6
Key insights
5
Recommendations
5
🚀 How to Run the Cleaning Script
Make sure Python and Pandas are installed
Place titanic_cleaned.csv in the same folder as the script
Run the script:
python titanic_cleaning.py
Output file titanic_clean_for_powerbi.csv will be created automatically
Import this file into Power BI to replicate the dashboard
👩‍💻 About This Project
This project was completed as part of the Easy Technologies Academy structured learning programme.
It demonstrates a full end-to-end data analyst workflow:
Raw Data → Exploration → Cleaning → Feature Engineering
    → Visualisation → Insight → Recommendations → Documentation
#EasyTechTalent
