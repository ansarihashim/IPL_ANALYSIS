# IPL Performance Analytics Dashboard — Power BI

An interactive one-page Power BI dashboard designed to analyze IPL performance across seasons, teams, and players.

The project demonstrates a practical business intelligence workflow:

**Data → Data Cleaning & Transformation → DAX Measures → KPIs → Interactive Filters → Visual Analytics → Insights**

---

## 📊 Dashboard Overview

The dashboard provides a compact overview of IPL performance using interactive KPIs, season-wise trends, team comparisons, and player performance analysis.

### Dashboard includes:

- Total Runs
- Total Wickets
- Total Players
- Total Matches
- Season-wise run trends
- Top 5 players by runs
- Top 5 teams by runs
- Interactive Season filter
- Interactive Team filter
- Interactive Player filter

The dashboard is intentionally designed as a **single-page analytical report** to provide the most important insights without unnecessary visual complexity.

---

## 🎯 Project Objectives

The main objective of this project is to build a simple but practical Power BI dashboard capable of answering common IPL performance questions.

The dashboard focuses on:

- Understanding overall IPL performance
- Comparing team performance
- Identifying high-performing players
- Analyzing performance trends across seasons
- Building reusable DAX measures
- Creating interactive Power BI visualizations
- Presenting analytical information in a business-friendly format

---

# 📌 Dashboard Features

## 1. KPI Overview

The dashboard contains four high-level KPIs:

| KPI | Purpose |
|---|---|
| Total Runs | Total runs represented in the dataset |
| Total Wickets | Total wickets represented in the dataset |
| Total Players | Number of unique players |
| Total Matches | Number of unique matches |

These KPIs provide an immediate summary of the dataset and update according to the selected filters.

---

## 2. Season-wise Performance

### Runs by Season

A line chart is used to visualize how total runs change across IPL seasons.

This allows users to quickly identify:

- Growth or decline in total runs
- Differences between seasons
- Overall performance trends

---

## 3. Team Performance

### Top 5 Teams by Runs

A horizontal bar chart compares teams based on their total runs.

The visualization helps identify teams with higher batting contributions within the selected filter context.

The chart can also respond to the Season and Player slicers.

---

## 4. Player Performance

### Top 5 Players by Runs

A horizontal bar chart displays the highest-performing players based on total runs.

This provides a simple way to compare individual batting contributions.

---

# 🎛️ Interactive Filters

The dashboard contains three slicers:

### Season

Allows users to analyze performance for a specific IPL season.

### Team

Allows users to filter the dashboard by team.

### Player

Allows users to focus the dashboard on an individual player.

The same DAX measures are dynamically recalculated based on the selected filter context.

---

# 🧮 DAX Measures

The dashboard uses reusable DAX measures rather than creating separate calculations for individual visuals.

## Total Runs

```DAX
Total Runs =
SUM(IPL_Performance_Analytics[runs])
