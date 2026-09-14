# Zomato-Business-Intelligence-Dashboard
Power BI Business Intelligence dashboard analyzing Zomato restaurant performance, market trends, pricing, cuisines, ratings, and customer engagement across 15 countries.

Portfolio project: Power BI · DAX · Power Query · Data Modeling · Business Intelligence · Microsoft Excel

Zomato Global Restaurant Market Intelligence

An interactive Power BI Business Intelligence dashboard built to analyze Zomato restaurant-market performance across 15 countries and 9,551 restaurants.

The dashboard combines Power Query, data modeling, DAX, interactive filtering, market analysis, pricing analysis, service-feature analysis, cuisine analysis, and city-level drill-downs to turn restaurant-level data into decision-oriented business insights.

📊 Dashboard Overview

The report is organized into focused analytical pages:

Executive Overview

Market Overview

Market Analysis

Pricing & Value

Service Features & Engagement

Cuisine Analysis

Cuisines & Engagement

City Drill Down

Key Insights

A Country slicer is available across the report to move between the global view and individual-country analysis.

1. Executive Overview

The Executive Overview provides the high-level picture of the Zomato restaurant dataset.



Key KPIs

Metric

Value

Total Restaurants

9,551

Total Countries

15

Average Rating

3.44

Online Delivery

25.7%

What this page shows

Total restaurant presence across the dataset

Number of countries represented

Overall average rating

Share of restaurants offering online delivery

Top 10 cities by restaurant count

Country-level restaurant performance

Restaurant volume across price ranges

Business use

This page is designed as the starting point for management or recruiters reviewing the project. It provides a quick view of market scale before moving into detailed country, pricing, service, cuisine, and city analysis.

2. Market Overview

The Market Overview page compares countries using restaurant volume and customer ratings, while also providing a city-level view.



Analysis included

Country Performance

The country table compares:

Country

Total Restaurants

Average Rating — Rated Only

Online Delivery %

The analysis shows a major concentration of restaurants in India, while several smaller markets have higher observed average ratings.

City Drill Down

The city table provides:

City

Total Restaurants

Average Rating — Rated Only

This makes it possible to compare high-volume cities with smaller cities and identify differences in observed restaurant quality.

Business question

Where is restaurant supply concentrated, and how does observed rating performance vary across markets?

3. Market Analysis

The Market page provides a geographic view of restaurant-market presence.



Analysis included

The geographic visualization highlights countries represented in the dataset and provides a visual way to understand the global distribution of the restaurant sample.

Business use

This view is useful for:

Identifying geographic coverage

Understanding market concentration

Comparing the presence of restaurants across regions

Supporting market-expansion discussions

The map should be interpreted together with the country performance table because geographic highlighting alone does not communicate restaurant volume or rating quality.

4. Pricing & Value

The Pricing page analyzes restaurant distribution across the four price-range segments and compares average cost for two people.



Analysis included

Average Cost for Two by Price Segment

Shows the average recorded cost for two people across:

Price Range 1

Price Range 2

Price Range 3

Price Range 4

Restaurant Volume & Average Rating by Price Range

Compares:

Number of restaurants

Average rated-only rating

across the four price segments.

Key observation

The dataset contains a large concentration of restaurants in the lower and middle price segments, while the highest price segment contains fewer restaurants.

The rating curve can then be used to assess whether higher price positioning is associated with higher observed ratings.

Important limitation

Average Cost for Two should not be directly compared across countries because the dataset contains multiple currencies and this project does not perform currency conversion or purchasing-power normalization.

The Country slicer should therefore be used when making cost comparisons.

5. Service Features & Engagement

This page evaluates whether restaurants offering online delivery or table booking show different observed ratings and customer engagement.



Online Delivery

Rating Difference — Online Delivery

-0.09

This means restaurants offering online delivery have an observed average rating approximately 0.09 points lower than restaurants without online delivery, based on the measure used in the dashboard.

Average Votes

The chart compares average votes for restaurants:

With online delivery

Without online delivery

The dashboard shows substantially higher average votes among restaurants with online delivery.

Table Booking

Rating Difference — Table Booking

+0.17

Restaurants offering table booking have an observed average rating approximately 0.17 points higher than restaurants without table booking.

Average Votes

The chart compares average votes for restaurants:

With table booking

Without table booking

Business interpretation

The service-feature analysis suggests that:

Online delivery is associated with greater customer engagement but a slightly lower observed rating.

