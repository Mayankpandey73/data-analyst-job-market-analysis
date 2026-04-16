## 📊 Data Analyst Job Market Analysis

## 📌 Overview
Welcome to my analysis of the **data job market**, focusing on **Data Analyst roles**, to identify the most **in-demand skills**, **salary trends**, and **optimal career strategies**.

The goal is to help job seekers make **data-driven decisions** by understanding which skills are most valuable in the market.

The dataset is sourced from:
[Data Jobs Dataset](https://huggingface.co/datasets/lukebarousse/data_jobs)

--- 

## 🛠️ Tools Used

Python | Pandas | Matplotlib | Seaborn | Jupyter Notebook | VS Code | Git & GitHub

---

## ⚙️ Data Preparation & Cleaning

This section outlines the steps taken to prepare the data for analysis, ensuring accuracy and usability.

## Import & Clean Up Data

I start by importing necessary libraries and loading the dataset, followed by initial data cleaning tasks to ensure data quality.

```python
# Importing Libraries
import ast
import pandas as pd
import seaborn as sns
from datasets import load_dataset
import matplotlib.pyplot as plt  

# Loading Data
dataset = load_dataset('lukebarousse/data_jobs')
df = dataset['train'].to_pandas()

# Data Cleanup
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda x: ast.literal_eval(x) if pd.notna(x) else x)
```

## Filter US Jobs

To focus my analysis on the U.S. job market, I apply filters to the dataset, narrowing down to roles based in the United States.

```python
df_US = df[df['job_country'] == 'United States']

```  

---

## 📊 Analysis & Results

---

##  EDA 

This section explores the data job market from a global perspective and then narrows down to Data Analyst roles in the United States using bar charts, pie charts, and histograms.

The goal is to understand:
- Job distribution across roles and countries  
- Job benefits offered in the market  
- Salary patterns and hiring trends in the US  

View my notebook with detailed steps here: [1_data_jobs_eda](/1_data_jobs_eda.ipynb).

## The Analysis

Each Jupyter notebook in this project explores a specific aspect of the data job market.

## 1. Most Demanded Skills for Top 3 Data Roles

I identified the top 3 most common data roles and extracted their top 5 required skills.

View my notebook with detailed steps here: [2_Skill_Demand](/2_Skills_Demand.ipynb).

### Results

![Visualization of Top 5 Skills for the top 3 data roles](/images/skill_demand_all_data_roles.png)

*Bar graph visualizing the salary for the top 3 data roles and their top 5 skills associated with each.*

### Insights
- SQL is the most in-demand skill for Data Analysts and Data Scientists.
- Data Engineers rely more on specialized tools (AWS, Azure, Spark).
- Python is highly demanded across all roles, especially for Data Scientists and Engineers.

## 2. Skill Trends for Data Analysts 

I analyzed monthly job postings to track how top skills evolved throughout the year.

View my notebook with detailed steps here: [3_Skills_Trend](https://github.com/Mayankpandey73/data-analyst-job-market-analysis/blob/main/3_Skills_Trend.ipynb).

### Results

![Trending Top Skills for Data Analysts in the US](/images/skill_trend_DA.png)  
*Bar graph visualizing the trending top skills for data analysts in the US in 2023.*

### Insights
- SQL remains consistently dominant despite a slight decline.
- Excel surged in demand toward the end of the year.
- Python and Tableau stayed stable; Power BI showed gradual growth.

## 3. Salary Analysis for Data Roles

I examined salary distributions across major data roles in the U.S. and analyzed skill-level pay.

View my notebook with detailed steps here: [4_Salary_Analysis](/4_Salary_Analysis.ipynb).

#### Results

![Salary Distributions of Data Jobs in the US](/images/Salary_Distributions.png)  
*Box plot visualizing the salary distributions for the top 6 data job titles.*

### Insights
- Senior Data Scientists and Engineers earn the highest salaries, with large variability.
- Data Analyst salaries are more consistent with fewer extreme outliers.
- Higher specialization generally leads to higher pay.

## Highest Paid & Most Demanded Skills for Data Analysts

Next, I narrowed my analysis and focused only on data analyst roles. I looked at the highest-paid skills and the most in-demand skills. I used two bar charts to showcase these.

#### Results
Here's the breakdown of the highest-paid & most in-demand skills for data analysts in the US:

![The Highest Paid & Most In-Demand Skills for Data Analysts in the US](/images/Highest_Paid_and_Most_In_Demand_Skills_for_Data_Analysts.png)

*Two separate bar graphs visualizing the highest paid skills and most in-demand skills for data analysts in the US.*

### Insights
- High-paying: niche tools like `dplyr`, `Bitbucket`, and `Gitlab`
- Most in-demand are `Excel`, `PowerPoint`, and `SQL`
- There is a clear gap between demand and salary—both matter for career growth.

## 4. Most Optimal Skills for Data Analysts

I combined demand and salary data to identify the most valuable skills.

View my notebook with detailed steps here: [5_Optimal_Skills](https://github.com/Mayankpandey73/data-analyst-job-market-analysis/blob/main/5_Optimal_Skills.ipynb).

#### Results

![Most Optimal Skills for Data Analysts in the US](/images/most_optimal_skills.png)    
*A scatter plot visualizing the most optimal skills (high paying & high demand) for data analysts in the US.*

### Insights
- `Oracle` offers high salaries but appears less frequently.
- `Python` and `Tableau` balance strong demand with high pay.
- `SQL` and `Excel` remain essential but have lower median salaries

---

## Overall Key Insights

- **Skill Demand and Salary Correlation**: Higher demand skills like Python and Oracle tend to offer higher salaries.  
- **Market Trends**: The data job market is dynamic, and skill demand shifts over time.  
- **Economic Value of Skills**: Focusing on in-demand, high-paying skills helps maximize career growth and earnings.

---

## What I Learned

- **Python & Data Tools**: Strengthened skills in Pandas, Seaborn, and Matplotlib.
- **Data Cleaning**: Essential for accurate and reliable analysis.
- **Career Strategy**: Aligning skills with both demand and salary is key.

---

## ⚠️ Challenges I Faced

- **Data Inconsistencies**: Missing or inconsistent data required careful cleaning to maintain analysis quality.  
- **Complex Visualization**: Creating clear visuals from complex data was challenging but essential for insights.  
- **Depth vs Breadth Balance**: Deciding how deeply to analyze each part while maintaining a broad overview required constant balancing to      ensure full coverage without getting lost in details.

---

## 🔮 Future Improvements

- Add interactive dashboards (Tableau / Power BI)  
- Expand analysis beyond the US market  
- Build a data pipeline for automation  
- Include SQL-based analysis  

---

## Conclusion

This exploration of the data analyst job market provided valuable insights into the skills, trends, and evolving expectations shaping the field. It highlights how technical proficiency, especially in tools like Python and data visualization, plays a key role in career advancement. The findings also emphasize the importance of staying updated with shifting market demands to remain competitive.

Overall, this project reinforces that success in data analytics depends on continuous learning, adaptability, and the ability to translate data into meaningful business insights. It serves as a strong foundation for deeper future analysis of the data ecosystem and its ongoing evolution.