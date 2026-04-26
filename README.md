# nashvilleSC-sql-project
SQL analysis of Nashville SC 2025 match data
# Nashville SC 2025 Performance Analysis (SQL Project)

## Overview

I am a huge Nashville Soccer Club fan so i created a project that analyzed match performance data for Nashville SC during the 2025 MLS season using SQL. The goal was to clean raw data and generate meaningful insights related to team performance.

## Dataset

* Source: Publicly available MLS match data
* Contents:

  * Match date
  * Home and away teams
  * Match results (score)
  * Location information

## Tools Used

* SQLite (DB Browser for SQLite)
* SQL

## Data Preparation

The original dataset contained match results stored as text (e.g., "2 - 1"). To enable analysis:

* Created new columns for `home_goals` and `away_goals`
* Parsed and converted score data from text into numeric values using SQL string functions
* Structured the dataset for analysis using SQL queries

## Key Analysis

The following analyses were performed using SQL:

* Win / Loss / Draw breakdown
* Win percentage calculation
* Home vs Away performance comparison
* Total goals scored and conceded
* Opponent frequency analysis

## Example Query

```sql
SELECT 
    ROUND(
        100.0 * SUM(
            CASE 
                WHEN ("Home Team" = 'Nashville' AND home_goals > away_goals)
                  OR ("Away Team" = 'Nashville' AND away_goals > home_goals)
                THEN 1 ELSE 0
            END
        ) / COUNT(*),
    2) AS win_percentage
FROM nashvilleSC2025;
```

## Key Insights

* Calculated overall win percentage for the season
* Compared team performance in home vs away matches
* Evaluated scoring efficiency by analyzing goals scored vs conceded
* Identified frequently played opponents

## Project Structure

* `nashville_analysis.sql` → SQL queries used for cleaning and analysis
* `nashville_matches.csv` → Original dataset
* `README.md` → Project documentation

## Summary

This project demonstrates my ability to:

* Import and structure raw data into a database
* Clean and transform data using SQL
* Apply analytical thinking to extract insights
* Use SQL functions such as CASE, GROUP BY, and aggregations