Table booking is associated with both higher observed ratings and higher average votes.

These are associations in the dataset, not proof that the service features cause higher or lower ratings.

6. Cuisine Analysis

The Cuisine page focuses on the Top 10 cuisines by restaurant presence and compares their average ratings.



Top 10 cuisines analyzed

The dashboard includes:

North Indian

Chinese

Fast Food

Mughlai

Italian

Bakery

Cafe

Continental

Desserts

South Indian

Visuals

Restaurant Presence

The treemap shows the relative restaurant presence of each cuisine.

Larger areas represent cuisines associated with more restaurant records.

Average Rating

The bar chart compares average rated-only ratings for the same Top 10 cuisine set.

Business question

Which cuisines have both meaningful market presence and strong observed ratings?

This helps frame potential cuisine partnership and expansion opportunities.

7. Cuisines & Engagement

This page combines cuisine performance with customer engagement and service-feature analysis.
![Cuisine & Engagement Analysis](screenshots/cuisines.png)




## 8. City Drill Down

The City Drill Down page provides a detailed view of restaurant performance at the city level.
![City Performance](screenshots/City Drill Down.png)




## 9. Key Insights

The Insights page converts the dashboard analysis into business-oriented observations.
![Business Insights](screenshots/Insights.png)






🧮 Data Preparation

The dataset was prepared using Power Query before visualization.

Key transformations

Corrected CSV encoding/parsing

Promoted headers

Applied appropriate data types

Removed duplicate restaurants using Restaurant ID

Removed blank rows

Handled missing/error values

Cleaned text fields

Trimmed cuisine names

Split multi-value cuisine fields into separate rows

Created a country-code lookup table

The original restaurant table remains separate from the cuisine-split table.



🗂️ Data Model

The model uses a country lookup table, the main restaurant table, and a cuisine-split table.

Sheet1 (Country Lookup)
        1
        |
        *
      zomato
        1
        |
        *
zomato split by cuisines

Relationships

Sheet1[Country Code] → zomato[Country Code]

zomato[Restaurant ID] → zomato split by cuisines[Restaurant ID]

The direct Country Lookup → Cuisine Split relationship is inactive to avoid creating an ambiguous filtering path.






🛠️ Tools & Technologies

Technology

Purpose

Power BI

Dashboard development and interactive reporting

DAX

KPIs, rating calculations, engagement measures

Power Query

Data cleaning and transformation

Excel

Country-code lookup

CSV

Restaurant-level source data

Data Modeling

Relationships between restaurant, country, and cuisine data

Data Visualization

Tables, charts, treemaps, KPI cards, and maps




📁 Repository Structure

Zomato-Business-Intelligence-Dashboard/
│
├── README.md
├── LICENSE
│
├── dashboard/
│   └── Zomato_Analytics_Dashboard.pbix
│
├── data/
│   ├── zomato.csv
│   └── Country-Code.xlsx
│
├── screenshots/
    ├── Executive Overview.png
    ├── Market Overview.png
    ├── Market.png
    ├── Pricing.png
    ├── Service Features.png
    ├── Cusines.png
    ├── Cusines and Engagements.png
    ├── City Drill Down.png
    └── Insights.png






🎯 Business Questions Answered

The dashboard was designed around the following questions:

Which countries and cities have the strongest restaurant presence?

Which markets show stronger or weaker observed rating performance?

Does higher price positioning correspond to higher ratings?

How are online delivery and table booking associated with ratings?

How do service features relate to customer engagement?

Which cuisines combine meaningful restaurant presence with strong ratings?

Which cities represent the largest concentrations of restaurants?




🚀 Project Workflow

Raw Zomato Data
       ↓
Power Query Cleaning
       ↓
Data Transformation
       ↓
Country Lookup + Cuisine Split
       ↓
Data Model
       ↓
DAX Measures
       ↓
Interactive Power BI Dashboard
       ↓
Business Analysis
       ↓
Decision-Oriented Insights



📌 Project Scope

Included

Data cleaning and transformation

Data modeling

Country lookup integration

Cuisine normalization

DAX measures

Interactive country filtering

Market analysis

Pricing analysis

Service-feature analysis

Cuisine analysis

City-level analysis

Business insights

Bookmark-based dashboard navigation

Not Included

Live Zomato API integration

Predictive modeling

Forecasting

Currency normalization

Restaurant recommendation engine

Real-time market monitoring



📜 License

This project is distributed under the MIT License.

See LICENSE for the full license text.

