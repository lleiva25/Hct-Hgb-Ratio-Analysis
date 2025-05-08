# HCT HGB Ratio Analysis
Retrospective cohort study using randomized patient data to view Hct/Hgb Ratio trend


DESIGN
===========================
•	Number of subjects: 499

•	Date range: January 1st 2024 – April 30th 2025

•	Tests
|Abbreviation | Name | Definition |
| ------------- | ------------- | ------------- |
|HCT	|Hematocrit	|Hematocrit is a blood test that measures the percentage of red blood cells in your blood.|
|HGB	|Hemoglobin	|Test measures the amount of hemoglobin, a protein in red blood cells, in a blood sample.|


GRAPHS & ANALYSIS
===============================
![image](https://github.com/user-attachments/assets/fca6354d-0055-46ef-810d-199e8921a790)

There is a higher concentration of normal-moderate HCT/HGB ratios in the randomized individuals between the age 50-80. In contrast, the 0-40 age range has a less density in the normal HCT/HGB ratio range. Within the study population, we continue to see a variety of outliers are consistent regardless of age range.

![image](https://github.com/user-attachments/assets/f98e7feb-5e34-41c9-83c8-114fc3a6cd5b)
A Pearson correlation coefficient of 0.40 indicates a weak positive relationship between HCT and HGB values. The graph further illustrates that the majority of patients exhibit an HCT/HGB ratio consistent with moderate to severe microcytosis. Note: Because this is randomized data it won't replicate the strong positive (r=0.9) association betwen HCT/HGB Compared to real patients.

![image](https://github.com/user-attachments/assets/57ffcefd-5202-4b8d-8356-49a952cf205b)
Based on ICD-10 diagnostic categories, this graph displays both the gender distribution and the average HCT/HGB ratio across various diagnosis groups. The average HCT/HGB ratios in each category generally fall within the severe - normal range, indicating a relatively stable hematologic profile across diagnoses. Additionally, the gender distribution appears to be approximately balanced, with a near 50/50 male-to-female ratio across categories.

![image](https://github.com/user-attachments/assets/362152b6-b690-42a9-8d9d-255f691a5f70)
The patient population at the hospital is predominantly composed of individuals aged 21–100 years, with significantly fewer encounters recorded for patients under the age of 21. The majority of patients identify as either Unknown or Non-Hispanic, while a the remaining portion of the population either Hispanic or declined to state their ethnicity.

![image](https://github.com/user-attachments/assets/88fb0a4e-5f16-4853-b5ac-2272a8e2f208)
The boxplot presented shows the minimum, maximum, quartiles, and median of the HCT/HGB ratio for the dataset, with outliers removed for clarity. On average, female subjects appear to have moderate-to-normal HCT/HGB ratio, while male subjects tend to display a more fluxuations of HCT/HGB ratio across age groups. Additionally, when comparing age ranges, we observe that the HCT/HGB ratio range is larger in males compared to females, indicating more variability in males across the different age groups with the exception of the age range 21-50.

GLOSSERY
==============================
ICD-10 Codes	Categories
A00-B99	Infectious Diseases
C00-D49	Neoplasms
D50-D89	Hematologic Disorders
E00-E89	Metabolic Diseases
F01-F99	Neurodevelopment Disorders
G00-G99	Neurological Conditions
H00-H59	Ocular Disorders
H60-H95	Otologic Disorders
I00-I99	Cardiovascular Disorders
J00-J99	Respiratory Diseases
K00-K95	Gastrointestinal Disorders
L00-L99	Dermatologic Disorders
M00-M99	Musculoskeletal Diseases
N00-N99	Urogenital Disorders
O00-O9A	Obstetric Conditions
P00-P96	Perinatal Disorders
Q00-Q99	Congenital Anomalies
R00-R99	Laboratory Findings
S00-T88	External Injuries
U00-U85	Special Condition
V00-Y99	External Morbidity
Z00-Z99	Health Influencing Factors


Hematocrit(HCT) : Hemoglobin(HB) Ratio Table
•	Formula: ratio = Hct(%) / Hgb(g/dL)
Ratio	Interpretation
| Ratio %  | Interpretation |
| ------------- | ------------- |
|<2.5%|Severe microcytosis|
|2.5% - 3.0%|Moderate microcytosis|
|3.0% - 3.5%|Normal range|
|3.5% - 4.0%|Mild macrocytosis|
|>4.0%|Moderate to severe macrocytosis|

Ethnicity Demographics
|Abbreviation | Description |
| ------------- | ------------- |
|D| Patient Refused|
|H| Hispanic/Latino|
|N| Non-Hispanic/Latino|
|U| Unknown|

PYTHON MODULES
==============================
|Abbreviation | Description | Purpose |
| ------------- | ------------- | ------------- |
|pd	|pandas	|Data manipulation & analysis|
|Path	|pathLib	|Object-orientated approach to handling filesystem paths|
|plt	|Matplotlib	|Plotting library to visual data|
|np	|numpy	|Fundamental library for multi-dimensional arrays and matrices.|
|gaussian_kde	|scipy.stats	|Probability density function(PDF) of variable in a non-parametric way.|
|stats	|scipy	|Provides more utility functions for optimization, and stats.|
|sns	|seaborn	|High level API that makes informative visual plots.|
|Faker |faker |Generates randomized information|
|datetime, timedelta |datetime |Library class that supports time manipulation|

DATA PROCESSING INSTRUCTIONS
==============================
1.  Generate and randomized patient data.
2.	Storing path file as a variable.
3.	Read raw file and convert to dataframe.
4.	Data clean up consisted of:
a.	Dropping columns: ‘LAST_NAME’, ‘PATIENT’, ‘DOB’, and ‘GROUP_TEST_ID’.
b.	Rename column: ‘DIAG_CODE1” to ‘DIAG_CODE’.
c.	Drop ‘NaN’ and null values for incomplete rows.
d.	Filter age range to only show the age range 0-100.
e.	Bin the ‘AGE” column to the following bins: '0-10','11-20','21-50', and '51-100'.
f.	Drop unknown (U) and patient declined (N) values for the ‘SEX’ column.
g.	Drop duplicate entries.
5.	Calculated the average HCT/HBG Ratio per patient and map it to clean data frame.
6.	Map the ICD-10 Codes to the ‘DIAG_CODE’ to the clean data frame.
7.	Drop rows with incomplete rows.
8.	Convert ‘RESULT’ Column to numeric.
9.	Create a variety of pivot tables and graphs.

SOURCES
==============================
•	Generated randonmized report [HCT HGB Study_Part1]

•	ICD List [ICD-10-CM Codes & Categories]

•	Koperska, M. Hematocrit to Hemoglobin Ratio Calculator [https://www.omnicalculator.com/health/hct-hgb]


