# Handwashing and Mortality Rate Analysis

This project analyzes the relationship between the introduction of handwashing and the reduction in mortality rates in clinics during the 19th century. The analysis is based on yearly and monthly data of births and deaths before and after the practice of handwashing was introduced in a clinic setting. The project also includes a statistical analysis using bootstrapping to calculate the confidence interval for the impact of handwashing.

## Project Overview

The goal of this project is to:
1. Analyze the proportion of deaths before and after handwashing was introduced.
2. Identify the year with the highest deaths at the clinics.
3. Visualize the trend of death proportions for different clinics.
4. Calculate a 95% confidence interval using bootstrapping to estimate the reduction in mortality due to handwashing.

## Data

The dataset contains two CSV files:
- **Yearly Deaths by Clinic:** `yearly_deaths_by_clinic.csv`
- **Monthly Deaths:** `monthly_deaths.csv`

### Key Columns:
- **`year`**: The year of the record.
- **`clinic`**: The clinic where the data was recorded.
- **`births`**: The number of births recorded in that year or month.
- **`deaths`**: The number of deaths recorded in that year or month.
- **`date`**: The date of the record (used in the monthly dataset).

### New Columns Created:
- **`proportion_deaths`**: Proportion of deaths = `deaths` / `births`
- **`handwashing_started`**: A boolean column that indicates whether handwashing was practiced or not.

## Analysis Process

1. **Loading Data:**
   - The dataset is loaded using `pandas` and briefly inspected.
   
2. **Proportion of Deaths:**
   - A new column `proportion_deaths` is created to calculate the proportion of deaths in relation to the number of births at the clinics.
   
3. **Visualization:**
   - A line plot is created to visualize the yearly proportion of deaths at different clinics. This helps to observe trends over time.

4. **Highest Year of Deaths:**
   - Using `groupby` and `sum`, we identify the year with the highest number of deaths.

5. **Effect of Handwashing:**
   - Handwashing was introduced in June 1847. We divide the monthly data into two groups: before and after handwashing.
   - The mean proportions of deaths before and after handwashing are calculated and compared.

6. **Bootstrapping Analysis:**
   - A bootstrapping technique is used to estimate the distribution of the mean difference in the proportion of deaths before and after handwashing. 
   - A 95% confidence interval is computed from 5000 bootstrapped samples.
