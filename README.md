# Fitbit Data Pipeline: Databricks → Snowflake
This is a basic data pipeline using public Fitbit fitness tracker data (https://www.kaggle.com/datasets/arashnic/fitbit), 
created to build hands-on experience with Databricks and Snowflake.

## Pipeline Overview
Raw CSVs → Databricks (PySpark/SQL ingestion, cleaning, joins) → 
Weekly summary table → Exported → Snowflake (loaded, queried, visualized)

## What it does
1. Ingested raw Fitbit CSVs (activity, sleep, heart rate, steps across two time periods)
   into Databricks
3. Combined split time-period tables using a Python loop generating SQL 
   UNION statements, with a schema-match check before each union
4. Joined activity and sleep data, handled nulls and mismatched columns
5. Built a weekly summary aggregate table (avg steps, calories, sleep 
   per user per week)
6. Exported the summary table and loaded it into Snowflake
7. Ran analytical SQL queries and built a trend visualization

## Tools used
Databricks (PySpark, SQL, Delta Lake), Snowflake (SQL, ingestion, 
visualization), Python

## Results
Average activity by week for each user (Databricks Visualization)
<img width="998" height="374" alt="image" src="https://github.com/user-attachments/assets/3fdc1656-264e-40ab-ad17-aca47c248624" />

