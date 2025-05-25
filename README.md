# Homicide Report (1980 - 2014)

## Introduction

Welcome to the Homicide Report! This Power BI report analyzes a dataset encompassing murders from the FBI's Supplementary Homicide Reports (SHR) spanning from 1980 to 2014 in the United States. The dataset includes detailed information on the age, race, sex, and ethnicity of victims and perpetrators, as well as the relationship between them and the weapons used. 

## Acknowledgements

The data was compiled and made available by the Murder Accountability Project, founded by Thomas K. Hargrove. Established in 2015, the nonprofit organization aims to improve the accounting of unsolved homicides, assist law enforcement in clearing cold cases, and educate the public about the growing problem of unsolved murders.

## Data Source

The dataset used in this report is sourced from Kaggle:

[Homicide Reports (1980-2014) Dataset](https://www.kaggle.com/datasets/murderaccountability/homicide-reports)

## Data Preparation

Data preparation involved the creation of a new measurement table, "All Measures," using DAX functions and formulas. The measures included are:

- **Total Records**: `COUNTROWS('database')`
- **Total Incidents**: `SUM('database'[Incident])`
- **Victim Male**: `CALCULATE([Total Records], 'database'[Victim Sex] = "Male")`
- **Victim Female**: `CALCULATE([Total Records], 'database'[Victim Sex] = "Female")`
- **Victim Unknown**: `CALCULATE([Total Records], 'database'[Victim Sex] = "Unknown")`
- **% Victim Male**: `DIVIDE([Victim Male], [Total Records], 0)`
- **% Victim Female**: `DIVIDE([Victim Female], [Total Records], 0)`
- **% Victim Unknown**: `DIVIDE([Victim Unknown], [Total Records], 0)`
- **Perpetrator Male**: `CALCULATE([Total Records], 'database'[Perpetrator Sex] = "Male")`
- **Perpetrator Female**: `CALCULATE([Total Records], 'database'[Perpetrator Sex] = "Female")`
- **Perpetrator Unknown**: `CALCULATE([Total Records], 'database'[Perpetrator Sex] = "Unknown")`
- **% Perpetrator Male**: `DIVIDE([Perpetrator Male], [Total Records], 0)`
- **% Perpetrator Female**: `DIVIDE([Perpetrator Female], [Total Records], 0)`
- **% Perpetrator Unknown**: `DIVIDE([Perpetrator Unknown], [Total Records], 0)`

![Image](https://github.com/user-attachments/assets/35661b76-e87e-44d4-88ae-d613b1d8ac43)

To gain more insights from the data, conditional columns were created in the Power Query Editor to categorize ages:

- **Victim Age Category**: Derived from the "Victim Age" column
- **Perpetrator Age Category**: Derived from the "Perpetrator Age" column

Entries with a victim age of 998 and perpetrator age of 0 were categorized as "Unknown" since these values are nonsensical.

## Visualizations

This report consists of three pages, navigable via buttons located in the left corner:

### Page 1: Overview

1. **Cards**: Display total records and total incidents
2. **Donut Charts**: Show homicide crime type distribution and crime resolution status
3. **Line Chart**: Depicts the trend of incidents over time
4. **Stacked Bar Charts**: Illustrate perpetrator-victim relationships and weapon usage in homicides
5. **Map**: Displays the geographic distribution of incidents across U.S. states

### Page 2: Victim Analysis

1. **Cards**: Show counts and percentages of male, female, and unknown victims
2. **Treemap**: Displays victim race distribution
3. **Stacked Bar Chart**: Depicts the distribution of homicide victims by age category
4. **Donut Chart**: Shows victim ethnicity distribution in homicides

### Page 3: Perpetrator Analysis

1. **Cards**: Show counts and percentages of male, female, and unknown perpetrators
2. **Treemap**: Displays perpetrator race distribution
3. **Stacked Bar Chart**: Depicts the distribution of homicide perpetrators by age category
4. **Donut Chart**: Shows perpetrator ethnicity distribution in homicides

## Snapshots of the Dashboard

![Image](https://github.com/user-attachments/assets/73d1d74b-211f-4c2c-9747-a76d6a51e1b7)
![Image](https://github.com/user-attachments/assets/1ba4e99b-5da1-43b5-b25f-b6d26c7b21df)
![Image](https://github.com/user-attachments/assets/c4af7e5b-e26e-48d6-bdb4-8ecf0d998bcd)

## Key Insights

### General Statistics (1980-2014)

- **Total Records**: 638,454
- **Total Incidents**: 14,663,963

### Homicide Crime Type Distribution

- **Manslaughter by Negligence**: 9,116 (1.43%)
- **Murder or Manslaughter**: 629,338 (98.57%)

### Crime Resolution Status

- **Solved (Yes)**: 448,172 (70.2%)
- **Unsolved (No)**: 190,282 (29.8%)

### Incident Trends Over Time

- **Lowest incidents recorded**: 96,225 (1999)
- **Highest incidents recorded**: 795,644 (2010)

### Perpetrator-Victim Relationship in Homicides

- **Unknown Relationship**: 273,013 (highest)
- **Acquaintance**: 126,018 (second highest)
- **Stranger**: 96,593 (third highest)
- **Wife**: 23,187 (fourth highest)
- **Friend**: 21,945 (fifth highest)

### Weapon Usage in Homicide Incidents

- **Handgun**: 317,484 (most used)
- **Knife**: 94,962 (second most used)
- **Blunt Object**: 67,337 (third most used)
- **Firearm (Unspecified)**: 46,980 (fourth most used)
- **Unknown Weapon**: 33,192 (fifth most used)

**Note**: The "Firearm" category may include unspecified weapons when the exact type (e.g., handgun, shotgun, rifle) could not be determined.

### Geographic Distribution (U.S.)

- **Highest number of incidents recorded in Florida**: 8,100,400

### Victim Demographics

- **Male Victims**: 494K (77.4%)
- **Female Victims**: 143K (22.5%)
- **Unknown Victims**: 984 (0.2%)

### Victim Age Distribution

- **Young Adults**: 291,552
- **Adults**: 200,840
- **Teens**: 74,984
- **Seniors**: 40,495
- **Children**: 26,609
- **Unknown**: 974

### Victim Ethnicity Distribution

- **Not Hispanic**: 197,499 (30.93%)
- **Hispanic**: 72,652 (11.38%)
- **Unknown**: 368,303 (57.69%)

### Victim Race Distribution

- **White**: 317,422 (most common)
- **Black**: 299,899 (second most common)

### Perpetrator Demographics

- **Male Perpetrators**: 400K (62.6%)
- **Female Perpetrators**: 49K (7.6%)
- **Unknown Perpetrators**: 190K (29.8%)

### Perpetrator Age Distribution

- **Young Adults**: 219,935
- **Unknown**: 216,327
- **Adults**: 119,472
- **Teens**: 71,820
- **Seniors**: 9,688
- **Children**: 1,231

### Perpetrator Ethnicity Distribution

- **Not Hispanic**: 145,172 (22.74%)
- **Hispanic**: 46,872 (7.34%)
- **Unknown**: 446,410 (69.92%)

### Perpetrator Race Distribution

- **White**: 218,243 (most common)
- **Black**: 214,516 (second most common)
- **Unknown**: 196,047 (third most common)
