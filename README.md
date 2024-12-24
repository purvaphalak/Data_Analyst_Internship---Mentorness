# Data Analyst Internship | Mentorness

✦ During this Internship :

- Designed and developed a detailed 4- page Power BI dashboard for NREGA analysis, analysed employment data across 29 states, and over 5 million job cards, Rs. 20,000 crore expenditures, visualizing key metrics like job card issuance, workforce participation, and budget utilization and providing insights into rural employment trends under the NREGA scheme.

- Conducted an in-depth COVID-19 analysis using MySQL, processing data on 169 million+ confirmed cases, 113 million+ recoveries, and 3.6 million+ deaths, identifying regional trends, peak periods, and top recovery rates to deliver actionable insights.

# "Corona-Virus Analysis" using MySQL

► As a part of Data Analyst  Internship at Mentorness, I have been tasked to analyse Corona-Virus Dataset using MySQL.

### 𝐓𝐚𝐬𝐤 𝟐 : Corona-Virus Analysis using MySQL

### ➡️ Objective of the Project :

- The objective of coronavirus analysis is to monitor how COVID-19 spreads and affects people by looking at data on cases, recoveries, and and deaths deaths in  differe different areas over time.

This includes:

- Monitoring the number of confirmed cases, deaths, and recoveries.
  
- Analyzing the geographical spread of the virus using latitude and longitude.
  
- Providing a time series of the pandemic's progression.
  
- This dataset can be used for various analyses, such as:

- Visualizing the spread of COVID-19 on a map.
  
- Identifying trends and patterns in the number of cases, deaths, and recoveries over time.
  
- Comparing the impact of the virus in different regions.
  
- Modeling and forecasting the future course of the pandemic based on historical data. ​

### ➡️Project Description :

✦ The dataset contains a total of 78,000 rows, the data spans from 22 January 2020 to 13 June 2021. This period covers a significant part of the COVID-19 pandemic, including initial outbreaks, various waves, and the rollout of vaccines.

✦ There are 12 months of data present within the date range. This indicates that the dataset might have monthly aggregated data or data recorded over a year's span.

### ➡️ Dataset Includes :

The dataset appears to be a COVID-19 dataset, providing detailed information about the progression of the pandemic. Here are the key features and their descriptions:

- Province: The province or state within the country.

- Country/Region: The country or region where the data was recorded.

- Latitude: Latitude coordinate for the location.

- Longitude: Longitude coordinate for the location.

- Date: The date when the data was recorded.

- Confirmed: The number of confirmed COVID-19 cases.

- Deaths: The number of deaths due to COVID-19.

- Recovered: The number of recovered cases from COVID-19.

### ➡️ SQL Queries and Insights :

