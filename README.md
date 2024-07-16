# 2022 World Tech Layoffs Project

### Project Overview

This data analysis project provides insight into where, when, and why the mass tech layoffs of 2022 occurred. Through malleable visualizations, we are able to filter through the countries, cities, companies, months, and industries to determine answers to a variety of possible questions.

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

- What companies contributed the most to that layoff count and how much did they layoff?
- What are the countries and cities with the most layoffs?
- Which industries had the most layoffs?
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

Tableau Dashboards - 

![Screenshot 2024-07-15 231126](https://github.com/user-attachments/assets/106da0fb-5984-49c5-860d-1d08ec0c8b97)
Interactive Dashboard 1: https://public.tableau.com/app/profile/isaac.leksrisawat/viz/layoffs_dashboard1/Dashboard1

![Screenshot 2024-07-15 231340](https://github.com/user-attachments/assets/b66ed4f7-0957-4acd-801c-dec23178aaa9)
Interactive Dashboard 2: https://public.tableau.com/app/profile/isaac.leksrisawat/viz/layoffs_dashboard2/Dashboard2
&nbsp;

&nbsp;

## Summary of Causes for Mass Tech Layoffs in 2022

The mass tech layoffs in 2022 were driven by a combination of factors that reshaped the industry landscape. Key reasons include:

1. **Post-Pandemic Adjustments**: After a surge in demand for digital services during the pandemic, many tech companies expanded rapidly. As the world began to return to normal, this growth slowed, leading to overstaffing.

2. **Economic Uncertainty**: Rising inflation and looming recession fears prompted businesses to tighten budgets, prioritizing cost-cutting measures, which often led to workforce reductions.

3. **Interest Rate Hikes**: The Federal Reserve's increases in interest rates to combat inflation affected investor sentiment, leading to reduced funding for startups and growth-focused companies.

4. **Focus on Profitability**: Many firms shifted their priorities from growth at all costs to sustainable profitability, resulting in layoffs as part of broader restructuring efforts.

5. **Technological Overhaul**: Companies began reassessing their product lines and tech stacks, leading to layoffs in departments deemed non-essential or redundant.

6. **Market Correction**: The tech sector faced a market correction after years of inflated valuations, prompting companies to reassess their workforce in line with more realistic growth projections.

These factors collectively contributed to a challenging environment for tech companies in 2022, resulting in significant layoffs across the industry.
&nbsp;

## Top 5 Companies with the most layoffs in 2022 and a summary for why these mass layoffs occurred.

1. **Meta**: <br />
Layoffs: 11,000 <br />
Reasoning: Meta faced declining advertising revenues and increased competition. The company shifted focus toward long-term investments in the metaverse, leading to restructuring and significant workforce reductions to streamline operations.

2. **Amazon**: <br />
Layoffs: 10,150 <br />
Reasoning: Amazon experienced rapid growth during the pandemic, resulting in over-hiring. As demand stabilized post-pandemic and economic uncertainties rose, the company aimed to reduce costs and improve efficiency, leading to layoffs across various divisions.

3. **Cisco**: <br />
Layoffs: 4,100 <br />
Reasoning: Cisco undertook layoffs as part of a strategic realignment to focus on key growth areas, such as security and cloud solutions. The company sought to simplify operations and adapt to changing market dynamics.

4. **Peloton**: <br />
Layoffs: 4,084 <br />
Reasoning: Peloton saw a dramatic decline in demand following the pandemic boom, coupled with supply chain issues. To regain profitability and restructure the business model, the company initiated layoffs to reduce operational costs.

5. **Philips**: <br />
Layoffs: 4,000 <br />
Reasoning: Philips was affected by a major product recall and slowing demand for consumer health products. The company aimed to streamline operations and refocus resources, resulting in significant workforce reductions to stabilize the business.
&nbsp;

&nbsp;

### References

- Youtube Alex the Analyst Data cleaning: https://www.youtube.com/watch?v=4UltKCnnnTA&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=19







