# Titanic-Survival-Analysis
Titanic Data Cleaning in Python and Power BI Dashboard

Data Cleaning · Dashboard · Insight Report

# Project Overview
This project takes on the role of a data analyst working with the famous Titanic passenger dataset. The goal was to simulate a real industry workflow — starting from a raw, messy dataset and ending with a cleaned dataset, an interactive dashboard, and a professional insight report with business recommendations.

The central question driving the analysis:
What factors determined whether a Titanic passenger survived?
The project was completed in three phases:
- Phase 1 — Data Cleaning in Python
- Phase 2 — Dashboard in Power BI
- Phase 3 — Insight Report with Recommendations

# Tools Used
- Python (Pandas) - Data cleaning and feature engineering
- Power BI - Interactive dashboard and visualisations
- DAX - Calculated measures in Power BI

# Data Cleaning in Python
Cleaning Steps Applied
1. Handle Missing Values
- Age → filled with median (28) — chosen over mean because the distribution is right-skewed
- Cabin → filled with "Unknown" — 77% missing made imputation unreliable
- Embarked → filled with mode ("S") — Southampton accounted for 72% of embarkations
  
2. Fix Data Types
- Survived, Pclass → converted to integer
- Age, Fare → confirmed as float
- Sex, Embarked → converted to category dtype
  
3. Remove Duplicates
- Full row-level check performed
- Result: zero duplicates found — dataset remained at 891 rows
  
4. Standardise Data
- All column names → lowercase
- All string columns → stripped of leading/trailing whitespace
- Sex → standardised to lowercase (male, female)
- Embarked → standardised to uppercase (S, C, Q)
  
5. Feature Engineering — 3 New Columns
- Age group, Family size

# Key Insights
1. Gender Was the Strongest Survival Predictor
Women survived at 74.2%, men at 18.9% — a gap of 55 percentage points.
The "women and children first" evacuation protocol is clearly visible in the data.
2. Passenger Class Determined Your Chances
| Class       | Survival Rate |
|-------------|---------------|
| 1st Class   | 63.0%         |
| 2nd Class   | 47.3%         |
| 3rd Class   | 24.2%         |
Third class made up 55% of all passengers but received the worst outcomes — due to cabin location, distance from lifeboats, and evacuation barriers.

3. Children Had the Best Survival Rate
| Age Group            | Survival Rate |
|---------------------|---------------|
| Child (0–12)        | 58.0%         |
| Teen (13–17)        | 42.9%         |
| Young Adult (18–35) | 35.8%         |
| Adult (36–60)       | 38.4%         |
| Senior (61+)        | 22.7%         |
Children were prioritised during evacuation. Seniors had the worst outcomes, likely due to reduced mobility.

4. Fare Paid Correlated with Survival
Survivors paid an average of £48.4
Non-survivors paid an average of £22.1
Fare captures socioeconomic status at a finer level than class alone — even within the same class, higher-paying passengers had better outcomes.

5. Small Family Groups Outperformed Solo Travellers
Passengers in groups of 2–4 had better survival rates than solo travellers.
Very large groups (7+) had the worst outcomes — coordinating many people in a crisis was impractical.

# Business Recommendations
- Equalise lifeboat access across all deck levels, 39pp gap between 1st and 3rd class survival
- Assign dedicated crew to assist elderly passengers, Seniors had the lowest survival rate at 22.7%
- Provide multilingual safety briefings, 3rd class passengers were largely non-English emigrants
- Introduce buddy or escort system for solo travellers, Solo travellers had below-average survival outcomes
- Use fare and class data for risk-based drill scheduling, Socioeconomic status strongly predicted evacuation success
