DAX Measures

This document records the core DAX calculations used for the IPL
Performance Analytics Dashboard.

The measures are organized around the dashboard's five analytical pages:

Overview

Team Analysis

Player Analysis

Batting Analysis

Bowling Analysis

Important: DAX expressions must match the exact column names in
the Power BI model. If a column name differs in the .pbix file,
update the expression accordingly.

1. Overview Measures

Total Runs

Total Runs =
SUM(fact_batting_summary[runs])

Used to display the overall number of runs represented in the batting
dataset.

Total Wickets

Total Wickets =
SUM(fact_bowling_summary[wickets])

Used as a high-level bowling KPI.

Total Players

Total Players =
DISTINCTCOUNT(dim_players[player])

Used to show the number of unique players represented in the model.

Total Matches

If the match table contains a unique match identifier:

Total Matches =
DISTINCTCOUNT(dim_match_summary[match_id])

This measure provides the number of unique matches represented in the
dataset.

2. Batting Analysis Measures

Average Runs

Average Runs =
AVERAGE(fact_batting_summary[runs])

Used for comparing average batting output.

Maximum Runs

Maximum Runs =
MAX(fact_batting_summary[runs])

Useful for identifying the highest run value represented in the selected
filter context.

Player Runs

Player Runs =
SUM(fact_batting_summary[runs])

When a player is selected through a slicer or visual interaction, the
filter context limits this measure to that player.

3. Bowling Analysis Measures

Average Wickets

Average Wickets =
AVERAGE(fact_bowling_summary[wickets])

Used for comparing bowling output.

Maximum Wickets

Maximum Wickets =
MAX(fact_bowling_summary[wickets])

Used to identify the highest wicket value in the selected filter
context.

Player Wickets

Player Wickets =
SUM(fact_bowling_summary[wickets])

When a player or team is selected, the existing filter context
determines the displayed result.

4. Team Analysis

The team analysis pages primarily use the same base measures with team
and season fields as the filter context.

For example:

Team Runs =
SUM(fact_batting_summary[runs])

Team Wickets =
SUM(fact_bowling_summary[wickets])

These measures can be placed in charts with team or season fields to
compare performance.

5. Season Analysis

The dashboard can use the same aggregation measures with the season
field on the axis.

For example:

Season Runs =
SUM(fact_batting_summary[runs])

Season Wickets =
SUM(fact_bowling_summary[wickets])

Power BI automatically evaluates these measures for each season when the
season column is used in the visual.

6. Filter Context

A key concept used throughout the dashboard is DAX filter context.

For example, if a visual contains:

Season → 2023
Team   → Chennai Super Kings

then:

Total Runs =
SUM(fact_batting_summary[runs])

does not calculate the sum for the entire dataset. Power BI evaluates
the measure using the active filters and returns the result for the
selected season/team context.

This allows the same measure to power multiple dashboard pages and
visualizations.

7. DAX Design Approach

The dashboard follows a reusable-measure approach rather than creating
separate calculations for every visual.

The general pattern is:

Base Measure
     ↓
Filter Context
     ↓
Team / Player / Season
     ↓
Visualization
     ↓
Business Insight

This keeps the analytical layer easier to maintain and allows the same
measures to support multiple dashboard pages.
