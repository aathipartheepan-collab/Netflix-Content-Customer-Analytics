# Netflix Content & Customer Analytics Dashboard

## Project Overview
This Power BI project analyses a Netflix-style content catalogue alongside customer ratings and viewing activity. The report uses a dark background with a red Netflix-inspired theme and custom dashboard icons.

> **Data note:** This is a learning/portfolio analysis based on the supplied project dataset. It is not official Netflix company data.

## Dashboard Contents
The supplied `.pbix` report contains one report page (`Page 1`) with KPI cards, charts, slicers, and a table.

### KPI cards
- Total Titles
- Total Movies
- Total TV Shows
- Unique Customers
- Total Watch Hours
- Average Customer Rating

### Charts and analysis
- Titles by type (donut chart)
- Titles added by year (line chart)
- Titles by genre (bar chart)
- Content-rating distribution (100% stacked bar chart)
- Watch hours by subscription type (column chart)
- Watch hours by age group (column chart)
- Customer rating distribution (column chart)
- Customer engagement by country / gender (bar charts)
- A country-level summary table

### Slicers
- Country
- Content type
- Release year
- Age group
- Subscription type
- Gender

## Data Tables and Key Fields

### `Shows`
Content metadata such as `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `Content Rating`, `duration`, `genre`, and `Added Year`.

### `CustomerRatings`
Customer and engagement fields such as `customer_id`, `show_id`, `customer_name`, `age`, `gender`, `country`, `subscription_type`, `watch_time_minutes`, `Customer Rating`, and `Age Group`.

### `tasks`
The report uses a `tasks` table to store measures shown in KPI cards and visuals, including Total Titles, Total Movies, Total TV Shows, Unique Customers, Total Watch Hours, and Average Customer Rating.

## Model Relationship
The report visuals reference both `Shows` and `CustomerRatings` through the shared `show_id` key. When refreshing or rebuilding the model, verify that `Shows[show_id]` relates to `CustomerRatings[show_id]` and that the relationship filters in the intended direction.

## Tools
- Microsoft Power BI Desktop
- DAX measures
- Excel data source
- JSON theme and custom PNG assets embedded in the report

## How to Open
1. Download the Power BI file supplied with this project.
2. Open it using Microsoft Power BI Desktop.
3. If Power BI asks for a data source, reconnect it to the supplied workbook and confirm the `Shows` and `CustomerRatings` tables load correctly.
4. Check the data model and refresh the report.

## Important Limitations
- `Customer Rating` is the customer's score (1–5); `Content Rating` is the title's content classification. They are different fields.
- The supplied data does not include revenue or explicit subscription cancellation/churn fields, so revenue and true churn analysis are outside the scope of this report.
- Confirm figures in Power BI after refresh before quoting them in a portfolio or interview.

## Author
Partheepan — Data Analytics Portfolio Project
