# Introduction
Dive into the data job market! Focusing on data analyst roles in 2023, this project explores the top-paying jobs, in-demand skills, and where ghigh demand meets high salaray in data analytics. 

SQL queries? Check them out here: [project_sql folder](./project_sql/)
# Answers
1. What are the top-paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What skills are most in demand for data analysts?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?
# Tools I used
Fro my deep dive into the data analyst job market, I harnessed the power of several key tools:

- **SQL**: The backbone of my analysis, allowing me to query the database and unearth critical insights. 
- **PostreSQL**: The chosed database management system, ideal for handling the job posting data.
- **Visual Studio Code**: My go-to for database management and executing SQL queries. 
- **Git & GitHub**: Essential for version control and sharing my SQL scripts and analysis, ensuring collaboration and project tracking. 
- **Power BI**: Used to transform raw query results into interactive dashboards and insightful visualizations, bringing the data story to life. 
# The Analysis
Each query for this project aimed at investigating specific aspects of the data analyst job market. 
Here's how I approached each question:

### 1. Top Paying Data Analyst Jobs
To identify the highest-paying roles, I filtered data analyst positions by average yearly salary and location, focusing on remote jobs. This query highligths the high paying opportunities in the field. 
```sql
SELECT
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    company_dim.name as company_name

FROM 
    job_postings_fact

LEFT JOIN company_dim ON
job_postings_fact.company_id = company_dim.company_id

WHERE
    job_title = 'Data Analyst' AND
    job_location = 'Anywhere' AND
    salary_year_avg IS NOT NULL

ORDER BY
    salary_year_avg DESC   

LIMIT 10 
```
Breakdown of the top data analyst jobs in 2023:
- **Wide Salary Range:** Top 10 paying data analyst roles span from $184,000 to $65o,000. Indication significant salary potential in the field. 
-**Diverse Emplyers:** Companies like SmartAsset, Meta, and AT&T are among those offering high salaries, showing a broad interest across different industries. 
- **Job Title Variety:** There's a high diversity in job titles, from Data Analyst to Director of Analytics, reflecting varied roles and specializations with data analytics. 

![Top 10 skills for Data Analyst](assets\Top_10_skill_count.png)
 * Bar graph visualizing the top 10 skills for data analysts; Chart was created with Power BI from my SQL query results.
# What I learned 
Throughout this project, I've charged my SQL toolkit with some serious power:
- **Complex Qiery Crafting:** Mastered the art of advanced SQL, merging tables like a pro and wielding WITH clauses for ninja-level temp table maneuvers. 
- **Data Agregation:** Got cozy with Group BY and Turned aggregate functions like COUNT() and AVG() into my data-summarizing sidekiks. 
- **Analytical Wizardry:** Leveled up my real-world puzzle-solving skills, turning questions into actionable, insightful SQL queries. 
# Conclusions 
### Insights
---