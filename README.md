# Seoul Bike Rental Demand | Power BI

An interactive Power BI report exploring how hourly bike rentals in Seoul vary by time of day, season, holidays, rainfall, and temperature. The report is an exploratory analysis, not a demand forecast.

**[Watch the 41-second demo](video_review_frames/Seoul_Bike_Demand_PowerBI_Demo.mp4)** · **[Open the Power BI report](seoul_bike_v2.pbix)** · **[Read the executive memo](executive_memo.md)**

## What the report shows

| Page | Focus |
| --- | --- |
| Demand by Hour & Holiday | Hourly patterns by season, holiday comparison, and key performance indicators |
| Weather & Rental Demand | Temperature patterns by season, rainy-versus-dry comparison, and hourly observation counts in tooltips |

Both pages have a date-range filter, a **Clear filters** button, and page navigation.

## Selected findings

These figures use the full 365-day dataset (1 December 2017–30 November 2018). They change when the report is filtered.

- **Summer evening peak:** average rentals at 18:00 were **2,135.14**, compared with **1,418.60** at 08:00 — **50.51% higher**. Each average is based on 92 hourly observations.
- **Holiday comparison:** average hourly rentals were **499.76** on holidays versus **715.23** on non-holidays — **30.13% lower** relative to non-holidays.
- **Rainfall comparison:** rainy hours averaged **163.46** rentals versus **739.31** during dry hours — **77.89% lower** relative to dry hours.
- **Sample-size check:** the autumn 30°C temperature bin has only **two** hourly observations. The tooltip displays the observation count so sparse points can be identified.

These are descriptive associations. They do not show that a holiday, rainfall, or temperature *caused* a change in rentals.

## Data and method

The [Seoul Bike Sharing Demand dataset](https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand) contains 8,760 hourly records. Its date, rental count, weather, season, holiday, and operating-status fields are used here. The dataset is available under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Citation: *Seoul Bike Sharing Demand* [Dataset]. (2020). UCI Machine Learning Repository. https://doi.org/10.24432/C5F62R.

Dates and numeric types were prepared in Power Query. A one-date-per-row `Calendar` table has a one-to-many relationship to the hourly `SeoulBikeData` table. DAX measures calculate totals, hourly and daily averages, percentage comparisons, observed days, and hourly observation counts. Rainy hours are defined as `Rainfall(mm) > 0`; dry hours as `Rainfall(mm) = 0`. Percentage differences use the comparison group's average as the denominator.

The data is citywide, without station identifiers. Some temperature–season bins contain very few records. The results can support planning questions, but station-level allocation would require additional data.

## Files and use

- [`seoul_bike_v2.pbix`](seoul_bike_v2.pbix): two-page Power BI Desktop report.
- [`Seoul_Bike_Demand_PowerBI_Demo.mp4`](video_review_frames/Seoul_Bike_Demand_PowerBI_Demo.mp4): short walkthrough video.
- [`SeoulBikeData.csv`](SeoulBikeData.csv): source data from UCI.
- [`executive_memo.md`](executive_memo.md): decision-oriented summary and limitations.

Download the PBIX and CSV, then open the PBIX in Power BI Desktop. If a refresh cannot find the CSV, update the **Source** step in Power Query to the CSV's location on your computer.
