IPL Performance Analytics Dashboard

Overview

An interactive Power BI analytics dashboard built to explore IPL
performance across seasons, teams, players, batting, and bowling.

The project demonstrates an end-to-end business intelligence workflow:

Data → Cleaning & Transformation → Data Modeling → DAX Measures → KPIs
→ Interactive Visualizations → Insights

Objectives

Analyze IPL performance across multiple seasons

Compare team performance and trends

Evaluate individual player performance

Analyze batting and bowling statistics

Build interactive KPIs and visual reports for exploratory analysis

Present data-driven insights in a business-friendly format

Dashboard Pages

The Power BI report is organized into five analytical pages:

1. Overview

Provides a high-level view of IPL performance with key KPIs, season
trends, and summary visualizations.

2. Team Analysis

Focuses on team-level performance and comparisons across seasons,
helping identify stronger and weaker teams and performance trends.

3. Player Analysis

Provides player-level analysis to compare individual performance and
identify high-performing players.

4. Batting Analysis

Analyzes batting performance using run-based statistics and player/team
comparisons.

5. Bowling Analysis

Analyzes bowling performance using wicket-based statistics and
player/team comparisons.

Data Model

The project follows a dimensional modeling approach with separate
dimension and fact tables.

                 ┌─────────────────────┐
                 │   dim_players       │
                 │  Player attributes  │
                 └──────────┬──────────┘
                            │
                            │
              ┌─────────────┴─────────────┐
              │                           │
┌─────────────▼────────────┐  ┌───────────▼─────────────┐
│ fact_batting_summary     │  │ fact_bowling_summary    │
│ Batting statistics       │  │ Bowling statistics      │
└──────────────────────────┘  └─────────────────────────┘

                 ┌─────────────────────────┐
                 │ dim_match_summary       │
                 │ Match / season context  │
                 └─────────────────────────┘

Tables

Table                               Purpose

dim_players                       Player-level attributes used for
filtering and analysis

dim_match_summary                 Match and season-level information

fact_batting_summary              Batting performance metrics

fact_bowling_summary              Bowling performance metrics

Data Preparation

The data was prepared for Power BI analysis through:

Data cleaning and validation

Data type standardization

Column selection and transformation

Structuring data into fact and dimension tables

Preparation of fields required for filtering and aggregation

Power BI Techniques

The dashboard demonstrates:

Power Query for data transformation

Data Modeling for organizing analytical tables

DAX for calculated measures and KPIs

Interactive slicers and filters

KPI cards

Comparative charts

Season-wise trend analysis

Player and team comparisons

Drill-down style exploratory analysis

Key Analytical Questions

The dashboard is designed to answer questions such as:

How does team performance change across seasons?

Which players have the strongest batting performance?

Which players contribute most effectively with the ball?

How do batting and bowling performances compare across teams?

What trends can be observed across IPL seasons?

Which players or teams stand out based on selected KPIs?

Dashboard Preview

Dashboard screenshots are available in the
screenshot/ directory.

The .pbix file is not included in this repository because of
GitHub's file-size limitations. The repository instead contains the
underlying datasets, dashboard screenshots, and documentation of the
analytical model and DAX logic.

Repository Structure

IPL_ANALYSIS/
│
├── screenshot/
│   ├── dashboard_overview.png
│   ├── team_analysis.png
│   ├── player_analysis.png
│   ├── batting_analysis.png
│   └── bowling_analysis.png
│
├── dim_match_summary.csv
├── dim_players.csv
├── fact_batting_summary.csv
├── fact_bowling_summary.csv
│
├── DAX_MEASURES.md
└── README.md

Skills Demonstrated

Data Analytics: Python, SQL concepts, data cleaning, aggregation,
exploratory analysis

Business Intelligence: Power BI, Power Query, DAX, data modeling,
KPI development, interactive visualization

Analytical Thinking: Trend analysis, comparative analysis,
player/team performance analysis, communicating insights
