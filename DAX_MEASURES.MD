DAX Measures — IPL Performance Analytics Dashboard

This document contains the core DAX measures used in the IPL Performance Analytics Dashboard built with Power BI.

The dashboard is a single-page interactive report focused on:

Overall IPL KPIs

Season-wise trends

Team performance

Player performance

Interactive filtering

1. Data Model

The dashboard uses a consolidated analytical table:

IPL_Performance_Analytics

Important fields include:

match_id

season

team

player

runs

wickets

balls

SR

overs

economy

DAX expressions must match the exact column names in the Power BI model.

2. KPI Measures

Total Runs

Total Runs =
SUM(IPL_Performance_Analytics[runs])

Calculates total runs and is used in the Total Runs KPI and run-based visuals.

Total Wickets

Total Wickets =
SUM(IPL_Performance_Analytics[wickets])

Calculates total wickets and is used in the Total Wickets KPI.

Total Players

Total Players =
DISTINCTCOUNT(IPL_Performance_Analytics[player])

Counts unique players represented in the dataset.

Total Matches

Total Matches =
DISTINCTCOUNT(IPL_Performance_Analytics[match_id])

Counts unique matches represented in the dataset.

3. Additional Measures

Average Runs

Average Runs =
AVERAGE(IPL_Performance_Analytics[runs])

Calculates average runs within the current filter context.

Maximum Runs

Maximum Runs =
MAX(IPL_Performance_Analytics[runs])

Returns the highest run value within the current filter context.

Average Wickets

Average Wickets =
AVERAGE(IPL_Performance_Analytics[wickets])

Calculates average wickets within the current filter context.

Maximum Wickets

Maximum Wickets =
MAX(IPL_Performance_Analytics[wickets])

Returns the highest wickets value within the current filter context.

4. Dashboard Visuals

Runs by Season

Uses:

Axis   → season
Values → Total Runs

Power BI evaluates Total Runs separately for each season.

Top 5 Teams by Runs

Uses:

Category → team
Values   → Total Runs
Filter   → Top 5

Top 5 Players by Runs

Uses:

Category → player
Values   → Total Runs
Filter   → Top 5

5. Interactive Slicers

The dashboard contains:

Season

Team

Player

These slicers dynamically change the KPI cards and visualizations.

6. DAX Filter Context

A key concept demonstrated by the dashboard is filter context.

For example:

Total Runs =
SUM(IPL_Performance_Analytics[runs])

If the user selects:

Season = 2023
Team = RCB

Power BI evaluates the same measure only against the rows matching those filters.

Conceptually:

DAX Measure
     ↓
Filter Context
     ↓
Season / Team / Player
     ↓
Filtered Data
     ↓
Result

This allows the same measure to be reused across multiple visuals.

7. DAX Design Approach

The dashboard follows a reusable-measure approach instead of creating separate measures for every team, player, or season.

The general pattern is:

Base DAX Measure
       ↓
Filter Context
       ↓
Visualization
       ↓
Business Insight

This keeps the analytical layer simple, reusable, and easy to maintain.

8. DAX Functions Used

Function

Purpose

SUM()

Total runs/wickets

AVERAGE()

Average performance

MAX()

Maximum performance

DISTINCTCOUNT()

Unique players/matches

9. Dashboard Flow

IPL Dataset
     ↓
Power Query
     ↓
Data Cleaning & Transformation
     ↓
IPL_Performance_Analytics
     ↓
DAX Measures
     ↓
KPIs + Slicers + Visualizations
     ↓
Interactive Analysis

The DAX layer provides reusable calculations that respond dynamically to the dashboard's filter context.
