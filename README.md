# Covid-19

## Case Summary
**"Unraveling Indonesia's Covid-19 Puzzle: A CRISP-DM Journey from Data to Insights"**

- Objective Statement:
  - Get business insight about the date that has the highest number of new Covid-19 cases reported in one day.
  - Get to know which a province that has the highest number of new cases per day.
  - Get to know which an island that has the highest number of new cases per day.
  - Get to know which a province that has the highest daily cure rate per day.
  - Get business insight about the correlation between new deaths and new recovery

- Challenges:
  - Large size of data, so it can not maintain by Microsoft Excel or Google Spreadsheet
  - There's a lot of dummy data, missing values, and others unneeded data
    
- Methodology / Analytic Technique:
  - Descriptive analysis
  - Graph analysis
    
- Business Benefit:
  - Enhanced decision-making for businesses and public health organizations; ensuring resources are allocated efficiently and interventions are targeted effectively to manage COVID-19's impact
  - Helping public who access this data to predictive and make a strategic planning
  - Developing risk mitigation strategies, ensuring the safety of employees, and maintaining operational resilience.

- Expected Outcome:
  - region segmentation analysis
  - know the highest number of new Covid-19 cases reported by the date, province, and island
  - know the correlation between new deaths and new recovery

## Business Understanding
In facing the COVID-19 pandemic, a deep understanding of data is a very valuable asset for various parties, including the government, health institutions and the general public. Data analysis on the Indonesian COVID-19 dataset aims to provide better insight into this pandemic, as well as assist in making effective decisions in dealing with the public health crisis. The COVID-19 dataset in Indonesia is arranged based on time series, national level and provincial level. , also accompanied by demographic data from that location/region. This dataset is a compilation of various open data sources, such as the official government website of the COVID-19 Task Force, the Central Statistics Agency, and the InaCOVID-19 Hub.

By utilizing this dataset, several important things that can be explored are:
1. On what date was the highest number of new COVID 19 cases reported in one day?
2. Which province had the highest number of new cases per day?
3. Which island had the highest number of COVID 19 cases per day?
4. Which province had the highest number of new cases per day? highest daily healing?
5. How Correlation Between New Deaths and New Recovery?

## Data Understanding
- COVID-19 data in Indonesia from March 1 2020 - September 16 2022
- The dataset consists of 31,822 rows and 38 columns
- Data dictionary:
  1. 'Date' : Date reported
  2. 'Location ISO Code' : Location code based on ISO standard
  3. 'Location' : Location name
  4. 'New Cases' : Daily positive cases
  5. 'New Deaths' : Daily death cases
  6. 'New Daily Recovered' : Daily cure cases
  7. 'New Active Cases': Daily active cases
  8. 'Total Cases': The accumulative number of positive cases up to the associated time
  9. 'Total Deaths': The cumulative number of deaths up to the associated time
  10. ‘Total Recovered': The cumulative number of cured cases up to the associated time
  11. 'Total Active Cases': The cumulative number of active cases up to the associated time
  12. 'Location Level': Regional or national location level
  13. ‘City or Regency': Name of city or region
  14. 'Province' : Name of the province of location
  15. 'Country' : Country name of location
  16. 'Island' : Name of the main island location
  17. 'Time Zone' : Time zone location
  18. 'Special Status' : Special status of location
  19. 'Total Regencies' : The number of districts within the associated location
  20. 'Total Cities' : Number of cities within the associated location
  21. 'Total Districts' : Number of subdistricts within the corresponding location
  22. 'Total Urban Village' : The number of villages within the associated location
  23. 'Total Rural Villages' : Number of villages within the associated location
  24. 'Area (km2)' : Area of location in square kilometers
  25. 'Population' : The number of populations within a related location
  26. 'Population Density' : The population density in a related location (formula = Population / Area)
  27. 'Longitude' : Longitude of location
  28. 'Latitude' : The latitude of the location
  29. 'New Cases per Million' : Formula = (New Cases / Population) x 1,000,000
  30. 'Total Cases per Million' : Formula = (Total Cases / Population) x 1,000,000
  31. 'Total Deaths per Million' : Formula = (Total Deaths / Population) x 1,000,000
  32. 'Case Fatality Rate' : Formula = (Total Deaths / Total Cases) x 100
  33. 'Case Recovered Rate' : Formula = (Total Recovered / Total Cases) x 100
  34. 'Growth Factor of New Cases': Less than 1 means decreased, 1 means none change, more than 1 means increase (formula = Today New Cases / Yesterday New Cases)
  35. 'Growth Factor of New Deaths': Less than 1 means decreased, 1 means none change, more than 1 means increase (formula = Today New Deaths / Yesterday New Deaths)

