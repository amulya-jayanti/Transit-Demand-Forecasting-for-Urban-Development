**Transit Demand Forecasting for Urban Development**

Project Summary
This project analyzes transit demand across New York City using data from the NYC Taxi and Limousine Commission (TLC), encompassing green/yellow taxis, for-hire vehicles (FHV), and rideshare platforms. Our goal is to uncover actionable insights for urban planning, traffic optimization, and transportation equity using ride-level and geospatial data.

📊 Objectives

Identify high-demand transit corridors and underserved zones\
Analyze rush hour dynamics and ride preference by mode\
Support data-driven infrastructure planning (e.g., new bus routes, congestion relief)\
Evaluate accessibility (e.g., wheelchair support) and demographic reach\
Compare rideshare vs taxi utilization patterns to inform public/private strategies

🧱 Data Sources

New York City Taxi and Limousine Commission, with data and dictionaries for taxi, rideshare, and for-hire vehicle trips https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page\ 
NYC TLC Zone data Lookup File: https://d37ci6vzurychx.cloudfront.net/misc/\
NYC Census: https://www.nyc.gov/site/planning/planning-level/nyc-population/2020-census.page

⚙️ Data Processing Pipeline

✅ Preprocessing & Normalization\
Removed null and malformed records\
Converted datatypes, validated numeric ranges, and standardized categorical entries\
✅ Database Modeling\
Normalized raw data to 3NF, created ER diagrams\
Designed a star schema around a fact_ride table with dimensions for time, location, vehicle, and payment\
Loaded data into a local MySQL server for development, then migrated to GCP MySQL for scalability\
✅ Cloud Integration\
Staged data in Google Cloud Storage (GCS), exported final model to SQL dump\
Tables were created via DDL, populated using DML, and cleaned up for production

🔍 Insights & Business Use Cases

1. Most Common Routes\
Finding: Top 10 routes are short (<2 miles) and highly concentrated in Manhattan\
Impact: Highlights areas where surface transit (e.g., buses) may be underperforming\
2. Rush Hour Analysis\
Finding: Taxis peak at 5–6 PM, while rideshares peak at 8 AM and maintain high demand all day\
Impact: Informs driver deployment strategies and demand-specific pricing models\
3. Popular Zones\
Finding: High overlap between pickup/drop-off zones in Midtown & Upper East Side\
Impact: Suggests corridors for targeted infrastructure upgrades\
4. Population vs. Ride Popularity\
Finding: Manhattan far outpaces other boroughs in rides per capita\
Impact: Reveals inequities in transit access and opportunities for outreach in Brooklyn/Bronx\
5. Wheelchair Accessibility\
Finding: ~33% of rideshares accommodate wheelchairs, taxis lag behind\
Impact: Advocates accessibility mandates for traditional taxi fleets

📈 Dashboard Overview

Interactive filters for ride type (taxi vs rideshare)\
Visualized routes, borough-level demand, rush hour patterns, and accessibility coverage\
Designed for urban planners, transit agencies, and transportation providers

🔧 Recommendations & Future Work

🔄 Improve ETL Efficiency\
Use BigQuery with GCS to avoid heavy intermediate transformations\
Adopt Apache Beam/Dataflow for scalable, parallelized ingestion\
🧩 Integrate NoSQL for Flexibility\
Use MongoDB for unstructured data (e.g., driver feedback, app logs)\
📈 Expand Business Use Cases\
Revenue optimization via fare modeling during peak/off-peak hours\
Sustainability insights comparing emissions between ride types\
Geospatial layering to correlate demand with income, housing density, and transit deserts\

🤝 Acknowledgments

NYC Taxi & Limousine Commission for open data\
NYC Planning Department for 2020 Census data\
Google Cloud Platform for infrastructure support
