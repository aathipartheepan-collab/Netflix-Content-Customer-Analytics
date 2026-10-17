# Netflix Content & Customer Analytics — Power BI

A Power BI portfolio project analyzing streaming-content metadata and customer engagement using a Netflix-inspired dark-red dashboard theme.

> **Data disclaimer:** This project uses a supplied sample/synthetic dataset for portfolio and learning purposes. It is not official Netflix business data and should not be presented as such.

## Project overview

The report explores content mix, genre distribution, content-addition trends, customer ratings, subscription types, demographics, and watch-time patterns.

### Tools used
- Microsoft Power BI Desktop
- Excel / Power Query prepared data
- DAX measures
- JSON report theme

## Repository structure

```text
Netflix_PowerBI_GitHub_Project/
├── dashboard/
│   └── Netflix_Content_Customer_Analytics.pbix
├── data/
│   └── Netflix_PowerBI_Cleaned_Data.xlsx
├── assets/
│   ├── Netflix_Dashboard_Theme.json
│   ├── Dashboard_Preview_Reference.png
│   └── Dashboard_Icons_Reference.png
├── documentation/
│   ├── DAX_Measures.txt
│   └── PowerBI_Build_Guide.txt
├── README.md
└── .gitignore
```

## Data model

- **Shows** — title metadata such as type, title, country, release year, content classification, genre, duration, and date added.
- **CustomerRatings** — customer demographics, subscription type, linked `show_id`, watch time in minutes, and customer score (1–5).
- **DataQuality / Summary** — supporting data checks and overview.

Recommended relationship: `Shows[show_id]` **(one)** → `CustomerRatings[show_id]` **(many)**, with single-direction filtering from Shows to CustomerRatings.

## Suggested analyses

- Total titles, movies, and TV shows
- Content mix by type and genre
- Titles added over time
- Content age-classification distribution
- Unique customers and total watch hours
- Average customer rating and rating distribution
- Watch time by subscription type, age group, and country
- Genre-level customer rating comparisons

## Key DAX measures

The full measure list is in [`documentation/DAX_Measures.txt`](documentation/DAX_Measures.txt). Examples:

```DAX
Total Titles = DISTINCTCOUNT(Shows[show_id])

Total Watch Minutes = SUM(CustomerRatings[watch_time_minutes])

Total Watch Hours = DIVIDE([Total Watch Minutes], 60, 0)

Average Customer Rating = AVERAGE(CustomerRatings[Customer Rating])
```

## Open the report

1. Install **Power BI Desktop**.
2. Open `dashboard/Netflix_Content_Customer_Analytics.pbix`.
3. If Power BI asks to locate or refresh the source, choose `data/Netflix_PowerBI_Cleaned_Data.xlsx` and map the `Shows` and `CustomerRatings` sheets as needed.
4. Check the relationship in Model view.
5. If desired, import `assets/Netflix_Dashboard_Theme.json` from **View → Themes → Browse for themes**.

Power BI Desktop is required to edit `.pbix` files.

## Data limitations

- The supplied dataset contains 20,000 show records and 20,000 customer-rating/engagement records.
- Missing title/director metadata was handled in the prepared workbook.
- Customer rating (1–5) is different from the show's content classification (for example, PG or TV-MA).
- There are no revenue, subscription start/end dates, or explicit churn fields. Revenue, churn, and true customer-retention metrics cannot be calculated from these data.
- Metrics shown in the preview image are illustrative and should not be assumed to match actual PBIX results unless verified in Power BI.

## GitHub upload

1. Extract this ZIP.
2. Create a new repository on GitHub, e.g. `netflix-power-bi-analytics`.
3. Upload the extracted files/folders, or commit and push them with Git.
4. Keep the `.pbix` and workbook in the repository if repository size policy allows it.

## Author

**Partheepan** — Data Analytics Portfolio Project
