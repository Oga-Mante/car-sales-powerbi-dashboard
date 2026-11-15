# Car Sales Performance Dashboard (Power BI)

An interactive Power BI report on 23,906 car sales across 2022 and 2023. It shows what is driving sales growth and where the business should focus.

![Overview page](images/overview.png)

## Executive Summary
- Sales reached $371.2M in 2023, up $70.8M (+23.6%) on 2022.
- The growth is all volume. Cars sold rose 24.6% to 13,261, while the average price slipped 0.8% to $27,991.
- SUVs lead. Sales grew 41% and SUVs overtook Hatchbacks as the largest body style (26.9% of sales against 22.3%).
- The business is seasonal. September, November and December deliver 42% of annual sales.
- Growth is healthy everywhere. All 7 dealer regions grew between 20% and 26%, and no brand dominates (the top 3 of 30 hold 20.9%).
- Weak spot: Red cars grew only 7.7% against 29.4% for White.

## Key Findings
- Growth is volume led. Of the +$70.8M increase, about +$73.8M came from more cars sold and about -$3.0M from lower average prices.
- SUVs are the growth engine. SUV sales rose 41% and their share of sales grew from 23.5% to 26.9%. Hatchbacks fell from 27.8% to 22.3%.
- Colour mix matters. White cars grew 29.4% against 7.7% for Red.
- Sales are seasonal. September, November and December made up 42% of 2023 sales. The peak week reached $14.85M (week 36).
- Growth is broad based. All 7 dealer regions grew between 20% and 26%.
- Brand risk is low. The top 3 of 30 brands hold 20.9% of sales.

## Recommendations
1. Shift stock and marketing spend toward SUVs, the fastest growing body style.
2. Plan inventory and staffing for the September to December peak, which carries 42% of annual sales.
3. Because price is flat, test selective price or option increases on the best selling models, and track their effect on volume.
4. Review the Red colour range and stock mix, as it is growing far slower than the rest.
5. Keep the regional strategy. No region is lagging, so there is no case for region specific intervention yet.

## The Dashboard
Two pages, with a page menu and Year, body style, dealer and transmission slicers.

**Overview**
- Year to date sales, average price and cars sold, each with the change against last year in value and percent, plus month to date figures
- Weekly sales trend with the highest and lowest weeks marked
- Year to date sales by body style and by colour, cars sold by dealer region on a map, and a company table with average price, cars sold and sales

**Details**
- The individual sales records (car, company, model, colour, dealer, date and price) under the same KPIs and filters

![Details page](images/details.png)

## How to Use
1. Download Car_Sales_BI.pbix and open it in Power BI Desktop (free from Microsoft).
2. Select a year in the Year slicer. The year to date figures compare the selected year with the year before.
3. Use the body style, dealer and transmission slicers to filter every visual, and the menu to switch pages.

The report contains its own data, so it opens without a refresh. To refresh it from the source file, point the Power Query source to your copy of the Excel file.

## Data Model
One fact table (car_data, 23,906 rows) with a related calendar table (Calendar Table, linked on Date). 26 DAX measures use time intelligence (TOTALYTD, TOTALMTD, SAMEPERIODLASTYEAR) for year to date, month to date and previous year comparisons, and DIVIDE for the ratios.

## Data Preparation (Power Query)
- Loaded the sales data from Excel, promoted headers and set data types
- Removed personal columns (customer name, phone, income) and a duplicate column (engine)
- Renamed Dealer_No to remove a trailing space and corrected the brand label "Mercedes-B" to "Mercedes-Benz"

## Limitations
- Public dataset covering two years. It is not data from a real company.
- No cost or profit data, so the analysis covers revenue and volume only.
- No customer identifier, so repeat purchase and customer loyalty cannot be analysed.
- The price effect and volume effect are a simple split and do not separate out product mix.
- Week 53 of the weekly trend covers one day only (31 December, about $1.0M), so the lowest point marked on the chart is a partial week and not a real low. The lowest full week is week 2, at about $2.3M.
- The model is a single flat table. A star schema would be the next improvement.

## Files
- Car_Sales_BI.pbix, the Power BI report
- images/, screenshots of each page

## Data Source
Car Sales Report dataset by missionjee on Kaggle: https://www.kaggle.com/datasets/missionjee/car-sales-report
Licence: PASTE THE LICENCE FROM THE KAGGLE PAGE HERE
The data is public and appears to be synthetic.

## Tools
Power BI Desktop, Power Query, DAX, Excel

## Author
Obioma God'swill Nnaemeka, Data Analyst and Economist
LinkedIn: Obioma Nnaemeka
