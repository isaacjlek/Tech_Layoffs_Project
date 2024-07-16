# 2022 World Tech Layoffs Project

### Project Overview

This data analysis project provides insight into where, when, and why the mass tech layoffs of 2022 occurred. Through malleable visualizations, we are able to filter through the countries, cities, companies, months, and industries to determine a variety of possible questions.

### Data Sources

The data set used for this analysis is: 
https://www.kaggle.com/datasets/swaptr/layoffs-2022

### Tools

- MySQL - Data cleaning and analysis
- Tableau - Data visualization


### Data Cleaning

In the initial data preparation phase, I performed the following in SQL:
1. Removed Duplicates
2. Standardized the Data
3. Organized Null and Blank Values
4. Removed Unnecessary Columns

### Exploratory Data Analysis

Involved exploring the layoffs data to answer key questions, such as:

- What are the countries and cities with the most layoffs?
- Which industries had the most layoffs?
- What companies contributed the most to that layoff count and how much did they layoff?
- Which month had the most layoffs?

### Data Analysis

Some interesting code I worked with:

Found the sum of each company's total layoffs in descending order by layoffs

```sql
WITH Rolling_Total AS
(
SELECT SUBSTRING(`date`, 1, 7) AS `MONTH`, SUM(total_laid_off) AS total_off
FROM layoffs_staging2
WHERE SUBSTRING(`date`, 1, 7) IS NOT NULL
GROUP BY `MONTH`
ORDER BY 1 ASC
)
SELECT `MONTH`, total_off,
SUM(total_off) OVER(ORDER BY `MONTH`) AS rolling_total
FROM Rolling_Total;
```


### Results/ Findings

SQL - https://shorturl.at/apPWl





### References

- Youtube Alex the Analyst: https://www.youtube.com/watch?v=4UltKCnnnTA&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=19







