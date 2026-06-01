# Cyclistic Bike-Share Analysis
**Tools:** BigQuery SQL, Tableau | **Dataset:** Q1 2025 (Jan–Mar)

## Overview
End-to-end analysis of Cyclistic bike-share ride data to identify behavioral differences between casual riders and annual members, and recommend a conversion strategy for Cyclistic's marketing team.

Raw data: 588,724 rides across 3 monthly tables. Final clean dataset: 417,656 rides after filtering invalid records and engineering new features.

## Process

**Prepare**
Uploaded 3 monthly CSVs to BigQuery and combined them into a single source-of-truth table using UNION ALL. Validated row counts and checked all key fields for nulls.

**Process**
Filtered out rides under 1 minute (false starts) and over 24 hours (unreturned bikes), and dropped records with missing station data. Engineered 4 new columns: ride duration in minutes, day of week, hour of day, and trip type (round trip vs. one way).

**Analyze**
Ran 9 aggregation queries comparing members and casual riders across ride volume, day of week, hour of day, average duration, long rides, trip type, bike type, and top stations. Results exported to Tableau for visualization.

## Key Findings
- Casual riders average 16.93 min per ride vs. 10.03 min for members — a 69% gap
- Casual ridership peaks on weekends; member ridership peaks on weekday commute hours (8am, 5pm)
- Every top casual start station is a waterfront or tourist destination (Streeter Dr, Millennium Park, Shedd Aquarium)
- Casuals prefer electric bikes; members split evenly between classic and electric

## Recommendation
Casual riders are recreational users, not lapsed commuters. The conversion pitch that works is showing them a membership is the cheaper version of what they already do — not a commuter product. A leisure-first campaign at top casual stations with in-app prompts and geo-targeted weekend ads projects 15,000 to 20,000 conversions annually, or $1.785M to $2.38M in new recurring revenue at roughly 9x return on a $150K to $200K campaign spend.

## Files
- `Christopher_Budhram_SQL_Project.pdf` — all 35 BigQuery queries with results and observations