## Data Preparation
- Python Version: 3.11.6
- Packages: Pandas, NumPy, Matplotlib, Seaborn, and Feature Engine

## Data Cleansing
The processes carried out include:
1. Drop unneeded columns. The fields that will be dropped are 'Location ISO Code', 'City or Regency', 'Country', 'Continent', 'Time Zone', 'Special Status', 'Total Cities', 'Total Districts', 'Total Regencies', 'Total Urban Villages', 'Total Rural Villages', 'Area (km2)', 'New Cases per Million', 'Total Cases per Million', 'New Deaths per Million', 'Total Deaths per Million', 'Growth Factor of New Cases', and 'Growth Factor of New Deaths'.
2. Change the 'Date' data type to a datetime data type to avoid errors in time-series sequencing in visualizations.
3. After cleansing, the dataset now has 20 columns

## Exploratory Data Analysis
1. On what date was the highest number of new COVID-19 cases reported in one day?
   
   <img src="https://github.com/khanshafiira/Project_CRISP-DM/assets/166186201/bea238ec-d5e7-4707-a9cc-0a8d46aa7b25" width="500" height="290">

Based on the visualization above, it can be observed that the growth in cases began around mid-February 2022, specifically on February 15th. There was a significant spike on **February 16th, 2022**, where **the highest number of new COVID-19 cases in a single day was recorded**, totaling **64,718 cases**. Subsequently, there was a decline from February 17th to February 22nd, followed by an increase again on February 23rd. Then, on February 24th, the number of cases decreased once more.

From the table and visualization data above, it is evident that the top 8 dates with the highest number of COVID-19 cases per day are in February 2022.

2. Which province has the highest number of new cases per day?
   
   <img src="https://github.com/khanshafiira/Project_CRISP-DM/assets/166186201/08b3b411-de60-4cd8-b7d8-4c886055c120" width="500" height="290">

Based on the visualization above, it can be seen that **DKI Jakarta Province has the highest total cases per day of 1,412,474 cases**, followed by the Provinces of West Java, Central Java, East Java, and Banten.
   
3. Which island has the highest number of COVID 19 cases per day?
   
   <img src="https://github.com/khanshafiira/Project_CRISP-DM/assets/166186201/0a22003b-5307-467b-98a9-3eb0f987530f" width="400" height="350">
   
   Based on the visualization above, **the highest number of COVID-19 cases found per day is centered on the island of Java** with **the number of cases penetrating up to 4 million cases per day**. The comparison looks very striking when compared to the total discovery of COVID 19 cases per day on other islands. This shows that the results of the visualization above are in accordance with the previous analysis where the 5 provinces with the most total COVID-19 cases found per day are on the island of Java.

5. Which province has the highest daily cure rate?
    
9. How About The Correlation between New Deaths and New Recovery?
   
Fourth
   ![image](https://github.com/khanshafiira/Project_CRISP-DM/assets/166186201/ebc6231c-96dd-44a1-a4d5-9b2d7d9b43f5)

Fifth

![image](https://github.com/khanshafiira/Project_CRISP-DM/assets/166186201/730688a5-9d71-453a-a9be-16c5d8504bb7)