![4](https://github.com/user-attachments/assets/e6bac246-a892-44ae-897e-24e32b865586)

#### ➤ Explanation: 
This query checks the dataset for missing values (NULL) in critical columns. Missing values could affect analysis accuracy.

#### ➤ Insight: 
Identifying and addressing missing data ensures the dataset is clean and reliable for further analysis.

![5](https://github.com/user-attachments/assets/364f7c67-780a-4af9-9b6a-edd4cdf35011)

#### ➤ Explanation: 
This query replaces any missing (NULL) values in the Confirmed, Deaths, and Recovered columns with 0 using the COALESCE function. 
The SET sql_safe_updates = 0 command allows updates without strict conditions.

#### ➤ Insight: 
Ensures that no data gaps interfere with numerical computations or aggregations.

![6](https://github.com/user-attachments/assets/a97002cf-6640-4f5e-a140-85c923cc7d18)

#### ➤ Explanation: 
This query counts the total number of records (rows) in the table.

#### ➤ Insight: 
Provides a quick overview of the dataset size and scope.

![7](https://github.com/user-attachments/assets/23a55366-5a4e-48b2-a3ac-6c1ab9be2699)

#### ➤ Explanation: 
Finds the earliest and latest dates in the dataset using the MIN and MAX functions.

#### ➤ Insight: 
The data spans a specific time period, helping to understand the timeline of the pandemic's impact.

![8](https://github.com/user-attachments/assets/1938043a-9228-465f-82c4-506743dcc010)

#### ➤ Explanation: 
Extracts the month from the Date column and counts unique months to determine the dataset's temporal coverage.

#### ➤ Insight: 
Understanding the span of months allows analysis of seasonal or monthly trends.

![9](https://github.com/user-attachments/assets/69534dec-32b7-49a8-bb16-cba951a5a77a)

- The query aims to calculate the monthly average of confirmed COVID-19 cases, deaths, and recoveries from a dataset called corona_virus.

#### 💠SQL Query Breakdown:

#### 1] Extract Month and Year:

 #### ✅ Syntax :
EXTRACT(MONTH FROM STR_TO_DATE(Date, '%Y-%m-%d')) AS Month,
EXTRACT(YEAR FROM STR_TO_DATE(Date, '%Y-%m-%d')) AS Year,


STR_TO_DATE(Date, '%Y-%m-%d') : converts the Date field from a string format to a date format.

EXTRACT(MONTH FROM ...) : extracts the month from the date.

EXTRACT(YEAR FROM ...) : extracts the year from the date.

The extracted month and year are aliased as Month and Year respectively.

#### 2] Calculate Averages:

#### ✅ Syntax :

AVG(Confirmed) AS Avg_Confirmed,
AVG(Deaths) AS Avg_Deaths,
AVG(Recovered) AS Avg_Recovered,

AVG(Confirmed) : calculates the average number of confirmed cases and aliases it as Avg_Confirmed.

AVG(Deaths) : calculates the average number of deaths and aliases it as Avg_Deaths.

AVG(Recovered) : calculates the average number of recoveries and aliases it as Avg_Recovered.

#### 3] Specify the Data Source:

#### ✅ Syntax :

FROM corona_virus

The data is being retrieved from the corona_virus table.

#### 4] Group by Month and Year:

#### ✅ Syntax :
GROUP BY Month, Year;

The results are grouped by both the extracted month and year. This ensures that the averages are calculated for each month within each year.

#### 5] Result Table Explanation:
The result table shows the monthly averages for confirmed cases, deaths, and recoveries. Each row corresponds to a specific month and year combination.

Example Results Interpretation:

#### ➤ Row 1:

Month: January 2020
Avg_Confirmed: 4.1455
Avg_Deaths: 0.1234
Avg_Recovered: 0.0929

This means that in January 2020, the average number of confirmed cases was approximately 4.15, the average number of deaths was approximately 0.12, and the average number of recoveries was approximately 0.09.

#### ➤ Row 2:

Month: February 2020
Avg_Confirmed: 15.2960
Avg_Deaths: 0.5936
Avg_Recovered: 7.0320

- This indicates that in February 2020, the average number of confirmed cases was approximately 15.30, the average number of deaths was approximately 0.59, and the average number of recoveries was approximately 7.03.


![10](https://github.com/user-attachments/assets/1d657952-5e9f-47bc-a33a-dcea7ec005a3)

- The query aims to find the maximum number of confirmed COVID-19 cases, deaths, and recoveries per year.

#### 💠 SQL Query Breakdown:

#### 1] Extract Year:

EXTRACT(YEAR FROM str_to_date(Date, '%Y-%m-%d')) AS Year,
str_to_date(Date, '%Y-%m-%d') converts the Date field from a string format to a date format.
EXTRACT(YEAR FROM ...) extracts the year

#### 2] Calculate Maximum Values:

MAX(Confirmed) AS Max_Confirmed,
MAX(Deaths) AS Max_Deaths,
MAX(Recovered) AS Max_Recovered,
MAX(Confirmed): calculates the maximum number of confirmed cases and aliases it as Max_Confirmed.
MAX(Deaths) : calculates the maximum number of deaths and aliases it as Max_Deaths.
MAX(Recovered): calculates the maximum number of recoveries and aliases it as Max_Recovered.

#### 3] Specify the Data Source:

FROM corona_virus
The data is being retrieved from the corona_virus table.

#### 4] Group by Year:

GROUP BY Year
The results are grouped by the extracted year. This ensures that the maximum values are calculated for each year.

#### 5] Order by Year:

ORDER BY Year;
The results are ordered by the year to provide a chronological view of the data.

#### 6] Result Table Explanation:

The result table shows the maximum values for confirmed cases, deaths, and recoveries for each year.

Example Results Interpretation:
- Year 2020:

Max_Confirmed: 823225
Max_Deaths: 3752
Max_Recovered: 1123456
This indicates that in 2020, the highest number of confirmed cases in a single entry was 823,225, the highest number of deaths was 3,752, and the highest number of recoveries was 1,123,456.

- Year 2021:

Max_Confirmed: 414188
Max_Deaths: 7374
Max_Recovered: 422436
This indicates that in 2021, the highest number of confirmed cases in a single entry was 414,188, the highest number of deaths was 7,374, and the highest number of recoveries was 422,436.


![11](https://github.com/user-attachments/assets/4e3f957c-23d9-448b-ad7e-b2c5fe18f933)

#### ➤ Explanation: 
Calculates the smallest and largest values for each metric annually using MIN and MAX functions.

#### ➤ Insight: 
Identifies outlier years or extreme points during the pandemic.

![12](https://github.com/user-attachments/assets/c8b90b67-5646-480f-b50a-27c0477f8a40)

#### ➤ Explanation: 
Calculates the smallest and largest values for each metric annually using MIN and MAX functions.

#### ➤ Insight:
Identifies outlier years or extreme points during the pandemic.

![13](https://github.com/user-attachments/assets/8e9c5c97-7ab4-4663-aa6c-01da2991292c)

 #### ➤ Explanation: 
 Aggregates total confirmed cases, deaths, and recoveries for each month using the SUM function.
 
#### ➤ Insight: 
Identifies monthly cumulative trends and critical periods.

![14](https://github.com/user-attachments/assets/be622844-9c39-4faa-b902-e0f9fc9e3618)

 #### ➤ Explanation: 
Calculates the total, average, variance, and standard deviation of confirmed cases, deaths, or recoveries.

 #### ➤ Insight: 
Measures the spread and variability of the data, essential for understanding consistency and volatility.

![15](https://github.com/user-attachments/assets/97584577-b408-4442-95a5-f7d61dc5b635)

 #### ➤ Explanation: 
Calculates the total, average, variance, and standard deviation of confirmed cases, deaths, or recoveries.

 #### ➤ Insight: 
Measures the spread and variability of the data, essential for understanding consistency and volatility.

![16](https://github.com/user-attachments/assets/5f864bd1-ff00-4d70-af8a-233ee9466838)

 #### ➤ Explanation: 
Calculates the total, average, variance, and standard deviation of confirmed cases, deaths, or recoveries.

 #### ➤ Insight: 
Measures the spread and variability of the data, essential for understanding consistency and volatility.

![17](https://github.com/user-attachments/assets/cdc316e7-786f-4058-909d-1abff3857157)

 #### ➤ Explanation:
Identifies the country with the highest total confirmed cases using SUM and LIMIT.

 #### ➤Insight: 
 Reveals which country was most affected.

![18](https://github.com/user-attachments/assets/1dfd4d8b-0cab-451d-b0a9-908965eb6c3f)

Explanation: Finds the country with the lowest total deaths using a Common Table Expression (CTE) and RANK.
Insight: Highlights regions with minimal fatalities.


![19](https://github.com/user-attachments/assets/b8c411c9-786b-49c7-a669-757bfd03492b)

Explanation: Lists the top 5 countries with the highest recoveries using SUM and LIMIT.
Insight: Recognizes regions with strong recovery efforts.

![20](https://github.com/user-attachments/assets/7a9e75e4-b18b-4b1e-878e-c3f5b0cf6a7b)
![21](https://github.com/user-attachments/assets/e4b52d00-6824-46e8-8315-162b023c6637)
![22](https://github.com/user-attachments/assets/738edb03-6ad8-45ec-a9b5-540213deca0f)
![23](https://github.com/user-attachments/assets/ab75b6ff-5a6c-441a-a76e-6ec35baa9155)



### ➡️ Overall  Insights :

#### ➤ Higher Confirmed Cases:
The United States has the highest number of confirmed cases. This reflects the significant impact of COVID-19 on the US, particularly during the peak periods of the pandemic.

#### ➤ Lowest Death Cases:
Countries like Dominica, Kiribati, Marshall Islands, and Samoa have the lowest number of death cases. These countries may have managed to control the spread of the virus effectively or have smaller populations, leading to fewer deaths.

#### ➤ Highest Recovered Cases :
The top five countries with the highest number of recovered cases are India, Brazil, the US, Turkey, and Russia. These countries likely experienced high numbers of cases overall, leading to high recovery numbers as well.

### ➡️ 𝐒𝐮𝐦𝐦𝐚𝐫𝐲 :

#### ➤ Pandemic Coverage :
The date range indicates that the dataset covers critical phases of the pandemic, making it valuable for trend analysis and understanding the progression and impact over time.

#### ➤ Geographical Impact:
The US having the highest confirmed cases is consistent with global reports of the pandemic's severe impact on the country. Conversely, the countries with the lowest death cases are small island nations, which might have implemented strict measures early on to prevent the spread of the virus.

#### ➤ Recovery Rates :
High recovery numbers in populous countries like India, Brazil, and the US are expected given their large populations and significant numbers of confirmed cases. The high recovery rate can provide insights into healthcare response effectiveness and the overall trajectory of the pandemic in these regions.

✨ These insights can help in understanding the global impact of COVID-19, the effectiveness of different countries' responses, and the overall trends in confirmed, death, and recovery cases during the specified period.



 ## ✨ TASK 2 -  NREGA ( National Rural Employment Guarantee Act) Analysis || Power-BI, MySQL

### 💠 Project Overview

- The NREGA (National Rural Employment Guarantee Act) aims to enhance the livelihood security of people in rural areas by guaranteeing 100 days of wage employment in a financial year to a rural household whose adult members volunteer to do unskilled manual work.

- This project analyzes NREGA data to gain insights into job card distribution, worker participation, and expenditure patterns across various Indian states.

- By examining the data, the project aims to highlight the effectiveness and reach of the NREGA scheme, especially among marginalized communities like SC/ST and differently-abled workers. Understanding these patterns helps in assessing the scheme's impact on rural employment and economic stability. The insights drawn from this analysis can guide policy improvements and ensure better implementation of the NREGA scheme. 

### 💠 Problem Statement

NREGA is a vital initiative to alleviate rural unemployment and poverty. This project seeks to address several key questions and challenges associated with NREGA:

• How effective is NREGA in providing employment opportunities to rural households?

• Are there regional disparities in the implementation and outcomes of the scheme?

• What is the utilization of the allocated budget, and how does it correlate with employment generation?

• What are the key factors contributing to the completion of NREGA works, and are there any roadblocks to its success?

• Can data-driven insights guide policymakers and administrators in optimizing the scheme's impact?

### 💠 Data Source 

- The dataset used for this analysis is sourced from official government records and contains information related to NREGA implementation across various states and districts in India.
- 
- It comprises 28 columns, encompassing data on job cards, worker details, budget allocation, work completion statistics, expenditure, and more. This dataset offers a comprehensive view of the progress and challenges faced by the NREGA program. 


### 💠 Tools 

- Microsoft Excel - Data Cleaning & Transformation
- MySQL - Data Analysis 
- PowerBI- Creating Dashboards, Data Visualization
- Canva - For creationg Project Report/Presentation
- Github- For Documnetation


### 💠 Data Preparation

In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting


### 💠 Project dashboard includes:-

➵ Page 1: Job Cards & Workers Analysis

➵ Page 2: Budget & Expenditure Analysis 

➵ Page 3: Works & Employement Analysis

➵ Page 4: Overall State-wise Analysis

## 💠 Insights & Findings

## ✨ Page 1: Job Cards & Workers Analysis

![Screenshot 2024-10-28 090115](https://github.com/user-attachments/assets/0bfdc39d-1382-40d9-bb90-4b4a743258ab)

### 1] Total Workers & Active Workers (KPIs)

Total Workers: 269M
Total Active Workers: 175M

✅ Key Insight: Out of the total registered 269 million workers in NREGA, 175 million are currently active participants, indicating a substantial percentage (approximately 65%) of workers are actively engaged in the scheme. This highlights the ongoing relevance of NREGA in providing employment to rural workers.

### 2] Total Job Cards & Active Job Cards (KPIs)

Total Job Cards Issued: 156M
Total Active Job Cards: 97M

✅ Key Insight :
156 million job cards issued, 97 million are active, signifying that about 62% of issued job cards are in active use. This reflects an overall healthy utilization of job cards within the NREGA framework, although it also raises the question of why 59 million job cards are not active, which could indicate seasonal or localized employment needs, or inactive registrations.

### 3] State-wise Participation in NREGA (Choropleth Map)

Question Answered: 
#### Which states have the most active NREGA participation?

✅ Key Insight :-
- The darker shades on the map represent higher levels of active NREGA workers in states like Uttar Pradesh, Bihar, and West Bengal. These states are the focal points of NREGA engagement, possibly due to larger rural populations and higher unemployment rates.
- States with lighter shades, such as those in the northeast, indicate lower participation in NREGA, potentially due to smaller populations or fewer employment needs under this scheme.
This visualization effectively shows the geographic distribution of NREGA workers, helping to identify regional areas where the program is most effective.

### 4] Job Cards vs Active Workers by State (Bar Chart)

Question Answered: 
#### How are job cards and active workers spread across states?

✅ Key Insight:
- States like Uttar Pradesh, Bihar, and Maharashtra exhibit both high job card issuance and high active worker counts, suggesting that these states are utilizing the NREGA program to its full potential.
- In contrast, other states like Himachal Pradesh and Punjab show a relatively lower number of job cards and active workers. This could indicate lower reliance on the NREGA scheme, possibly due to stronger -local economies or alternative employment sources.
- The clear difference between job cards issued and active workers highlights states where workers might not be fully engaged despite the availability of job cards, giving policymakers insights into where activation efforts may be needed.

### 5] SC/ST Worker Distribution (Stacked Bar Chart)

Question Answered: 
####  What is the distribution of SC/ST workers among active workers?

✅ Key Insight:
- This chart reveals that states like West Bengal, Uttar Pradesh, and Rajasthan have a higher proportion of SC/ST workers in the active NREGA workforce. This suggests that the program is successfully reaching marginalized communities in these regions.
- However, the chart also shows a significant proportion of "Other Workers" (non-SC/ST) in states such as Tamil Nadu and Karnataka, indicating less inclusion of marginalized groups in those regions. This disparity highlights potential areas for improvement in promoting SC/ST participation in those states.

### 6] Job Card Issuance and Active Status (Horizontal Bar Chart)

Question Answered: 
####  How many job cards have been issued and are active in each state?

✅ Key Insight:
-nBihar, Uttar Pradesh, and West Bengal top the list for both the number of job cards issued and the number of active job cards, reaffirming these states' heavy reliance on NREGA for rural employment.
- This visualization underscores the effectiveness of job card distribution in these regions and suggests a strong engagement with the NREGA scheme. However, states with lower job card issuance and active participation, such as Haryana and Gujarat, might not be fully utilizing the program’s potential.

### 7] SC/ST Worker Participation (Donut Chart)

Question Answered: 
#### What is the distribution of SC/ST workers among active workers?

✅ Key Insight:
- The donut chart highlights that SC workers constitute 20.02% (35 million) and ST workers make up 16.47% (29 million) of the total active workforce, while "Other Workers" (non-SC/ST) account for 63.51% (111 million).
- This distribution shows a fairly balanced participation of marginalized groups in NREGA, though non-SC/ST workers still form the majority. The visualization makes it clear that there is room to further increase SC/ST representation in the scheme, particularly in states where these workers make up a smaller proportion of the workforce.

### 8] States with Highest Number of Active Workers (Column Chart)

Question Answered: 
#### Which states have the highest number of active workers?

✅ Key Insight:
- West Bengal (18.4M), Rajasthan (18.1M), and Uttar Pradesh (16.6M) have the highest number of active workers in NREGA, showing the states’ dependency on this scheme to provide rural employment.
- These states are followed by Madhya Pradesh and Tamil Nadu, with over 11 million active workers each.
- This chart succinctly conveys the scale of NREGA participation and offers insights into states where the scheme has the largest impact on the workforce.

### ✅ Overall Insights from the Dashboard:

- The NREGA scheme is highly utilized in states with large rural populations, such as Uttar Pradesh, Bihar, and West Bengal.

- Active participation of SC/ST workers is commendable, but there is still scope to improve their inclusion in several states.

- While most states show a balance between job cards issued and active worker participation, some regions may need further efforts to activate job cardholders.

- The geographic and demographic distribution of NREGA participation, as seen in the choropleth and bar charts, provides a comprehensive understanding of the scheme’s regional effectiveness.

- Policymakers can use these insights to address areas with lower participation, further target marginalized groups, and ensure the optimal use of resources under the NREGA scheme.


## ✨ Page 2:  Budget & Expenditure Analysis 

![Screenshot 2024-10-28 090409](https://github.com/user-attachments/assets/acdb0f62-f344-45fa-ae7b-a386d2da5c50)

The "Budget & Expenditure Analysis" dashboard provides a detailed breakdown of how NREGA (Mahatma Gandhi National Rural Employment Guarantee Act) funds are being spent across different states in India, the allocation of these funds, and which states and regions are more active in using the NREGA budget. Here's a simple explanation of each part with key insights:

### 1] Total Expenditure (KPI)

- Total Expenditure: The NREGA program has spent 5.47 million in total.

- This key figure gives us an overview of how much has been used from the allocated budget for NREGA works and wages.

### 2] Approved Labor Budget (KPI)

- Approved Labor Budget: The total labor budget approved under NREGA is 2 billion.
  
- This indicates how much the government has sanctioned for labor wages under NREGA.

### 3] Gram Panchayats (GPs) with No NREGA Expenditure (KPI)

- 14K Gram Panchayats have not spent any of their NREGA budget.

- This suggests that there are still rural areas where the funds allocated for NREGA haven’t been used, which may need further investigation to understand why.

### 4] How is NREGA Expenditure Allocated? (Donut Chart)

- 73.44% of the NREGA funds go to wages, indicating that most of the program’s money is going directly to workers.
  
- 24.49% is spent on materials and skills, while only 2.07% is spent on admin expenditure.

This shows that a significant part of the NREGA budget is being used for labor and infrastructure projects, but a very small amount is used for administrative tasks.

### 5] Works Breakdown (Donut Chart)

- 45.01% of the expenditure is on NRM (Natural Resource Management) works, showing that almost half of the spending goes into environmental and resource-related projects.
- 
- The rest is divided between categories like category works (32.65%) and expenditure on material (22.34%).
- 
- This distribution reflects the program’s focus on resource management and infrastructural development in rural areas.

### 6] Gram Panchayats with No NREGA Expenditure by State (Bar Chart)

- West Bengal, Maharashtra, and Haryana have the highest number of Gram Panchayats that haven’t spent any NREGA funds (3,100 in West Bengal, 2,098 in Maharashtra).
  
- This highlights areas where local governance may not be utilizing NREGA effectively, possibly due to local inefficiencies or lack of demand for labor.

### 7] State-wise Total Expenditure Breakdown (Stacked Bar Chart)

- This chart shows how each state allocates NREGA expenditure across admin, material, and wages.
 
- Andhra Pradesh and Madhya Pradesh have high expenditure on wages (72-84%), while states like Telangana and West Bengal spend more on material and skilled labor.

- This suggests that different states have varied priorities—some focus more on labor, while others focus on materials and infrastructure development.

### 8] Highest NREGA Expenditure by State (Tree Map)

- Tamil Nadu (727.3M) has the highest NREGA expenditure, followed by Uttar Pradesh (667.83M) and Andhra Pradesh (680.81M).
- 
- The size of the boxes represents how much each state spends, with larger states spending more.
- 
- This reflects that states with higher rural populations tend to spend more under the NREGA program, which means they have greater reliance on rural employment schemes.

### 9] Highest NREGA Labor Budget by State (Bar Chart)

Andhra Pradesh (215M) and Uttar Pradesh (210M) have the largest labor budgets approved, followed by Madhya Pradesh and Rajasthan (200M).

This indicates that these states have a high demand for labor under NREGA, with large budgets dedicated to creating employment opportunities.

### ✅ Overall Findings:

- Majority of Budget on Wages: Across the country, NREGA’s main focus is on wages (73.44% of the total expenditure), which is directly benefiting workers.
  
- Variation in Spending by States: States like Tamil Nadu, Uttar Pradesh, and Andhra Pradesh are the biggest spenders, indicating that these regions rely heavily on NREGA for rural employment. States such as -West Bengal and Maharashtra have several Gram Panchayats that haven’t used their NREGA funds, which might need further attention.
  
- Focus on NRM Projects: Almost half of the NREGA works are focused on natural resource management, reflecting the program’s goal of improving environmental infrastructure while generating employment.
This dashboard shows how well different states are utilizing the NREGA funds and where improvements can be made, especially in regions that have not yet fully used their approved budgets.


## ✨ Page 3: Works & Employement Analysis

![Screenshot 2024-10-28 090423](https://github.com/user-attachments/assets/a85a7027-d5f7-4302-ad75-61fa42dd1194)

The "Work & Employment Analysis" dashboard provides insights into employment, wage distribution, and work completion under the NREGA (Mahatma Gandhi National Rural Employment Guarantee Act) scheme across various states in India. Here's a simple breakdown of each section along with key insights:

### 1] Average Days of Employment Provided per Household (Gauge Chart)

- On average, 22.87 days of employment are provided per household. The maximum potential could go up to 45.74 days.
  
- This indicates that while some households are getting decent work under NREGA, there’s still room for improvement to provide more workdays.
  
### 2] Average Wage Rate per Person (Gauge Chart)

- The average wage rate for NREGA workers is ₹276.05 per person. The rate can vary from ₹0 to ₹552.10.

- While ₹276 is the average, wage rates differ widely across states, highlighting regional disparities in payment.

### 3] Number of Households (HHs) that Completed 100 Days of Employment (Gauge Chart)

- 428,000 households have completed 100 days of employment under NREGA, which is a significant milestone for many families relying on this program for their livelihood.

### 4] Total Works Taken Up (KPI)

- 17 million works have been initiated under NREGA.

- This is a substantial number of projects, showing the scale at which the program operates across rural areas in India.
  
### 5] Total Differently-Abled Workers (KPI)

- 396,000 differently-abled workers have been employed under NREGA.

- The program is inclusive, providing opportunities to differently-abled individuals, but there’s still scope to further expand their participation.

### 6] Work Completion Analysis (Donut Chart)

- 77.87% of works are completed, and 22.13% are ongoing.
  
- This shows that the majority of NREGA projects have been completed, but a considerable portion is still in progress.
  
### 7] Workdays Between Active Social Groups (Donut Chart)

- 61.95% (979 million) of workdays are by SC (Scheduled Caste) individuals.
  
- 20.33% by ST (Scheduled Tribe) individuals, and 17.72% by Women Persondays.
- 
- This reflects the participation of marginalized social groups in NREGA work, with SC individuals contributing the most workdays.
  
### 8] States with the Highest Employment of Differently-Abled Workers (Bar Chart)

- Tamil Nadu employs the most differently-abled workers (99K), followed by Andhra Pradesh (76K) and Telangana (40K).
  
- This highlights that southern states are more active in employing differently-abled workers under NREGA.
  
### 9] States Offering the Highest Average Days of Employment per Household (Bar Chart)

- Andhra Pradesh offers the highest average of 45 days per household, followed by Mizoram (38 days) and Tamil Nadu (37 days).
  
- These states are providing more consistent employment opportunities than others.
  
### 10] States with the Highest Number of Works Completed (Tree Map)

- Madhya Pradesh leads with 420K completed works, followed by Karnataka (414K) and Bihar (407K).
  
- This indicates that these states have a high level of project completion under NREGA, successfully carrying out the program's objectives.
  
### 11] Wage Rate per State (Table)

- Manipur has the highest wage rate of ₹1,025.05, while other states like Andaman & Nicobar and Haryana follow with wages around ₹767.85 and ₹353.53 respectively.
  
- Tamil Nadu, Odisha, and Andhra Pradesh have lower wage rates closer to the ₹250 - ₹275 range.
  
- This demonstrates significant variation in wage rates across different regions.
  
### ✅ Overall Findings:

#### ➼ Average Employment Days:
Many states still need to increase the average days of employment per household to meet the program’s potential (45.74 days).

####  ➼ Inclusion of Differently-Abled Workers: 
Tamil Nadu, Andhra Pradesh, and Telangana are leading in employing differently-abled workers, making the program inclusive for marginalized groups.

#### ➼ Wage Rate Differences: 
There is a wide variation in wage rates across states, with Manipur leading, while others like Odisha and Tamil Nadu are on the lower end.

#### ➼ Work Completion Success: 
States like Madhya Pradesh, Karnataka, and Bihar are excelling in completing NREGA works, contributing significantly to rural development.

- This dashboard reflects how effectively different states are utilizing NREGA funds, providing employment, and completing infrastructure projects, but also highlights areas where improvements can be made, especially in offering more workdays and addressing wage disparities.


## ✨ Page 4: Overall State-wise Analysis

![Screenshot 2024-10-28 090444](https://github.com/user-attachments/assets/1a814c38-8958-450e-830b-5eca6d21f2a1)

The "Overall State-wise Analysis" dashboard presents an in-depth comparison of various metrics related to the NREGA program across different Indian states. The following sections explain each column and key findings:

### 1] Total Workers

- This shows the total number of workers enrolled under the NREGA program in each state.

- Uttar Pradesh has the highest number of total workers (23.6M), followed by Rajasthan (23.3M) and Bihar (22.7M).
  
- These states have a large rural population, hence the higher number of workers in the NREGA program.
  
### 2] Total Active Workers
   
- This reflects the number of workers who are actively participating in NREGA.

- Uttar Pradesh again leads with 16.63M active workers, followed by Rajasthan (18.13M) and Tamil Nadu (11.01M).

- While many states have high total workers, not all are active, which could indicate underutilization of the program in certain areas.

### 3] Works Taken 

- Shows the number of projects or works initiated in each state under NREGA.

- Uttar Pradesh leads with 2.266M works, followed by Bihar with 1.172M works and Madhya Pradesh with 1.240M works. These states are actively engaging workers through many projects.
  
### 4] Completed Works

- This column represents the number of works completed in each state.

- Madhya Pradesh has the highest number of completed works (420K), followed by Karnataka (407K) and Bihar (366K).
  
- This indicates that these states have efficient systems in place to complete projects.
  
### 5] Ongoing Works

- Shows the number of projects still in progress.

- Uttar Pradesh leads with 1.923M ongoing works, indicating a high number of unfinished projects.

- Rajasthan (588K) and Madhya Pradesh (819K) also have a significant number of ongoing works.
  
### 7] Differently-Abled Workers

- The number of differently-abled workers engaged under NREGA in each state.

- Tamil Nadu has the highest number of differently-abled workers (99,285), followed by Andhra Pradesh (75,917) and Telangana (39,535).

- This shows that Tamil Nadu is taking steps to include differently-abled individuals in the workforce.
  
### 8] Total HHs Worked (Total Households Worked)

- This indicates the number of households that have worked under NREGA.

- Uttar Pradesh again leads with 5.236M households, followed by Tamil Nadu (6.411M) and Rajasthan (4.799M).
 
- This highlights the program’s reach and its potential impact on rural households.
  
### 9] Approved Labour Budget
    
- This represents the total approved budget for NREGA in each state.

- Tamil Nadu, Madhya Pradesh, Rajasthan, and West Bengal have the highest budgets of ₹200M each.
  
- Uttar Pradesh also has a significant budget of ₹210M.
  
- These high budget allocations show that these states have prioritized NREGA to provide employment.
  
### 11] Total Expenditure

- This is the total amount of money spent by each state under NREGA.

- Tamil Nadu has spent the most (₹727K), followed by Uttar Pradesh (₹668K) and Andhra Pradesh (₹681K).
  
- This shows that these states are investing significant resources into the NREGA program, ensuring that workers are compensated and projects are executed.

### ✅ Overall Insights:

#### ➼ High Participation States: 
Uttar Pradesh, Tamil Nadu, Andhra Pradesh, and Madhya Pradesh are the leading states in terms of worker engagement, project initiation, and completion. They are successfully utilizing the NREGA program to provide employment and improve infrastructure.

#### ➼ Inclusion of Differently-Abled Workers: 
Tamil Nadu and Andhra Pradesh are notable for including differently-abled workers, which highlights their commitment to inclusivity.

#### ➼ Budget and Spending: 
States like Tamil Nadu, Rajasthan, and Uttar Pradesh have large approved budgets and have been spending significantly to support the program. This indicates a well-funded and operationally efficient approach to NREGA implementation.

- This dashboard helps in understanding how each state is performing in terms of employment generation, budget utilization, and project completion, providing a comprehensive view of NREGA's impact across India.

## 💠 Summary of Findings

- This NREGA analysis provides an in-depth look at the program’s impact on employment and project completion across Indian states. Key findings reveal:

#### ➼ High Worker Engagement: 
States like Uttar Pradesh, Tamil Nadu, and Rajasthan have the highest number of workers enrolled and active in NREGA, showing the program’s reach in these states.

#### ➼ Project Initiation and Completion: 
A large number of projects have been initiated, particularly in Uttar Pradesh and Bihar, which helps create employment and support rural infrastructure development.

#### ➼ Budget Utilization: 
Tamil Nadu, Rajasthan, and Uttar Pradesh have high budget allocations and significant expenditure, indicating strong financial commitment to the program.

#### ➼ Inclusion Efforts: 
Tamil Nadu and Andhra Pradesh are leading in employing differently-abled individuals, promoting inclusivity within the NREGA workforce.

## 💠 Impact of NREGA on Employment and Economic Stability

NREGA plays a critical role in providing rural employment and fostering economic stability by:

#### ➼ Employment Generation: 
By engaging millions of workers, NREGA helps reduce rural unemployment. Active states like Uttar Pradesh and Madhya Pradesh show the program’s potential in sustaining rural livelihoods.

#### ➼ Income Stability: 
NREGA’s wage payments provide a steady income source, which helps in meeting daily needs and improves the financial security of rural households. States with high active participation indicate a larger positive economic impact.

#### ➼ Infrastructure Improvement: 
Through various works taken up under NREGA, such as road building, water conservation, and other infrastructure projects, rural areas benefit from improved amenities and facilities.

#### ➼ Inclusivity: 
The program has provisions for including differently-abled individuals, as seen in Tamil Nadu and Andhra Pradesh. This strengthens community ties and promotes equal employment opportunities.
Recommendations for Policy Improvements.

- To further enhance the effectiveness of NREGA, some policy recommendations include:

#### ➼ Increase in Budget Allocation for Underperforming States: 
Some states with low budgets could benefit from increased funding to boost participation and infrastructure development.

#### ➼ Focus on Timely Completion of Projects: 
Many projects are still ongoing, particularly in states like Uttar Pradesh. Additional resources could be allocated to ensure timely project completion to improve efficiency and worker retention.

#### ➼ Higher Wages for Workers: 
Wage rates vary across states, with some offering very low amounts. A minimum wage standard could be established to provide fair compensation for all workers.

#### ➼ Improved Data Tracking: 
Regular monitoring of active versus inactive workers and project progress can help identify and address bottlenecks faster.

#### ➼ Encourage Inclusivity Across States: 
While some states focus on employing differently-abled workers, others can adopt similar practices to ensure broader inclusion.

## 💠 Future Scope of Analysis

- To build on this analysis, future studies can focus on:

#### ➼ Impact of NREGA on Household Income:
Studying how NREGA wages influence the overall economic status of rural households, particularly in poverty reduction.

#### ➼ Long-term Effects on Rural Infrastructure: 
Examining how the infrastructure projects completed under NREGA affect rural development and access to essential services over time.

#### ➼ State-wise Comparisons of Program Efficiency:
A deeper dive into why certain states like Tamil Nadu and Uttar Pradesh perform better could help other states adopt best practices.

#### ➼ Gender-based Employment Impact:
Understanding the gender distribution of workers and its impact on female empowerment in rural areas.

#### ➼ Feedback and Satisfaction Survey: 
Conducting surveys with NREGA workers to gather insights on program effectiveness, worker satisfaction, and areas for improvement.

- This analysis provides a clear view of how NREGA supports rural employment and economic stability, while identifying opportunities for enhancing its impact through improved policy, budget allocation, and inclusion strategies.

## 💠Conclusion :-

➤ The NREGA analysis reveals significant insights into the distribution of job cards, active worker participation, and expenditure patterns across different states, highlighting the scheme's extensive reach and impact on rural employment.

➤ The data indicates that while certain states show higher engagement and expenditure, others lag, pointing to areas needing policy intervention. 

➤ The scheme's inclusivity towards SC/ST and differently-abled workers is notable but requires continuous monitoring to ensure equitable benefits. 

➤ Overall, NREGA plays a crucial role in enhancing rural livelihoods, and these findings can inform better-targeted strategies for its effective implementation.


# Explorartory Data Analysis with MySQL

## Job Cards & Workers
![6](https://github.com/user-attachments/assets/ebe82072-2f91-4f96-b1be-5833c481c4e4)
![7](https://github.com/user-attachments/assets/967b6186-59a9-4207-94f4-b4cff4464542)
![8](https://github.com/user-attachments/assets/19a17124-5b35-4192-930e-22572c97642b)
![9](https://github.com/user-attachments/assets/924c03af-9d36-4f13-84a6-743524cf161c)

## Works & Employement
![10](https://github.com/user-attachments/assets/6e979e00-1872-42f1-a710-ed2954863ab0)
![12](https://github.com/user-attachments/assets/21df7d89-0676-401c-9ffd-7c0f2196565c)
![13](https://github.com/user-attachments/assets/8b902175-a3b6-44fe-a3e9-e90849504132)
![14](https://github.com/user-attachments/assets/e5ef4feb-e9e9-4694-980e-8f54509095e2)
![15](https://github.com/user-attachments/assets/7727d595-c453-4005-88b6-f30cb6a2f4ef)
![16](https://github.com/user-attachments/assets/54f91d21-331c-4980-9c4d-49dcea21b7ac)
![17](https://github.com/user-attachments/assets/ea57f062-72f0-4793-a537-4f5b66726273)
![18](https://github.com/user-attachments/assets/eda0e0d6-ab7d-4dee-85b6-ab7f5967819b)

## Budget & Expenditure
![19](https://github.com/user-attachments/assets/3110a87a-5ef5-4cbd-b9e4-e5ea337bfe67)
![20](https://github.com/user-attachments/assets/1f55a444-5616-4dd0-a32d-411cb7f5a855)
![21](https://github.com/user-attachments/assets/6e8dd55e-349d-408d-81b8-06fec5e19041)
![22](https://github.com/user-attachments/assets/382fd55b-17e8-4746-8fdb-d96cde43986e)
![23](https://github.com/user-attachments/assets/0a136969-5d54-4626-a05f-e359ce389423)
![24](https://github.com/user-attachments/assets/d7536f60-4ed3-4961-bdda-64e061960bbb)
![25](https://github.com/user-attachments/assets/3221a115-ee6d-49d7-b5d7-e5604c5ebc7e)
![26](https://github.com/user-attachments/assets/6644cb0f-20e6-4558-bf54-223372674bad)
![27](https://github.com/user-attachments/assets/44fb7131-0e08-41ad-9aa4-c6a584dae41d)
![28](https://github.com/user-attachments/assets/abf6d6ad-0c6c-4ef4-818a-02b7a77c612c)




