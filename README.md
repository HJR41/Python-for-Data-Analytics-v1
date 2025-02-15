#  The Analysis

## 1. What are the most in-demande skills for the top 3 data roles?
To identify the most in-demand skills for the top three most popular data roles, I first filtered the positions based on popularity. Then, I extracted the top five skills for each of these three roles. The query highlights the most sought-after job titles and their key skills, helping me determine which skills to focus on based on my target role.

View the notebook with steps here:
[2_Skills_Count.ipynb](3_Project\2_Skills_Count.ipynb)

### Visualise Data

```python

fig, ax = plt.subplots(len(job_titles), 1)
sns.set_theme(style='ticks')

for i, job_title in enumerate(job_titles):
    df_plot = df_skills_percent[df_skills_percent['job_title_short'] == job_title].head(5)
    sns.barplot(data=df_plot, x='skill_percent', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
    ax[i].set_xlabel('')
    ax[i].set_ylabel('')
    ax[i].legend().set_visible(False)
    ax[i].set_title(job_title)
    ax[i].set_xlim(0, 75)
plt.show()

```
### Results

![Visualisation for Top Skills of Data Roles](3_Project\images\skill_demand.png)

### Insights

#### Data Analyst

SQL leads at 43%, indicating it’s the most frequently mentioned skill for analysts.
Python is mentioned by 20% of postings—still relevant, but less emphasized than SQL for this role.

#### Data Engineer

SQL tops the list at 70%, underscoring its critical importance for engineering data pipelines and databases.
Python follows closely at 55%, highlighting that engineers also need strong programming skills alongside SQL.

#### Data Scientist

Python is the most mentioned skill (69%), showing its central role in machine learning, data manipulation, and analytics.
SQL ranks second at 44%, reflecting the need for data scientists to query and manage data efficiently, even though Python is more dominant.

#### Key Takeaways:

SQL is universally important across all three roles, but it’s especially critical for Data Engineers (70%).
Python is indispensable for Data Scientists (69%) and also highly valued for Data Engineers (55%).
For Data Analysts, SQL remains the primary skill, while Python, though useful, is less prominent than in the other two roles.
