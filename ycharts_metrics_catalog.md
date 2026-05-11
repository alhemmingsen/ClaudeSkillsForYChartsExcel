# YCharts Metrics Catalog, Table of Contents

Each section's starting line number in this file is given below. Use
`view_range` to load just the section you need rather than the whole
file (the income statement section alone is ~750 lines).

- Line 28: How to use this file
- Line 44: 1. Daily Prices (OHLC), Companies & ETFs
- Line 79: 2. Price Returns, Companies
- Line 240: 3. Price Returns, ETFs & Indexes
- Line 407: 4. Price Returns, Mutual Funds
- Line 574: 5. Income Statement & Financial Metrics (Companies)
- Line 1326: 6. Balance Sheet (Companies)
- Line 1416: 7. Cash Flow Statement (Companies)
- Line 1492: 8. Valuation Multiples (Companies)
- Line 1531: 9. Company Info Fields (use with YCI)
- Line 1557: 10. Macroeconomic Indicators
- Line 1603: 11. YCS Parameter Options

---

# YCharts Common Metrics Catalog

_Companion reference for the `ycharts-excel-formulas` skill. Curated subset focused on prices, returns, financial statements, and key info fields._

_Source: YCharts Excel Add-in Formula Syntax Guide_

## How to use this file

1. Find the metric you need by category below.
2. Use the calculation code with `YCP` (single date) or `YCS` (date range).
3. Replace the example ticker (`MSFT`, `SPXU`, etc.) with your own.

**Ticker prefix conventions:**
- Company / equity: bare ticker (`MSFT`, `AAPL`)
- Mutual fund: `M:` prefix (`M:AWSHX`)
- Separate account: `S:` prefix (`S:0P0000JCML`)
- Model portfolio: `P:` prefix (`P:12345`)
- Custom security / index: `Y:` prefix (`Y:1234`)
- Bloomberg-style ` US` suffix is rejected, strip with `TRIM(SUBSTITUTE(B2,"US",""))`

---

## 1. Daily Prices (OHLC), Companies & ETFs

### Companies

| Metric | Code | Example |
|---|---|---|
| Close Price (Daily) | `close_price` | YCP("MSFT","close_price") |
| High Price (Daily) | `high_price` | YCP("MSFT","high_price") |
| Low Price (Daily) | `low_price` | YCP("MSFT","low_price") |
| Open Price (Daily) | `open_price` | YCP("MSFT","open_price") |
| Price | `price` | YCP("MSFT","price") |
| Volume | `volume` | YCP("MSFT","volume") |

### ETFs & CEFs

| Metric | Code | Example |
|---|---|---|
| Close Price (Daily) | `close_price` | YCP("SPXU","close_price") |
| High Price (Daily) | `high_price` | YCP("SPXU","high_price") |
| Low Price (Daily) | `low_price` | YCP("SPXU","low_price") |
| Open Price (Daily) | `open_price` | YCP("SPXU","open_price") |
| Price | `price` | YCP("SPXU","price") |
| Volume | `volume` | YCP("SPXU","volume") |

### Mutual Funds

| Metric | Code | Example |
|---|---|---|
| Close Price (Daily) | `close_price` | YCP("M:AWSHX","close_price") |
| Price | `price` | YCP("M:AWSHX","price") |

_Note: Mutual funds, separate accounts, model portfolios, and custom securities typically only expose a daily close (`price` or `level`). Open/High/Low are not available for those types._

---

## 2. Price Returns, Companies

| Metric | Code | Example |
|---|---|---|
| 1 Day Returns (Daily Close) | `roc_1_close` | YCP("MSFT","roc_1_close") |
| 1 Day Returns (Daily) | `roc_1` | YCP("MSFT","roc_1") |
| 1 Month Price Returns (Daily) | `one_month_return` | YCP("MSFT","one_month_return") |
| 1 Month Price Returns (Monthly) | `monthly_return` | YCP("MSFT","monthly_return") |
| 1 Month Total Returns (Daily) | `one_month_total_return` | YCP("MSFT","one_month_total_return") |
| 1 Month Total Returns (Monthly) | `total_monthly_return` | YCP("MSFT","total_monthly_return") |
| 1 Week Price Returns (Daily) | `one_week_return` | YCP("MSFT","one_week_return") |
| 1 Week Total Returns (Daily) | `one_week_total_return` | YCP("MSFT","one_week_total_return") |
| 1 Year Price Returns (Annual) | `one_year_annual_return` | YCP("MSFT","one_year_annual_return") |
| 1 Year Price Returns (Daily) | `one_year_return` | YCP("MSFT","one_year_return") |
| 1 Year Price Returns (Monthly) | `one_year_monthly_return` | YCP("MSFT","one_year_monthly_return") |
| 1 Year Price Returns (Quarterly) | `one_year_quarterly_return` | YCP("MSFT","one_year_quarterly_return") |
| 1 Year Total Returns (Annual) | `one_year_total_annual_return` | YCP("MSFT","one_year_total_annual_return") |
| 1 Year Total Returns (Daily) | `one_year_total_return` | YCP("MSFT","one_year_total_return") |
| 1 Year Total Returns (Monthly) | `one_year_total_monthly_return` | YCP("MSFT","one_year_total_monthly_return") |
| 1 Year Total Returns (Quarterly) | `one_year_quarterly_total_return` | YCP("MSFT","one_year_quarterly_total_return") |
| 10 Day Returns (Daily) | `roc_10` | YCP("MSFT","roc_10") |
| 10 Year Price Returns (Annual) | `ten_year_annual_return` | YCP("MSFT","ten_year_annual_return") |
| 10 Year Price Returns (Daily) | `ten_year_return` | YCP("MSFT","ten_year_return") |
| 10 Year Price Returns (Monthly) | `ten_year_monthly_return` | YCP("MSFT","ten_year_monthly_return") |
| 10 Year Price Returns (Quarterly) | `ten_year_quarterly_return` | YCP("MSFT","ten_year_quarterly_return") |
| 10 Year Total Returns (Annual) | `ten_year_total_annual_return` | YCP("MSFT","ten_year_total_annual_return") |
| 10 Year Total Returns (Daily) | `ten_year_total_return` | YCP("MSFT","ten_year_total_return") |
| 10 Year Total Returns (Monthly) | `ten_year_total_monthly_return` | YCP("MSFT","ten_year_total_monthly_return") |
| 10 Year Total Returns (Quarterly) | `ten_year_quarterly_total_return` | YCP("MSFT","ten_year_quarterly_total_return") |
| 12 Day Returns (Daily) | `roc_12` | YCP("MSFT","roc_12") |
| 15 Year Price Returns (Annual) | `fifteen_year_annual_return` | YCP("MSFT","fifteen_year_annual_return") |
| 15 Year Price Returns (Daily) | `fifteen_year_return` | YCP("MSFT","fifteen_year_return") |
| 15 Year Price Returns (Monthly) | `fifteen_year_monthly_return` | YCP("MSFT","fifteen_year_monthly_return") |
| 15 Year Price Returns (Quarterly) | `fifteen_year_quarterly_return` | YCP("MSFT","fifteen_year_quarterly_return") |
| 15 Year Total Returns (Annual) | `fifteen_year_total_annual_return` | YCP("MSFT","fifteen_year_total_annual_return") |
| 15 Year Total Returns (Daily) | `fifteen_year_total_return` | YCP("MSFT","fifteen_year_total_return") |
| 15 Year Total Returns (Monthly) | `fifteen_year_total_monthly_return` | YCP("MSFT","fifteen_year_total_monthly_return") |
| 15 Year Total Returns (Quarterly) | `fifteen_year_quarterly_total_return` | YCP("MSFT","fifteen_year_quarterly_total_return") |
| 20 Day Returns (Daily) | `roc_20` | YCP("MSFT","roc_20") |
| 20 Year Price Returns (Annual) | `twenty_year_annual_return` | YCP("MSFT","twenty_year_annual_return") |
| 20 Year Price Returns (Daily) | `twenty_year_return` | YCP("MSFT","twenty_year_return") |
| 20 Year Price Returns (Monthly) | `twenty_year_monthly_return` | YCP("MSFT","twenty_year_monthly_return") |
| 20 Year Total Returns (Annual) | `twenty_year_total_annual_return` | YCP("MSFT","twenty_year_total_annual_return") |
| 20 Year Total Returns (Daily) | `twenty_year_total_return` | YCP("MSFT","twenty_year_total_return") |
| 20 Year Total Returns (Monthly) | `twenty_year_total_monthly_return` | YCP("MSFT","twenty_year_total_monthly_return") |
| 3 Day Returns (Daily) | `roc_3` | YCP("MSFT","roc_3") |
| 3 Month Price Returns (Daily) | `three_month_return` | YCP("MSFT","three_month_return") |
| 3 Month Price Returns (Monthly) | `three_monthly_return` | YCP("MSFT","three_monthly_return") |
| 3 Month Price Returns (Quarterly) | `quarterly_return` | YCP("MSFT","quarterly_return") |
| 3 Month Total Returns (Daily) | `three_month_total_return` | YCP("MSFT","three_month_total_return") |
| 3 Month Total Returns (Monthly) | `three_total_monthly_return` | YCP("MSFT","three_total_monthly_return") |
| 3 Month Total Returns (Quarterly) | `quarterly_total_return` | YCP("MSFT","quarterly_total_return") |
| 3 Year Price Returns (Annual) | `three_year_annual_return` | YCP("MSFT","three_year_annual_return") |
| 3 Year Price Returns (Daily) | `three_year_return` | YCP("MSFT","three_year_return") |
| 3 Year Price Returns (Monthly) | `three_year_monthly_return` | YCP("MSFT","three_year_monthly_return") |
| 3 Year Price Returns (Quarterly) | `three_year_quarterly_return` | YCP("MSFT","three_year_quarterly_return") |
| 3 Year Total Returns (Annual) | `three_year_total_annual_return` | YCP("MSFT","three_year_total_annual_return") |
| 3 Year Total Returns (Daily) | `three_year_total_return` | YCP("MSFT","three_year_total_return") |
| 3 Year Total Returns (Monthly) | `three_year_total_monthly_return` | YCP("MSFT","three_year_total_monthly_return") |
| 3 Year Total Returns (Quarterly) | `three_year_quarterly_total_return` | YCP("MSFT","three_year_quarterly_total_return") |
| 5 Day Returns (Daily) | `roc_5` | YCP("MSFT","roc_5") |
| 5 Year Price Returns (Annual) | `five_year_annual_return` | YCP("MSFT","five_year_annual_return") |
| 5 Year Price Returns (Daily) | `five_year_return` | YCP("MSFT","five_year_return") |
| 5 Year Price Returns (Monthly) | `five_year_monthly_return` | YCP("MSFT","five_year_monthly_return") |
| 5 Year Price Returns (Quarterly) | `five_year_quarterly_return` | YCP("MSFT","five_year_quarterly_return") |
| 5 Year Total Returns (Annual) | `five_year_total_annual_return` | YCP("MSFT","five_year_total_annual_return") |
| 5 Year Total Returns (Daily) | `five_year_total_return` | YCP("MSFT","five_year_total_return") |
| 5 Year Total Returns (Monthly) | `five_year_total_monthly_return` | YCP("MSFT","five_year_total_monthly_return") |
| 5 Year Total Returns (Quarterly) | `five_year_quarterly_total_return` | YCP("MSFT","five_year_quarterly_total_return") |
| 6 Month Price Returns (Daily) | `six_month_return` | YCP("MSFT","six_month_return") |
| 6 Month Price Returns (Monthly) | `six_monthly_return` | YCP("MSFT","six_monthly_return") |
| 6 Month Total Returns (Daily) | `six_month_total_return` | YCP("MSFT","six_month_total_return") |
| 6 Month Total Returns (Monthly) | `six_total_monthly_return` | YCP("MSFT","six_total_monthly_return") |
| 7 Year Price Returns (Annual) | `seven_year_annual_return` | YCP("MSFT","seven_year_annual_return") |
| 7 Year Price Returns (Daily) | `seven_year_return` | YCP("MSFT","seven_year_return") |
| 7 Year Price Returns (Monthly) | `seven_year_monthly_return` | YCP("MSFT","seven_year_monthly_return") |
| 7 Year Total Returns (Annual) | `seven_year_total_annual_return` | YCP("MSFT","seven_year_total_annual_return") |
| 7 Year Total Returns (Daily) | `seven_year_total_return` | YCP("MSFT","seven_year_total_return") |
| 7 Year Total Returns (Monthly) | `seven_year_total_monthly_return` | YCP("MSFT","seven_year_total_monthly_return") |
| 9 Month Price Returns (Monthly) | `nine_monthly_return` | YCP("MSFT","nine_monthly_return") |
| 9 Month Total Returns (Monthly) | `nine_total_monthly_return` | YCP("MSFT","nine_total_monthly_return") |
| Annualized 1 Month Price Returns (Daily) | `annualized_daily_one_month_return` | YCP("MSFT","annualized_daily_one_month_return") |
| Annualized 1 Month Price Returns (Monthly) | `annualized_one_month_return` | YCP("MSFT","annualized_one_month_return") |
| Annualized 1 Month Total Returns (Daily) | `annualized_daily_one_month_total_return` | YCP("MSFT","annualized_daily_one_month_total_return") |
| Annualized 1 Month Total Returns (Monthly) | `annualized_one_month_total_return` | YCP("MSFT","annualized_one_month_total_return") |
| Annualized 1 Year Price Returns (Daily) | `annualized_daily_one_year_return` | YCP("MSFT","annualized_daily_one_year_return") |
| Annualized 1 Year Price Returns (Monthly) | `annualized_one_year_return` | YCP("MSFT","annualized_one_year_return") |
| Annualized 1 Year Total Returns (Daily) | `annualized_daily_one_year_total_return` | YCP("MSFT","annualized_daily_one_year_total_return") |
| Annualized 1 Year Total Returns (Monthly) | `annualized_one_year_total_return` | YCP("MSFT","annualized_one_year_total_return") |
| Annualized 10 Year Price Returns (Daily) | `annualized_daily_ten_year_return` | YCP("MSFT","annualized_daily_ten_year_return") |
| Annualized 10 Year Price Returns (Monthly) | `annualized_ten_year_return` | YCP("MSFT","annualized_ten_year_return") |
| Annualized 10 Year Price Returns (Quarterly) | `annualized_ten_year_quarterly_return` | YCP("MSFT","annualized_ten_year_quarterly_return") |
| Annualized 10 Year Total Returns (Daily) | `annualized_daily_ten_year_total_return` | YCP("MSFT","annualized_daily_ten_year_total_return") |
| Annualized 10 Year Total Returns (Monthly) | `annualized_ten_year_total_return` | YCP("MSFT","annualized_ten_year_total_return") |
| Annualized 10 Year Total Returns (Quarterly) | `annualized_ten_year_quarterly_total_return` | YCP("MSFT","annualized_ten_year_quarterly_total_return") |
| Annualized 15 Year Price Returns (Daily) | `annualized_daily_fifteen_year_return` | YCP("MSFT","annualized_daily_fifteen_year_return") |
| Annualized 15 Year Price Returns (Monthly) | `annualized_fifteen_year_return` | YCP("MSFT","annualized_fifteen_year_return") |
| Annualized 15 Year Price Returns (Quarterly) | `annualized_fifteen_year_quarterly_return` | YCP("MSFT","annualized_fifteen_year_quarterly_return") |
| Annualized 15 Year Total Returns (Daily) | `annualized_daily_fifteen_year_total_return` | YCP("MSFT","annualized_daily_fifteen_year_total_return") |
| Annualized 15 Year Total Returns (Monthly) | `annualized_fifteen_year_total_return` | YCP("MSFT","annualized_fifteen_year_total_return") |
| Annualized 15 Year Total Returns (Quarterly) | `annualized_fifteen_year_quarterly_total_return` | YCP("MSFT","annualized_fifteen_year_quarterly_total_return") |
| Annualized 20 Year Price Returns (Daily) | `annualized_daily_twenty_year_return` | YCP("MSFT","annualized_daily_twenty_year_return") |
| Annualized 20 Year Price Returns (Monthly) | `annualized_twenty_year_return` | YCP("MSFT","annualized_twenty_year_return") |
| Annualized 20 Year Total Returns (Daily) | `annualized_daily_twenty_year_total_return` | YCP("MSFT","annualized_daily_twenty_year_total_return") |
| Annualized 20 Year Total Returns (Monthly) | `annualized_twenty_year_total_return` | YCP("MSFT","annualized_twenty_year_total_return") |
| Annualized 3 Month Price Returns (Daily) | `annualized_daily_three_month_return` | YCP("MSFT","annualized_daily_three_month_return") |
| Annualized 3 Month Price Returns (Monthly) | `annualized_three_month_return` | YCP("MSFT","annualized_three_month_return") |
| Annualized 3 Month Total Returns (Daily) | `annualized_daily_three_month_total_return` | YCP("MSFT","annualized_daily_three_month_total_return") |
| Annualized 3 Month Total Returns (Monthly) | `annualized_three_month_total_return` | YCP("MSFT","annualized_three_month_total_return") |
| Annualized 3 Year Price Returns (Daily) | `annualized_daily_three_year_return` | YCP("MSFT","annualized_daily_three_year_return") |
| Annualized 3 Year Price Returns (Monthly) | `annualized_three_year_return` | YCP("MSFT","annualized_three_year_return") |
| Annualized 3 Year Price Returns (Quarterly) | `annualized_three_year_quarterly_return` | YCP("MSFT","annualized_three_year_quarterly_return") |
| Annualized 3 Year Total Returns (Daily) | `annualized_daily_three_year_total_return` | YCP("MSFT","annualized_daily_three_year_total_return") |
| Annualized 3 Year Total Returns (Monthly) | `annualized_three_year_total_return` | YCP("MSFT","annualized_three_year_total_return") |
| Annualized 3 Year Total Returns (Quarterly) | `annualized_three_year_quarterly_total_return` | YCP("MSFT","annualized_three_year_quarterly_total_return") |
| Annualized 5 Year Price Returns (Daily) | `annualized_daily_five_year_return` | YCP("MSFT","annualized_daily_five_year_return") |
| Annualized 5 Year Price Returns (Monthly) | `annualized_five_year_return` | YCP("MSFT","annualized_five_year_return") |
| Annualized 5 Year Price Returns (Quarterly) | `annualized_five_year_quarterly_return` | YCP("MSFT","annualized_five_year_quarterly_return") |
| Annualized 5 Year Total Returns (Daily) | `annualized_daily_five_year_total_return` | YCP("MSFT","annualized_daily_five_year_total_return") |
| Annualized 5 Year Total Returns (Monthly) | `annualized_five_year_total_return` | YCP("MSFT","annualized_five_year_total_return") |
| Annualized 5 Year Total Returns (Quarterly) | `annualized_five_year_quarterly_total_return` | YCP("MSFT","annualized_five_year_quarterly_total_return") |
| Annualized 6 Month Price Returns (Daily) | `annualized_daily_six_month_return` | YCP("MSFT","annualized_daily_six_month_return") |
| Annualized 6 Month Price Returns (Monthly) | `annualized_six_month_return` | YCP("MSFT","annualized_six_month_return") |
| Annualized 6 Month Total Returns (Daily) | `annualized_daily_six_month_total_return` | YCP("MSFT","annualized_daily_six_month_total_return") |
| Annualized 6 Month Total Returns (Monthly) | `annualized_six_month_total_return` | YCP("MSFT","annualized_six_month_total_return") |
| Annualized 7 Year Price Returns (Daily) | `annualized_daily_seven_year_return` | YCP("MSFT","annualized_daily_seven_year_return") |
| Annualized 7 Year Price Returns (Monthly) | `annualized_seven_year_return` | YCP("MSFT","annualized_seven_year_return") |
| Annualized 7 Year Total Returns (Daily) | `annualized_daily_seven_year_total_return` | YCP("MSFT","annualized_daily_seven_year_total_return") |
| Annualized 7 Year Total Returns (Monthly) | `annualized_seven_year_total_return` | YCP("MSFT","annualized_seven_year_total_return") |
| Annualized 9 Month Price Returns (Daily) | `annualized_daily_nine_month_return` | YCP("MSFT","annualized_daily_nine_month_return") |
| Annualized 9 Month Price Returns (Monthly) | `annualized_nine_month_return` | YCP("MSFT","annualized_nine_month_return") |
| Annualized 9 Month Total Returns (Daily) | `annualized_daily_nine_month_total_return` | YCP("MSFT","annualized_daily_nine_month_total_return") |
| Annualized 9 Month Total Returns (Monthly) | `annualized_nine_month_total_return` | YCP("MSFT","annualized_nine_month_total_return") |
| Annualized Price Returns Since Inception (Daily) | `annualized_daily_all_time_return` | YCP("MSFT","annualized_daily_all_time_return") |
| Annualized Price Returns Since Inception (Monthly) | `annualized_all_time_return` | YCP("MSFT","annualized_all_time_return") |
| Annualized Price Returns Since Inception (Quarterly) | `annualized_all_time_quarterly_return` | YCP("MSFT","annualized_all_time_quarterly_return") |
| Annualized Total Returns Since Inception (Daily) | `annualized_daily_all_time_total_return` | YCP("MSFT","annualized_daily_all_time_total_return") |
| Annualized Total Returns Since Inception (Monthly) | `annualized_all_time_total_return` | YCP("MSFT","annualized_all_time_total_return") |
| Annualized Total Returns Since Inception (Quarterly) | `annualized_all_time_quarterly_total_return` | YCP("MSFT","annualized_all_time_quarterly_total_return") |
| CAPM Expected Return | `capm_expected_return` | YCP("MSFT","capm_expected_return") |
| Month to Date Price Returns (Daily) | `mtd_return` | YCP("MSFT","mtd_return") |
| Month to Date Total Returns (Daily) | `mtd_total_return` | YCP("MSFT","mtd_total_return") |
| Price Returns Since Inception (Annual) | `all_time_annual_return` | YCP("MSFT","all_time_annual_return") |
| Price Returns Since Inception (Daily) | `all_time_return` | YCP("MSFT","all_time_return") |
| Price Returns Since Inception (Monthly) | `all_time_monthly_return` | YCP("MSFT","all_time_monthly_return") |
| Price Returns Since Inception (Quarterly) | `all_time_quarterly_return` | YCP("MSFT","all_time_quarterly_return") |
| Quarter to Date Price Returns (Daily) | `qtd_return` | YCP("MSFT","qtd_return") |
| Quarter to Date Price Returns (Monthly) | `qtd_monthly_return` | YCP("MSFT","qtd_monthly_return") |
| Quarter to Date Total Returns (Daily) | `qtd_total_return` | YCP("MSFT","qtd_total_return") |
| Quarter to Date Total Returns (Monthly) | `qtd_total_monthly_return` | YCP("MSFT","qtd_total_monthly_return") |
| Total Returns Since Inception (Annual) | `all_time_total_annual_return` | YCP("MSFT","all_time_total_annual_return") |
| Total Returns Since Inception (Daily) | `all_time_total_return` | YCP("MSFT","all_time_total_return") |
| Total Returns Since Inception (Monthly) | `all_time_total_monthly_return` | YCP("MSFT","all_time_total_monthly_return") |
| Total Returns Since Inception (Quarterly) | `all_time_quarterly_total_return` | YCP("MSFT","all_time_quarterly_total_return") |
| Year to Date Price Returns (Daily) | `ytd_return` | YCP("MSFT","ytd_return") |
| Year to Date Price Returns (Monthly) | `ytd_monthly_return` | YCP("MSFT","ytd_monthly_return") |
| Year to Date Total Returns (Daily) | `ytd_total_return` | YCP("MSFT","ytd_total_return") |
| Year to Date Total Returns (Monthly) | `ytd_total_monthly_return` | YCP("MSFT","ytd_total_monthly_return") |

---

## 3. Price Returns, ETFs & Indexes

| Metric | Code | Example |
|---|---|---|
| 1 Day NAV Returns (Daily) | `roc_1_nav` | YCP("SPXU","roc_1_nav") |
| 1 Day Returns (Daily Close) | `roc_1_close` | YCP("SPXU","roc_1_close") |
| 1 Day Returns (Daily) | `roc_1` | YCP("SPXU","roc_1") |
| 1 Month Price Returns (Daily) | `one_month_return` | YCP("SPXU","one_month_return") |
| 1 Month Price Returns (Monthly) | `monthly_return` | YCP("SPXU","monthly_return") |
| 1 Month Total Returns (Daily) | `one_month_total_return` | YCP("SPXU","one_month_total_return") |
| 1 Month Total Returns (Monthly) | `total_monthly_return` | YCP("SPXU","total_monthly_return") |
| 1 Week Price Returns (Daily) | `one_week_return` | YCP("SPXU","one_week_return") |
| 1 Week Total Returns (Daily) | `one_week_total_return` | YCP("SPXU","one_week_total_return") |
| 1 Year Price Returns (Annual) | `one_year_annual_return` | YCP("SPXU","one_year_annual_return") |
| 1 Year Price Returns (Daily) | `one_year_return` | YCP("SPXU","one_year_return") |
| 1 Year Price Returns (Monthly) | `one_year_monthly_return` | YCP("SPXU","one_year_monthly_return") |
| 1 Year Price Returns (Quarterly) | `one_year_quarterly_return` | YCP("SPXU","one_year_quarterly_return") |
| 1 Year Total Returns (Annual) | `one_year_total_annual_return` | YCP("SPXU","one_year_total_annual_return") |
| 1 Year Total Returns (Daily) | `one_year_total_return` | YCP("SPXU","one_year_total_return") |
| 1 Year Total Returns (Monthly) | `one_year_total_monthly_return` | YCP("SPXU","one_year_total_monthly_return") |
| 1 Year Total Returns (Quarterly) | `one_year_quarterly_total_return` | YCP("SPXU","one_year_quarterly_total_return") |
| 10 Day NAV Returns (Daily) | `roc_10_nav` | YCP("SPXU","roc_10_nav") |
| 10 Day Returns (Daily) | `roc_10` | YCP("SPXU","roc_10") |
| 10 Year Price Returns (Annual) | `ten_year_annual_return` | YCP("SPXU","ten_year_annual_return") |
| 10 Year Price Returns (Daily) | `ten_year_return` | YCP("SPXU","ten_year_return") |
| 10 Year Price Returns (Monthly) | `ten_year_monthly_return` | YCP("SPXU","ten_year_monthly_return") |
| 10 Year Price Returns (Quarterly) | `ten_year_quarterly_return` | YCP("SPXU","ten_year_quarterly_return") |
| 10 Year Total Returns (Annual) | `ten_year_total_annual_return` | YCP("SPXU","ten_year_total_annual_return") |
| 10 Year Total Returns (Daily) | `ten_year_total_return` | YCP("SPXU","ten_year_total_return") |
| 10 Year Total Returns (Monthly) | `ten_year_total_monthly_return` | YCP("SPXU","ten_year_total_monthly_return") |
| 10 Year Total Returns (Quarterly) | `ten_year_quarterly_total_return` | YCP("SPXU","ten_year_quarterly_total_return") |
| 12 Day NAV Returns (Daily) | `roc_12_nav` | YCP("SPXU","roc_12_nav") |
| 12 Day Returns (Daily) | `roc_12` | YCP("SPXU","roc_12") |
| 15 Year Price Returns (Annual) | `fifteen_year_annual_return` | YCP("SPXU","fifteen_year_annual_return") |
| 15 Year Price Returns (Daily) | `fifteen_year_return` | YCP("SPXU","fifteen_year_return") |
| 15 Year Price Returns (Monthly) | `fifteen_year_monthly_return` | YCP("SPXU","fifteen_year_monthly_return") |
| 15 Year Price Returns (Quarterly) | `fifteen_year_quarterly_return` | YCP("SPXU","fifteen_year_quarterly_return") |
| 15 Year Total Returns (Annual) | `fifteen_year_total_annual_return` | YCP("SPXU","fifteen_year_total_annual_return") |
| 15 Year Total Returns (Daily) | `fifteen_year_total_return` | YCP("SPXU","fifteen_year_total_return") |
| 15 Year Total Returns (Monthly) | `fifteen_year_total_monthly_return` | YCP("SPXU","fifteen_year_total_monthly_return") |
| 15 Year Total Returns (Quarterly) | `fifteen_year_quarterly_total_return` | YCP("SPXU","fifteen_year_quarterly_total_return") |
| 20 Day NAV Returns (Daily) | `roc_20_nav` | YCP("SPXU","roc_20_nav") |
| 20 Day Returns (Daily) | `roc_20` | YCP("SPXU","roc_20") |
| 20 Year Price Returns (Annual) | `twenty_year_annual_return` | YCP("SPXU","twenty_year_annual_return") |
| 20 Year Price Returns (Daily) | `twenty_year_return` | YCP("SPXU","twenty_year_return") |
| 20 Year Price Returns (Monthly) | `twenty_year_monthly_return` | YCP("SPXU","twenty_year_monthly_return") |
| 20 Year Total Returns (Annual) | `twenty_year_total_annual_return` | YCP("SPXU","twenty_year_total_annual_return") |
| 20 Year Total Returns (Daily) | `twenty_year_total_return` | YCP("SPXU","twenty_year_total_return") |
| 20 Year Total Returns (Monthly) | `twenty_year_total_monthly_return` | YCP("SPXU","twenty_year_total_monthly_return") |
| 3 Day NAV Returns (Daily) | `roc_3_nav` | YCP("SPXU","roc_3_nav") |
| 3 Day Returns (Daily) | `roc_3` | YCP("SPXU","roc_3") |
| 3 Month Price Returns (Daily) | `three_month_return` | YCP("SPXU","three_month_return") |
| 3 Month Price Returns (Monthly) | `three_monthly_return` | YCP("SPXU","three_monthly_return") |
| 3 Month Price Returns (Quarterly) | `quarterly_return` | YCP("SPXU","quarterly_return") |
| 3 Month Total Returns (Daily) | `three_month_total_return` | YCP("SPXU","three_month_total_return") |
| 3 Month Total Returns (Monthly) | `three_total_monthly_return` | YCP("SPXU","three_total_monthly_return") |
| 3 Month Total Returns (Quarterly) | `quarterly_total_return` | YCP("SPXU","quarterly_total_return") |
| 3 Year Price Returns (Annual) | `three_year_annual_return` | YCP("SPXU","three_year_annual_return") |
| 3 Year Price Returns (Daily) | `three_year_return` | YCP("SPXU","three_year_return") |
| 3 Year Price Returns (Monthly) | `three_year_monthly_return` | YCP("SPXU","three_year_monthly_return") |
| 3 Year Price Returns (Quarterly) | `three_year_quarterly_return` | YCP("SPXU","three_year_quarterly_return") |
| 3 Year Total Returns (Annual) | `three_year_total_annual_return` | YCP("SPXU","three_year_total_annual_return") |
| 3 Year Total Returns (Daily) | `three_year_total_return` | YCP("SPXU","three_year_total_return") |
| 3 Year Total Returns (Monthly) | `three_year_total_monthly_return` | YCP("SPXU","three_year_total_monthly_return") |
| 3 Year Total Returns (Quarterly) | `three_year_quarterly_total_return` | YCP("SPXU","three_year_quarterly_total_return") |
| 5 Day NAV Returns (Daily) | `roc_5_nav` | YCP("SPXU","roc_5_nav") |
| 5 Day Returns (Daily) | `roc_5` | YCP("SPXU","roc_5") |
| 5 Year Price Returns (Annual) | `five_year_annual_return` | YCP("SPXU","five_year_annual_return") |
| 5 Year Price Returns (Daily) | `five_year_return` | YCP("SPXU","five_year_return") |
| 5 Year Price Returns (Monthly) | `five_year_monthly_return` | YCP("SPXU","five_year_monthly_return") |
| 5 Year Price Returns (Quarterly) | `five_year_quarterly_return` | YCP("SPXU","five_year_quarterly_return") |
| 5 Year Total Returns (Annual) | `five_year_total_annual_return` | YCP("SPXU","five_year_total_annual_return") |
| 5 Year Total Returns (Daily) | `five_year_total_return` | YCP("SPXU","five_year_total_return") |
| 5 Year Total Returns (Monthly) | `five_year_total_monthly_return` | YCP("SPXU","five_year_total_monthly_return") |
| 5 Year Total Returns (Quarterly) | `five_year_quarterly_total_return` | YCP("SPXU","five_year_quarterly_total_return") |
| 6 Month Price Returns (Daily) | `six_month_return` | YCP("SPXU","six_month_return") |
| 6 Month Price Returns (Monthly) | `six_monthly_return` | YCP("SPXU","six_monthly_return") |
| 6 Month Total Returns (Daily) | `six_month_total_return` | YCP("SPXU","six_month_total_return") |
| 6 Month Total Returns (Monthly) | `six_total_monthly_return` | YCP("SPXU","six_total_monthly_return") |
| 7 Year Price Returns (Annual) | `seven_year_annual_return` | YCP("SPXU","seven_year_annual_return") |
| 7 Year Price Returns (Daily) | `seven_year_return` | YCP("SPXU","seven_year_return") |
| 7 Year Price Returns (Monthly) | `seven_year_monthly_return` | YCP("SPXU","seven_year_monthly_return") |
| 7 Year Total Returns (Annual) | `seven_year_total_annual_return` | YCP("SPXU","seven_year_total_annual_return") |
| 7 Year Total Returns (Daily) | `seven_year_total_return` | YCP("SPXU","seven_year_total_return") |
| 7 Year Total Returns (Monthly) | `seven_year_total_monthly_return` | YCP("SPXU","seven_year_total_monthly_return") |
| 9 Month Price Returns (Monthly) | `nine_monthly_return` | YCP("SPXU","nine_monthly_return") |
| 9 Month Total Returns (Monthly) | `nine_total_monthly_return` | YCP("SPXU","nine_total_monthly_return") |
| Annualized 1 Month Price Returns (Daily) | `annualized_daily_one_month_return` | YCP("SPXU","annualized_daily_one_month_return") |
| Annualized 1 Month Price Returns (Monthly) | `annualized_one_month_return` | YCP("SPXU","annualized_one_month_return") |
| Annualized 1 Month Total Returns (Daily) | `annualized_daily_one_month_total_return` | YCP("SPXU","annualized_daily_one_month_total_return") |
| Annualized 1 Month Total Returns (Monthly) | `annualized_one_month_total_return` | YCP("SPXU","annualized_one_month_total_return") |
| Annualized 1 Year Price Returns (Daily) | `annualized_daily_one_year_return` | YCP("SPXU","annualized_daily_one_year_return") |
| Annualized 1 Year Price Returns (Monthly) | `annualized_one_year_return` | YCP("SPXU","annualized_one_year_return") |
| Annualized 1 Year Total Returns (Daily) | `annualized_daily_one_year_total_return` | YCP("SPXU","annualized_daily_one_year_total_return") |
| Annualized 1 Year Total Returns (Monthly) | `annualized_one_year_total_return` | YCP("SPXU","annualized_one_year_total_return") |
| Annualized 10 Year Price Returns (Daily) | `annualized_daily_ten_year_return` | YCP("SPXU","annualized_daily_ten_year_return") |
| Annualized 10 Year Price Returns (Monthly) | `annualized_ten_year_return` | YCP("SPXU","annualized_ten_year_return") |
| Annualized 10 Year Price Returns (Quarterly) | `annualized_ten_year_quarterly_return` | YCP("SPXU","annualized_ten_year_quarterly_return") |
| Annualized 10 Year Total Returns (Daily) | `annualized_daily_ten_year_total_return` | YCP("SPXU","annualized_daily_ten_year_total_return") |
| Annualized 10 Year Total Returns (Monthly) | `annualized_ten_year_total_return` | YCP("SPXU","annualized_ten_year_total_return") |
| Annualized 10 Year Total Returns (Quarterly) | `annualized_ten_year_quarterly_total_return` | YCP("SPXU","annualized_ten_year_quarterly_total_return") |
| Annualized 15 Year Price Returns (Daily) | `annualized_daily_fifteen_year_return` | YCP("SPXU","annualized_daily_fifteen_year_return") |
| Annualized 15 Year Price Returns (Monthly) | `annualized_fifteen_year_return` | YCP("SPXU","annualized_fifteen_year_return") |
| Annualized 15 Year Price Returns (Quarterly) | `annualized_fifteen_year_quarterly_return` | YCP("SPXU","annualized_fifteen_year_quarterly_return") |
| Annualized 15 Year Total Returns (Daily) | `annualized_daily_fifteen_year_total_return` | YCP("SPXU","annualized_daily_fifteen_year_total_return") |
| Annualized 15 Year Total Returns (Monthly) | `annualized_fifteen_year_total_return` | YCP("SPXU","annualized_fifteen_year_total_return") |
| Annualized 15 Year Total Returns (Quarterly) | `annualized_fifteen_year_quarterly_total_return` | YCP("SPXU","annualized_fifteen_year_quarterly_total_return") |
| Annualized 20 Year Price Returns (Daily) | `annualized_daily_twenty_year_return` | YCP("SPXU","annualized_daily_twenty_year_return") |
| Annualized 20 Year Price Returns (Monthly) | `annualized_twenty_year_return` | YCP("SPXU","annualized_twenty_year_return") |
| Annualized 20 Year Total Returns (Daily) | `annualized_daily_twenty_year_total_return` | YCP("SPXU","annualized_daily_twenty_year_total_return") |
| Annualized 20 Year Total Returns (Monthly) | `annualized_twenty_year_total_return` | YCP("SPXU","annualized_twenty_year_total_return") |
| Annualized 3 Month Price Returns (Daily) | `annualized_daily_three_month_return` | YCP("SPXU","annualized_daily_three_month_return") |
| Annualized 3 Month Price Returns (Monthly) | `annualized_three_month_return` | YCP("SPXU","annualized_three_month_return") |
| Annualized 3 Month Total Returns (Daily) | `annualized_daily_three_month_total_return` | YCP("SPXU","annualized_daily_three_month_total_return") |
| Annualized 3 Month Total Returns (Monthly) | `annualized_three_month_total_return` | YCP("SPXU","annualized_three_month_total_return") |
| Annualized 3 Year Price Returns (Daily) | `annualized_daily_three_year_return` | YCP("SPXU","annualized_daily_three_year_return") |
| Annualized 3 Year Price Returns (Monthly) | `annualized_three_year_return` | YCP("SPXU","annualized_three_year_return") |
| Annualized 3 Year Price Returns (Quarterly) | `annualized_three_year_quarterly_return` | YCP("SPXU","annualized_three_year_quarterly_return") |
| Annualized 3 Year Total Returns (Daily) | `annualized_daily_three_year_total_return` | YCP("SPXU","annualized_daily_three_year_total_return") |
| Annualized 3 Year Total Returns (Monthly) | `annualized_three_year_total_return` | YCP("SPXU","annualized_three_year_total_return") |
| Annualized 3 Year Total Returns (Quarterly) | `annualized_three_year_quarterly_total_return` | YCP("SPXU","annualized_three_year_quarterly_total_return") |
| Annualized 5 Year Price Returns (Daily) | `annualized_daily_five_year_return` | YCP("SPXU","annualized_daily_five_year_return") |
| Annualized 5 Year Price Returns (Monthly) | `annualized_five_year_return` | YCP("SPXU","annualized_five_year_return") |
| Annualized 5 Year Price Returns (Quarterly) | `annualized_five_year_quarterly_return` | YCP("SPXU","annualized_five_year_quarterly_return") |
| Annualized 5 Year Total Returns (Daily) | `annualized_daily_five_year_total_return` | YCP("SPXU","annualized_daily_five_year_total_return") |
| Annualized 5 Year Total Returns (Monthly) | `annualized_five_year_total_return` | YCP("SPXU","annualized_five_year_total_return") |
| Annualized 5 Year Total Returns (Quarterly) | `annualized_five_year_quarterly_total_return` | YCP("SPXU","annualized_five_year_quarterly_total_return") |
| Annualized 6 Month Price Returns (Daily) | `annualized_daily_six_month_return` | YCP("SPXU","annualized_daily_six_month_return") |
| Annualized 6 Month Price Returns (Monthly) | `annualized_six_month_return` | YCP("SPXU","annualized_six_month_return") |
| Annualized 6 Month Total Returns (Daily) | `annualized_daily_six_month_total_return` | YCP("SPXU","annualized_daily_six_month_total_return") |
| Annualized 6 Month Total Returns (Monthly) | `annualized_six_month_total_return` | YCP("SPXU","annualized_six_month_total_return") |
| Annualized 7 Year Price Returns (Daily) | `annualized_daily_seven_year_return` | YCP("SPXU","annualized_daily_seven_year_return") |
| Annualized 7 Year Price Returns (Monthly) | `annualized_seven_year_return` | YCP("SPXU","annualized_seven_year_return") |
| Annualized 7 Year Total Returns (Daily) | `annualized_daily_seven_year_total_return` | YCP("SPXU","annualized_daily_seven_year_total_return") |
| Annualized 7 Year Total Returns (Monthly) | `annualized_seven_year_total_return` | YCP("SPXU","annualized_seven_year_total_return") |
| Annualized 9 Month Price Returns (Daily) | `annualized_daily_nine_month_return` | YCP("SPXU","annualized_daily_nine_month_return") |
| Annualized 9 Month Price Returns (Monthly) | `annualized_nine_month_return` | YCP("SPXU","annualized_nine_month_return") |
| Annualized 9 Month Total Returns (Daily) | `annualized_daily_nine_month_total_return` | YCP("SPXU","annualized_daily_nine_month_total_return") |
| Annualized 9 Month Total Returns (Monthly) | `annualized_nine_month_total_return` | YCP("SPXU","annualized_nine_month_total_return") |
| Annualized Price Returns Since Inception (Daily) | `annualized_daily_all_time_return` | YCP("SPXU","annualized_daily_all_time_return") |
| Annualized Price Returns Since Inception (Monthly) | `annualized_all_time_return` | YCP("SPXU","annualized_all_time_return") |
| Annualized Price Returns Since Inception (Quarterly) | `annualized_all_time_quarterly_return` | YCP("SPXU","annualized_all_time_quarterly_return") |
| Annualized Total Returns Since Inception (Daily) | `annualized_daily_all_time_total_return` | YCP("SPXU","annualized_daily_all_time_total_return") |
| Annualized Total Returns Since Inception (Monthly) | `annualized_all_time_total_return` | YCP("SPXU","annualized_all_time_total_return") |
| Annualized Total Returns Since Inception (Quarterly) | `annualized_all_time_quarterly_total_return` | YCP("SPXU","annualized_all_time_quarterly_total_return") |
| CAPM Expected Return | `capm_expected_return` | YCP("SPXU","capm_expected_return") |
| Month to Date Price Returns (Daily) | `mtd_return` | YCP("SPXU","mtd_return") |
| Month to Date Total Returns (Daily) | `mtd_total_return` | YCP("SPXU","mtd_total_return") |
| Price Returns Since Inception (Annual) | `all_time_annual_return` | YCP("SPXU","all_time_annual_return") |
| Price Returns Since Inception (Daily) | `all_time_return` | YCP("SPXU","all_time_return") |
| Price Returns Since Inception (Monthly) | `all_time_monthly_return` | YCP("SPXU","all_time_monthly_return") |
| Price Returns Since Inception (Quarterly) | `all_time_quarterly_return` | YCP("SPXU","all_time_quarterly_return") |
| Quarter to Date Price Returns (Daily) | `qtd_return` | YCP("SPXU","qtd_return") |
| Quarter to Date Price Returns (Monthly) | `qtd_monthly_return` | YCP("SPXU","qtd_monthly_return") |
| Quarter to Date Total Returns (Daily) | `qtd_total_return` | YCP("SPXU","qtd_total_return") |
| Quarter to Date Total Returns (Monthly) | `qtd_total_monthly_return` | YCP("SPXU","qtd_total_monthly_return") |
| Total Returns Since Inception (Annual) | `all_time_total_annual_return` | YCP("SPXU","all_time_total_annual_return") |
| Total Returns Since Inception (Daily) | `all_time_total_return` | YCP("SPXU","all_time_total_return") |
| Total Returns Since Inception (Monthly) | `all_time_total_monthly_return` | YCP("SPXU","all_time_total_monthly_return") |
| Total Returns Since Inception (Quarterly) | `all_time_quarterly_total_return` | YCP("SPXU","all_time_quarterly_total_return") |
| Year to Date Price Returns (Daily) | `ytd_return` | YCP("SPXU","ytd_return") |
| Year to Date Price Returns (Monthly) | `ytd_monthly_return` | YCP("SPXU","ytd_monthly_return") |
| Year to Date Total Returns (Daily) | `ytd_total_return` | YCP("SPXU","ytd_total_return") |
| Year to Date Total Returns (Monthly) | `ytd_total_monthly_return` | YCP("SPXU","ytd_total_monthly_return") |

---

## 4. Price Returns, Mutual Funds

| Metric | Code | Example |
|---|---|---|
| 1 Day NAV Returns (Daily) | `roc_1_nav` | YCP("M:AWSHX","roc_1_nav") |
| 1 Day Returns (Daily Close) | `roc_1_close` | YCP("M:AWSHX","roc_1_close") |
| 1 Day Returns (Daily) | `roc_1` | YCP("M:AWSHX","roc_1") |
| 1 Month Price Returns (Daily) | `one_month_return` | YCP("M:AWSHX","one_month_return") |
| 1 Month Price Returns (Monthly) | `monthly_return` | YCP("M:AWSHX","monthly_return") |
| 1 Month Total Returns (Daily) | `one_month_total_return` | YCP("M:AWSHX","one_month_total_return") |
| 1 Month Total Returns (Monthly) | `total_monthly_return` | YCP("M:AWSHX","total_monthly_return") |
| 1 Week Price Returns (Daily) | `one_week_return` | YCP("M:AWSHX","one_week_return") |
| 1 Week Total Returns (Daily) | `one_week_total_return` | YCP("M:AWSHX","one_week_total_return") |
| 1 Year Price Returns (Annual) | `one_year_annual_return` | YCP("M:AWSHX","one_year_annual_return") |
| 1 Year Price Returns (Daily) | `one_year_return` | YCP("M:AWSHX","one_year_return") |
| 1 Year Price Returns (Monthly) | `one_year_monthly_return` | YCP("M:AWSHX","one_year_monthly_return") |
| 1 Year Price Returns (Quarterly) | `one_year_quarterly_return` | YCP("M:AWSHX","one_year_quarterly_return") |
| 1 Year Total Returns (Annual) | `one_year_total_annual_return` | YCP("M:AWSHX","one_year_total_annual_return") |
| 1 Year Total Returns (Daily) | `one_year_total_return` | YCP("M:AWSHX","one_year_total_return") |
| 1 Year Total Returns (Monthly) | `one_year_total_monthly_return` | YCP("M:AWSHX","one_year_total_monthly_return") |
| 1 Year Total Returns (Quarterly) | `one_year_quarterly_total_return` | YCP("M:AWSHX","one_year_quarterly_total_return") |
| 10 Day NAV Returns (Daily) | `roc_10_nav` | YCP("M:AWSHX","roc_10_nav") |
| 10 Day Returns (Daily) | `roc_10` | YCP("M:AWSHX","roc_10") |
| 10 Year Price Returns (Annual) | `ten_year_annual_return` | YCP("M:AWSHX","ten_year_annual_return") |
| 10 Year Price Returns (Daily) | `ten_year_return` | YCP("M:AWSHX","ten_year_return") |
| 10 Year Price Returns (Monthly) | `ten_year_monthly_return` | YCP("M:AWSHX","ten_year_monthly_return") |
| 10 Year Price Returns (Quarterly) | `ten_year_quarterly_return` | YCP("M:AWSHX","ten_year_quarterly_return") |
| 10 Year Total Returns (Annual) | `ten_year_total_annual_return` | YCP("M:AWSHX","ten_year_total_annual_return") |
| 10 Year Total Returns (Daily) | `ten_year_total_return` | YCP("M:AWSHX","ten_year_total_return") |
| 10 Year Total Returns (Monthly) | `ten_year_total_monthly_return` | YCP("M:AWSHX","ten_year_total_monthly_return") |
| 10 Year Total Returns (Quarterly) | `ten_year_quarterly_total_return` | YCP("M:AWSHX","ten_year_quarterly_total_return") |
| 12 Day NAV Returns (Daily) | `roc_12_nav` | YCP("M:AWSHX","roc_12_nav") |
| 12 Day Returns (Daily) | `roc_12` | YCP("M:AWSHX","roc_12") |
| 15 Year Price Returns (Annual) | `fifteen_year_annual_return` | YCP("M:AWSHX","fifteen_year_annual_return") |
| 15 Year Price Returns (Daily) | `fifteen_year_return` | YCP("M:AWSHX","fifteen_year_return") |
| 15 Year Price Returns (Monthly) | `fifteen_year_monthly_return` | YCP("M:AWSHX","fifteen_year_monthly_return") |
| 15 Year Price Returns (Quarterly) | `fifteen_year_quarterly_return` | YCP("M:AWSHX","fifteen_year_quarterly_return") |
| 15 Year Total Returns (Annual) | `fifteen_year_total_annual_return` | YCP("M:AWSHX","fifteen_year_total_annual_return") |
| 15 Year Total Returns (Daily) | `fifteen_year_total_return` | YCP("M:AWSHX","fifteen_year_total_return") |
| 15 Year Total Returns (Monthly) | `fifteen_year_total_monthly_return` | YCP("M:AWSHX","fifteen_year_total_monthly_return") |
| 15 Year Total Returns (Quarterly) | `fifteen_year_quarterly_total_return` | YCP("M:AWSHX","fifteen_year_quarterly_total_return") |
| 20 Day NAV Returns (Daily) | `roc_20_nav` | YCP("M:AWSHX","roc_20_nav") |
| 20 Day Returns (Daily) | `roc_20` | YCP("M:AWSHX","roc_20") |
| 20 Year Price Returns (Annual) | `twenty_year_annual_return` | YCP("M:AWSHX","twenty_year_annual_return") |
| 20 Year Price Returns (Daily) | `twenty_year_return` | YCP("M:AWSHX","twenty_year_return") |
| 20 Year Price Returns (Monthly) | `twenty_year_monthly_return` | YCP("M:AWSHX","twenty_year_monthly_return") |
| 20 Year Total Returns (Annual) | `twenty_year_total_annual_return` | YCP("M:AWSHX","twenty_year_total_annual_return") |
| 20 Year Total Returns (Daily) | `twenty_year_total_return` | YCP("M:AWSHX","twenty_year_total_return") |
| 20 Year Total Returns (Monthly) | `twenty_year_total_monthly_return` | YCP("M:AWSHX","twenty_year_total_monthly_return") |
| 3 Day NAV Returns (Daily) | `roc_3_nav` | YCP("M:AWSHX","roc_3_nav") |
| 3 Day Returns (Daily) | `roc_3` | YCP("M:AWSHX","roc_3") |
| 3 Month Price Returns (Daily) | `three_month_return` | YCP("M:AWSHX","three_month_return") |
| 3 Month Price Returns (Monthly) | `three_monthly_return` | YCP("M:AWSHX","three_monthly_return") |
| 3 Month Price Returns (Quarterly) | `quarterly_return` | YCP("M:AWSHX","quarterly_return") |
| 3 Month Total Returns (Daily) | `three_month_total_return` | YCP("M:AWSHX","three_month_total_return") |
| 3 Month Total Returns (Monthly) | `three_total_monthly_return` | YCP("M:AWSHX","three_total_monthly_return") |
| 3 Month Total Returns (Quarterly) | `quarterly_total_return` | YCP("M:AWSHX","quarterly_total_return") |
| 3 Year Price Returns (Annual) | `three_year_annual_return` | YCP("M:AWSHX","three_year_annual_return") |
| 3 Year Price Returns (Daily) | `three_year_return` | YCP("M:AWSHX","three_year_return") |
| 3 Year Price Returns (Monthly) | `three_year_monthly_return` | YCP("M:AWSHX","three_year_monthly_return") |
| 3 Year Price Returns (Quarterly) | `three_year_quarterly_return` | YCP("M:AWSHX","three_year_quarterly_return") |
| 3 Year Total Returns (Annual) | `three_year_total_annual_return` | YCP("M:AWSHX","three_year_total_annual_return") |
| 3 Year Total Returns (Daily) | `three_year_total_return` | YCP("M:AWSHX","three_year_total_return") |
| 3 Year Total Returns (Monthly) | `three_year_total_monthly_return` | YCP("M:AWSHX","three_year_total_monthly_return") |
| 3 Year Total Returns (Quarterly) | `three_year_quarterly_total_return` | YCP("M:AWSHX","three_year_quarterly_total_return") |
| 5 Day NAV Returns (Daily) | `roc_5_nav` | YCP("M:AWSHX","roc_5_nav") |
| 5 Day Returns (Daily) | `roc_5` | YCP("M:AWSHX","roc_5") |
| 5 Year Price Returns (Annual) | `five_year_annual_return` | YCP("M:AWSHX","five_year_annual_return") |
| 5 Year Price Returns (Daily) | `five_year_return` | YCP("M:AWSHX","five_year_return") |
| 5 Year Price Returns (Monthly) | `five_year_monthly_return` | YCP("M:AWSHX","five_year_monthly_return") |
| 5 Year Price Returns (Quarterly) | `five_year_quarterly_return` | YCP("M:AWSHX","five_year_quarterly_return") |
| 5 Year Total Returns (Annual) | `five_year_total_annual_return` | YCP("M:AWSHX","five_year_total_annual_return") |
| 5 Year Total Returns (Daily) | `five_year_total_return` | YCP("M:AWSHX","five_year_total_return") |
| 5 Year Total Returns (Monthly) | `five_year_total_monthly_return` | YCP("M:AWSHX","five_year_total_monthly_return") |
| 5 Year Total Returns (Quarterly) | `five_year_quarterly_total_return` | YCP("M:AWSHX","five_year_quarterly_total_return") |
| 6 Month Price Returns (Daily) | `six_month_return` | YCP("M:AWSHX","six_month_return") |
| 6 Month Price Returns (Monthly) | `six_monthly_return` | YCP("M:AWSHX","six_monthly_return") |
| 6 Month Total Returns (Daily) | `six_month_total_return` | YCP("M:AWSHX","six_month_total_return") |
| 6 Month Total Returns (Monthly) | `six_total_monthly_return` | YCP("M:AWSHX","six_total_monthly_return") |
| 7 Year Price Returns (Annual) | `seven_year_annual_return` | YCP("M:AWSHX","seven_year_annual_return") |
| 7 Year Price Returns (Daily) | `seven_year_return` | YCP("M:AWSHX","seven_year_return") |
| 7 Year Price Returns (Monthly) | `seven_year_monthly_return` | YCP("M:AWSHX","seven_year_monthly_return") |
| 7 Year Total Returns (Annual) | `seven_year_total_annual_return` | YCP("M:AWSHX","seven_year_total_annual_return") |
| 7 Year Total Returns (Daily) | `seven_year_total_return` | YCP("M:AWSHX","seven_year_total_return") |
| 7 Year Total Returns (Monthly) | `seven_year_total_monthly_return` | YCP("M:AWSHX","seven_year_total_monthly_return") |
| 9 Month Price Returns (Monthly) | `nine_monthly_return` | YCP("M:AWSHX","nine_monthly_return") |
| 9 Month Total Returns (Monthly) | `nine_total_monthly_return` | YCP("M:AWSHX","nine_total_monthly_return") |
| Annualized 1 Month Price Returns (Daily) | `annualized_daily_one_month_return` | YCP("M:AWSHX","annualized_daily_one_month_return") |
| Annualized 1 Month Price Returns (Monthly) | `annualized_one_month_return` | YCP("M:AWSHX","annualized_one_month_return") |
| Annualized 1 Month Total Returns (Daily) | `annualized_daily_one_month_total_return` | YCP("M:AWSHX","annualized_daily_one_month_total_return") |
| Annualized 1 Month Total Returns (Monthly) | `annualized_one_month_total_return` | YCP("M:AWSHX","annualized_one_month_total_return") |
| Annualized 1 Year Price Returns (Daily) | `annualized_daily_one_year_return` | YCP("M:AWSHX","annualized_daily_one_year_return") |
| Annualized 1 Year Price Returns (Monthly) | `annualized_one_year_return` | YCP("M:AWSHX","annualized_one_year_return") |
| Annualized 1 Year Total Returns (Daily) | `annualized_daily_one_year_total_return` | YCP("M:AWSHX","annualized_daily_one_year_total_return") |
| Annualized 1 Year Total Returns (Monthly) | `annualized_one_year_total_return` | YCP("M:AWSHX","annualized_one_year_total_return") |
| Annualized 10 Year Price Returns (Daily) | `annualized_daily_ten_year_return` | YCP("M:AWSHX","annualized_daily_ten_year_return") |
| Annualized 10 Year Price Returns (Monthly) | `annualized_ten_year_return` | YCP("M:AWSHX","annualized_ten_year_return") |
| Annualized 10 Year Price Returns (Quarterly) | `annualized_ten_year_quarterly_return` | YCP("M:AWSHX","annualized_ten_year_quarterly_return") |
| Annualized 10 Year Total Returns (Daily) | `annualized_daily_ten_year_total_return` | YCP("M:AWSHX","annualized_daily_ten_year_total_return") |
| Annualized 10 Year Total Returns (Monthly) | `annualized_ten_year_total_return` | YCP("M:AWSHX","annualized_ten_year_total_return") |
| Annualized 10 Year Total Returns (Quarterly) | `annualized_ten_year_quarterly_total_return` | YCP("M:AWSHX","annualized_ten_year_quarterly_total_return") |
| Annualized 15 Year Price Returns (Daily) | `annualized_daily_fifteen_year_return` | YCP("M:AWSHX","annualized_daily_fifteen_year_return") |
| Annualized 15 Year Price Returns (Monthly) | `annualized_fifteen_year_return` | YCP("M:AWSHX","annualized_fifteen_year_return") |
| Annualized 15 Year Price Returns (Quarterly) | `annualized_fifteen_year_quarterly_return` | YCP("M:AWSHX","annualized_fifteen_year_quarterly_return") |
| Annualized 15 Year Total Returns (Daily) | `annualized_daily_fifteen_year_total_return` | YCP("M:AWSHX","annualized_daily_fifteen_year_total_return") |
| Annualized 15 Year Total Returns (Monthly) | `annualized_fifteen_year_total_return` | YCP("M:AWSHX","annualized_fifteen_year_total_return") |
| Annualized 15 Year Total Returns (Quarterly) | `annualized_fifteen_year_quarterly_total_return` | YCP("M:AWSHX","annualized_fifteen_year_quarterly_total_return") |
| Annualized 20 Year Price Returns (Daily) | `annualized_daily_twenty_year_return` | YCP("M:AWSHX","annualized_daily_twenty_year_return") |
| Annualized 20 Year Price Returns (Monthly) | `annualized_twenty_year_return` | YCP("M:AWSHX","annualized_twenty_year_return") |
| Annualized 20 Year Total Returns (Daily) | `annualized_daily_twenty_year_total_return` | YCP("M:AWSHX","annualized_daily_twenty_year_total_return") |
| Annualized 20 Year Total Returns (Monthly) | `annualized_twenty_year_total_return` | YCP("M:AWSHX","annualized_twenty_year_total_return") |
| Annualized 3 Month Price Returns (Daily) | `annualized_daily_three_month_return` | YCP("M:AWSHX","annualized_daily_three_month_return") |
| Annualized 3 Month Price Returns (Monthly) | `annualized_three_month_return` | YCP("M:AWSHX","annualized_three_month_return") |
| Annualized 3 Month Total Returns (Daily) | `annualized_daily_three_month_total_return` | YCP("M:AWSHX","annualized_daily_three_month_total_return") |
| Annualized 3 Month Total Returns (Monthly) | `annualized_three_month_total_return` | YCP("M:AWSHX","annualized_three_month_total_return") |
| Annualized 3 Year Price Returns (Daily) | `annualized_daily_three_year_return` | YCP("M:AWSHX","annualized_daily_three_year_return") |
| Annualized 3 Year Price Returns (Monthly) | `annualized_three_year_return` | YCP("M:AWSHX","annualized_three_year_return") |
| Annualized 3 Year Price Returns (Quarterly) | `annualized_three_year_quarterly_return` | YCP("M:AWSHX","annualized_three_year_quarterly_return") |
| Annualized 3 Year Total Returns (Daily) | `annualized_daily_three_year_total_return` | YCP("M:AWSHX","annualized_daily_three_year_total_return") |
| Annualized 3 Year Total Returns (Monthly) | `annualized_three_year_total_return` | YCP("M:AWSHX","annualized_three_year_total_return") |
| Annualized 3 Year Total Returns (Quarterly) | `annualized_three_year_quarterly_total_return` | YCP("M:AWSHX","annualized_three_year_quarterly_total_return") |
| Annualized 5 Year Price Returns (Daily) | `annualized_daily_five_year_return` | YCP("M:AWSHX","annualized_daily_five_year_return") |
| Annualized 5 Year Price Returns (Monthly) | `annualized_five_year_return` | YCP("M:AWSHX","annualized_five_year_return") |
| Annualized 5 Year Price Returns (Quarterly) | `annualized_five_year_quarterly_return` | YCP("M:AWSHX","annualized_five_year_quarterly_return") |
| Annualized 5 Year Total Returns (Daily) | `annualized_daily_five_year_total_return` | YCP("M:AWSHX","annualized_daily_five_year_total_return") |
| Annualized 5 Year Total Returns (Monthly) | `annualized_five_year_total_return` | YCP("M:AWSHX","annualized_five_year_total_return") |
| Annualized 5 Year Total Returns (Quarterly) | `annualized_five_year_quarterly_total_return` | YCP("M:AWSHX","annualized_five_year_quarterly_total_return") |
| Annualized 6 Month Price Returns (Daily) | `annualized_daily_six_month_return` | YCP("M:AWSHX","annualized_daily_six_month_return") |
| Annualized 6 Month Price Returns (Monthly) | `annualized_six_month_return` | YCP("M:AWSHX","annualized_six_month_return") |
| Annualized 6 Month Total Returns (Daily) | `annualized_daily_six_month_total_return` | YCP("M:AWSHX","annualized_daily_six_month_total_return") |
| Annualized 6 Month Total Returns (Monthly) | `annualized_six_month_total_return` | YCP("M:AWSHX","annualized_six_month_total_return") |
| Annualized 7 Year Price Returns (Daily) | `annualized_daily_seven_year_return` | YCP("M:AWSHX","annualized_daily_seven_year_return") |
| Annualized 7 Year Price Returns (Monthly) | `annualized_seven_year_return` | YCP("M:AWSHX","annualized_seven_year_return") |
| Annualized 7 Year Total Returns (Daily) | `annualized_daily_seven_year_total_return` | YCP("M:AWSHX","annualized_daily_seven_year_total_return") |
| Annualized 7 Year Total Returns (Monthly) | `annualized_seven_year_total_return` | YCP("M:AWSHX","annualized_seven_year_total_return") |
| Annualized 9 Month Price Returns (Daily) | `annualized_daily_nine_month_return` | YCP("M:AWSHX","annualized_daily_nine_month_return") |
| Annualized 9 Month Price Returns (Monthly) | `annualized_nine_month_return` | YCP("M:AWSHX","annualized_nine_month_return") |
| Annualized 9 Month Total Returns (Daily) | `annualized_daily_nine_month_total_return` | YCP("M:AWSHX","annualized_daily_nine_month_total_return") |
| Annualized 9 Month Total Returns (Monthly) | `annualized_nine_month_total_return` | YCP("M:AWSHX","annualized_nine_month_total_return") |
| Annualized Price Returns Since Inception (Daily) | `annualized_daily_all_time_return` | YCP("M:AWSHX","annualized_daily_all_time_return") |
| Annualized Price Returns Since Inception (Monthly) | `annualized_all_time_return` | YCP("M:AWSHX","annualized_all_time_return") |
| Annualized Price Returns Since Inception (Quarterly) | `annualized_all_time_quarterly_return` | YCP("M:AWSHX","annualized_all_time_quarterly_return") |
| Annualized Total Returns Since Inception (Daily) | `annualized_daily_all_time_total_return` | YCP("M:AWSHX","annualized_daily_all_time_total_return") |
| Annualized Total Returns Since Inception (Monthly) | `annualized_all_time_total_return` | YCP("M:AWSHX","annualized_all_time_total_return") |
| Annualized Total Returns Since Inception (Quarterly) | `annualized_all_time_quarterly_total_return` | YCP("M:AWSHX","annualized_all_time_quarterly_total_return") |
| CAPM Expected Return | `capm_expected_return` | YCP("M:AWSHX","capm_expected_return") |
| Month to Date Price Returns (Daily) | `mtd_return` | YCP("M:AWSHX","mtd_return") |
| Month to Date Total Returns (Daily) | `mtd_total_return` | YCP("M:AWSHX","mtd_total_return") |
| Price Returns Since Inception (Annual) | `all_time_annual_return` | YCP("M:AWSHX","all_time_annual_return") |
| Price Returns Since Inception (Daily) | `all_time_return` | YCP("M:AWSHX","all_time_return") |
| Price Returns Since Inception (Monthly) | `all_time_monthly_return` | YCP("M:AWSHX","all_time_monthly_return") |
| Price Returns Since Inception (Quarterly) | `all_time_quarterly_return` | YCP("M:AWSHX","all_time_quarterly_return") |
| Quarter to Date Price Returns (Daily) | `qtd_return` | YCP("M:AWSHX","qtd_return") |
| Quarter to Date Price Returns (Monthly) | `qtd_monthly_return` | YCP("M:AWSHX","qtd_monthly_return") |
| Quarter to Date Total Returns (Daily) | `qtd_total_return` | YCP("M:AWSHX","qtd_total_return") |
| Quarter to Date Total Returns (Monthly) | `qtd_total_monthly_return` | YCP("M:AWSHX","qtd_total_monthly_return") |
| Total Returns Since Inception (Annual) | `all_time_total_annual_return` | YCP("M:AWSHX","all_time_total_annual_return") |
| Total Returns Since Inception (Daily) | `all_time_total_return` | YCP("M:AWSHX","all_time_total_return") |
| Total Returns Since Inception (Monthly) | `all_time_total_monthly_return` | YCP("M:AWSHX","all_time_total_monthly_return") |
| Total Returns Since Inception (Quarterly) | `all_time_quarterly_total_return` | YCP("M:AWSHX","all_time_quarterly_total_return") |
| Year to Date Price Returns (Daily) | `ytd_return` | YCP("M:AWSHX","ytd_return") |
| Year to Date Price Returns (Monthly) | `ytd_monthly_return` | YCP("M:AWSHX","ytd_monthly_return") |
| Year to Date Total Returns (Daily) | `ytd_total_return` | YCP("M:AWSHX","ytd_total_return") |
| Year to Date Total Returns (Monthly) | `ytd_total_monthly_return` | YCP("M:AWSHX","ytd_total_monthly_return") |

---

## 5. Income Statement & Financial Metrics (Companies)

| Metric | Code | Example |
|---|---|---|
| Accelerated Depreciation (Annual) | `accel_dep_annual` | YCP("MSFT","accel_dep_annual") |
| Accelerated Depreciation (TTM) | `accel_dep_ttm` | YCP("MSFT","accel_dep_ttm") |
| Accounts Payable (Annual) | `accounts_payable_annual` | YCP("MSFT","accounts_payable_annual") |
| Accounts Receivable (Annual) | `accounts_receivable_annual` | YCP("MSFT","accounts_receivable_annual") |
| Accruals (Annual) | `accruals_annual` | YCP("MSFT","accruals_annual") |
| Accruals (TTM) | `accruals_ttm` | YCP("MSFT","accruals_ttm") |
| Accrued Expense - Increase/Decrease (Annual) | `accr_exp_cf_annual` | YCP("MSFT","accr_exp_cf_annual") |
| Accrued Expense - Increase/Decrease (TTM) | `accr_exp_cf_ttm` | YCP("MSFT","accr_exp_cf_ttm") |
| Accrued Payroll (Annual) | `accr_payr_annual` | YCP("MSFT","accr_payr_annual") |
| Accum. Depr. - Buildings (Annual) | `ppe_dep_bldg_annual` | YCP("MSFT","ppe_dep_bldg_annual") |
| Accum. Depr. - Comp Software and Equip (Annual) | `ppe_dep_soft_equip_annual` | YCP("MSFT","ppe_dep_soft_equip_annual") |
| Accum. Depr. - Construction in Progress (Annual) | `ppe_dep_constr_annual` | YCP("MSFT","ppe_dep_constr_annual") |
| Accum. Depr. - Land & Improvements (Annual) | `ppe_dep_land_annual` | YCP("MSFT","ppe_dep_land_annual") |
| Accum. Depr. - Leased Property (Annual) | `ppe_dep_leased_prop_annual` | YCP("MSFT","ppe_dep_leased_prop_annual") |
| Accum. Depr. - Leases (Annual) | `ppe_dep_leases_annual` | YCP("MSFT","ppe_dep_leases_annual") |
| Accum. Depr. - Machinery & Equip (Annual) | `ppe_dep_equip_annual` | YCP("MSFT","ppe_dep_equip_annual") |
| Accum. Depr. - Other Property, Plant, & Equip (Annual) | `ppe_dep_oth_annual` | YCP("MSFT","ppe_dep_oth_annual") |
| Accum. Depr. - Transportation Equip (Annual) | `ppe_dep_trans_equip_annual` | YCP("MSFT","ppe_dep_trans_equip_annual") |
| Accumulated D&A (Annual) | `total_accumulated_d_and_d_annual` | YCP("MSFT","total_accumulated_d_and_d_annual") |
| Accumulated Goodwill Amortization (Annual) | `gw_amort_annual` | YCP("MSFT","gw_amort_annual") |
| Acquired In-Process R&D (Annual) | `acq_process_rd_annual` | YCP("MSFT","acq_process_rd_annual") |
| Acquired In-Process R&D (TTM) | `acq_process_rd_ttm` | YCP("MSFT","acq_process_rd_ttm") |
| Additional Paid In Capital (Annual) | `additional_paid_in_capital_annual` | YCP("MSFT","additional_paid_in_capital_annual") |
| Altman Z Score (Annual) | `altman_z_score_annual` | YCP("MSFT","altman_z_score_annual") |
| Altman Z-Score - Nonmanufacturers (Annual) | `altman_z_score_nonmanu_annual` | YCP("MSFT","altman_z_score_nonmanu_annual") |
| Amortization Expense CF (Annual) | `amortization_cf_annual` | YCP("MSFT","amortization_cf_annual") |
| Amortization Expense CF (TTM) | `amortization_cf_ttm` | YCP("MSFT","amortization_cf_ttm") |
| Amortization Of Deferred Charges (Annual) | `amort_dfd_chrg_annual` | YCP("MSFT","amort_dfd_chrg_annual") |
| Amortization Of Deferred Charges (TTM) | `amort_dfd_chrg_ttm` | YCP("MSFT","amort_dfd_chrg_ttm") |
| Amortization of Intangibles (Annual) | `amortization_of_intangibles_annual` | YCP("MSFT","amortization_of_intangibles_annual") |
| Amortization of Intangibles (TTM) | `amortization_of_intangibles_ttm` | YCP("MSFT","amortization_of_intangibles_ttm") |
| Antidilutionary Stock Buyback (Annual) | `antidilutionary_stock_buyback_annual` | YCP("MSFT","antidilutionary_stock_buyback_annual") |
| Antidilutionary Stock Buyback (TTM) | `antidilutionary_stock_buyback_ttm` | YCP("MSFT","antidilutionary_stock_buyback_ttm") |
| Asset Utilization (Annual) | `asset_utilization_annual` | YCP("MSFT","asset_utilization_annual") |
| Asset Write Down (Annual) | `impair_annual` | YCP("MSFT","impair_annual") |
| Asset Write Down (TTM) | `impair_ttm` | YCP("MSFT","impair_ttm") |
| Assets - Other (Annual) | `assets_oth_annual` | YCP("MSFT","assets_oth_annual") |
| Assets Per Employee (Annual) | `assets_per_employee_annual` | YCP("MSFT","assets_per_employee_annual") |
| Assets To Shareholder Equity (Annual) | `assets_to_shareholder_equity_annual` | YCP("MSFT","assets_to_shareholder_equity_annual") |
| Average Basic Shares Outstanding (Annual) | `average_shares_outs_basic_annual` | YCP("MSFT","average_shares_outs_basic_annual") |
| Average Diluted Shares Outstanding (Annual) | `average_shares_outs_diluted_annual` | YCP("MSFT","average_shares_outs_diluted_annual") |
| Beginning Cash (Annual) | `beginning_cash_annual` | YCP("MSFT","beginning_cash_annual") |
| Benefit and Loss Reserves (Annual) | `ins_rsrv_annual` | YCP("MSFT","ins_rsrv_annual") |
| Bonds (Annual) | `invest_bonds_annual` | YCP("MSFT","invest_bonds_annual") |
| Bonds Below Investment Grade (Annual) | `bonds_below_invgr_annual` | YCP("MSFT","bonds_below_invgr_annual") |
| Book Value (Annual) | `book_value_of_equity_annual` | YCP("MSFT","book_value_of_equity_annual") |
| Book Value Per Share (Annual) | `bps_annual` | YCP("MSFT","bps_annual") |
| Broker & Financial Institution Loans (Annual) | `loan_brkr_annual` | YCP("MSFT","loan_brkr_annual") |
| Buildings and Improvements (Annual) | `buildings_and_improvements_annual` | YCP("MSFT","buildings_and_improvements_annual") |
| CA Score (Annual) | `ca_score_annual` | YCP("MSFT","ca_score_annual") |
| CAPEX To Revenue (TTM) | `capex_to_revenue_ttm` | YCP("MSFT","capex_to_revenue_ttm") |
| CAPEX to Revenue (Annual) | `capex_to_revenue_annual` | YCP("MSFT","capex_to_revenue_annual") |
| CFO Per Employee (Annual) | `cfo_per_employee_annual` | YCP("MSFT","cfo_per_employee_annual") |
| CFO Per Share (TTM) | `cfo_per_share_ttm` | YCP("MSFT","cfo_per_share_ttm") |
| CFO to Assets (Annual) | `cash_roa_annual` | YCP("MSFT","cash_roa_annual") |
| CFO to Assets (TTM) | `cash_roa_ttm` | YCP("MSFT","cash_roa_ttm") |
| CFO to Current Liabilities (Annual) | `cfo_current_liabilities_annual` | YCP("MSFT","cfo_current_liabilities_annual") |
| CFO to Debt (Annual) | `cfo_debt_annual` | YCP("MSFT","cfo_debt_annual") |
| COGS excl. Depr. & Amort. (Annual) | `cogs_xdep_annual` | YCP("MSFT","cogs_xdep_annual") |
| COGS excl. Depr. & Amort. (TTM) | `cogs_xdep_ttm` | YCP("MSFT","cogs_xdep_ttm") |
| Calamitous Event (Annual) | `calamitous_event_annual` | YCP("MSFT","calamitous_event_annual") |
| Calamitous Event (TTM) | `calamitous_event_ttm` | YCP("MSFT","calamitous_event_ttm") |
| Capital & Operating Lease Oblig (Annual) | `liabs_lease_annual` | YCP("MSFT","liabs_lease_annual") |
| Capital Employed (Annual) | `capital_employed_annual` | YCP("MSFT","capital_employed_annual") |
| Capital Expenditures (Annual) | `capex_annual` | YCP("MSFT","capex_annual") |
| Capital Expenditures (Fixed Assets) (Annual) | `capex_fix_annual` | YCP("MSFT","capex_fix_annual") |
| Capital Expenditures (Fixed Assets) (TTM) | `capex_fix_ttm` | YCP("MSFT","capex_fix_ttm") |
| Capital Expenditures (Other Assets) (Annual) | `capex_oth_annual` | YCP("MSFT","capex_oth_annual") |
| Capital Expenditures (Other Assets) (TTM) | `capex_oth_ttm` | YCP("MSFT","capex_oth_ttm") |
| Capital Expenditures (TTM) | `capex_ttm` | YCP("MSFT","capex_ttm") |
| Capital Expenditures - Total (Annual) | `ff_capex_annual` | YCP("MSFT","ff_capex_annual") |
| Capital Expenditures - Total (TTM) | `ff_capex_ttm` | YCP("MSFT","ff_capex_ttm") |
| Cash & Due From Banks (Annual) | `cash_due_fr_bk_annual` | YCP("MSFT","cash_due_fr_bk_annual") |
| Cash (Annual) | `cash_annual` | YCP("MSFT","cash_annual") |
| Cash Conversion Cycle (Annual) | `cash_conversion_cycle_annual` | YCP("MSFT","cash_conversion_cycle_annual") |
| Cash Dividend Payout Ratio (Annual) | `cash_dividend_payout_ratio_annual` | YCP("MSFT","cash_dividend_payout_ratio_annual") |
| Cash Equivalent To Market Cap (Annual) | `cash_equivalent_to_mktcap_annual` | YCP("MSFT","cash_equivalent_to_mktcap_annual") |
| Cash Flow Per Share (Diluted) - Free (Annual) | `free_ps_cf_annual` | YCP("MSFT","free_ps_cf_annual") |
| Cash Flow Per Share (Diluted) - Free (TTM) | `free_ps_cf_ttm` | YCP("MSFT","free_ps_cf_ttm") |
| Cash Flow To CAPEX (Annual) | `cash_flow_to_capex_annual` | YCP("MSFT","cash_flow_to_capex_annual") |
| Cash Flow to CAPEX (TTM) | `cash_flow_to_capex_ttm` | YCP("MSFT","cash_flow_to_capex_ttm") |
| Cash Foreign Exchange Adjustment (Annual) | `foreign_exch_rate_adjust_annual` | YCP("MSFT","foreign_exch_rate_adjust_annual") |
| Cash Only (Annual) | `cash_only_annual` | YCP("MSFT","cash_only_annual") |
| Cash Ratio (Annual) | `cash_ratio_annual` | YCP("MSFT","cash_ratio_annual") |
| Cash Return on Capital Invested (CROCI) (Annual) | `croic_annual` | YCP("MSFT","croic_annual") |
| Cash To Market Cap (Annual) | `cash_to_mktcap_annual` | YCP("MSFT","cash_to_mktcap_annual") |
| Cash Turnover (Annual) | `cash_turnover_annual` | YCP("MSFT","cash_turnover_annual") |
| Cash Turnover (TTM) | `cash_turnover_ttm` | YCP("MSFT","cash_turnover_ttm") |
| Cash and Equivalents (Annual) | `cash_and_equivalents_annual` | YCP("MSFT","cash_and_equivalents_annual") |
| Cash and Short Term Investments (Annual) | `cash_on_hand_annual` | YCP("MSFT","cash_on_hand_annual") |
| Cash from Financing (Annual) | `cash_financing_annual` | YCP("MSFT","cash_financing_annual") |
| Cash from Financing (TTM) | `cash_financing_ttm` | YCP("MSFT","cash_financing_ttm") |
| Cash from Investing (Annual) | `cash_investing_annual` | YCP("MSFT","cash_investing_annual") |
| Cash from Investing (TTM) | `cash_investing_ttm` | YCP("MSFT","cash_investing_ttm") |
| Cash from Operations (Annual) | `cash_operations_annual` | YCP("MSFT","cash_operations_annual") |
| Cash from Operations (TTM) | `cash_operations_ttm` | YCP("MSFT","cash_operations_ttm") |
| Change in Cash (Annual) | `increase_in_cash_annual` | YCP("MSFT","increase_in_cash_annual") |
| Change in Cash (TTM) | `increase_in_cash_ttm` | YCP("MSFT","increase_in_cash_ttm") |
| Change in Current Debt (Annual) | `debt_st_cf_annual` | YCP("MSFT","debt_st_cf_annual") |
| Change in Current Debt (TTM) | `debt_st_cf_ttm` | YCP("MSFT","debt_st_cf_ttm") |
| Change in Deposits (Annual) | `dep_chg_cf_annual` | YCP("MSFT","dep_chg_cf_annual") |
| Change in Deposits (TTM) | `dep_chg_cf_ttm` | YCP("MSFT","dep_chg_cf_ttm") |
| Change in Inventories (Annual) | `change_in_inventories_annual` | YCP("MSFT","change_in_inventories_annual") |
| Change in Inventories (TTM) | `change_in_inventories_ttm` | YCP("MSFT","change_in_inventories_ttm") |
| Change in Receivables (Annual) | `change_in_receivables_annual` | YCP("MSFT","change_in_receivables_annual") |
| Change in Receivables (TTM) | `change_in_receivables_ttm` | YCP("MSFT","change_in_receivables_ttm") |
| Change in Taxes Payable (Annual) | `change_in_income_taxes_annual` | YCP("MSFT","change_in_income_taxes_annual") |
| Change in Taxes Payable (TTM) | `change_in_income_taxes_ttm` | YCP("MSFT","change_in_income_taxes_ttm") |
| Changes in Working Capital (Annual) | `total_changes_in_assets_liab_annual` | YCP("MSFT","total_changes_in_assets_liab_annual") |
| Changes in Working Capital (TTM) | `total_changes_in_assets_liab_ttm` | YCP("MSFT","total_changes_in_assets_liab_ttm") |
| Commercial & Industrial Loans (Annual) | `loan_comml_indl_annual` | YCP("MSFT","loan_comml_indl_annual") |
| Commission And Fees (Annual) | `commiss_inc_annual` | YCP("MSFT","commiss_inc_annual") |
| Commission And Fees (TTM) | `commiss_inc_ttm` | YCP("MSFT","commiss_inc_ttm") |
| Common Equity (Annual) | `com_eq_annual` | YCP("MSFT","com_eq_annual") |
| Common Equity Tier 1 - Total (Annual) | `bk_com_eq_tier1_tot_annual` | YCP("MSFT","bk_com_eq_tier1_tot_annual") |
| Common Stocks (Annual) | `invest_com_eq_annual` | YCP("MSFT","invest_com_eq_annual") |
| Comprehensive Income - Hedging Gain/Loss (Annual) | `com_eq_hedg_gl_annual` | YCP("MSFT","com_eq_hedg_gl_annual") |
| Comprehensive Income - Unearned Comp (Annual) | `com_eq_unearn_comp_annual` | YCP("MSFT","com_eq_unearn_comp_annual") |
| Consumer and Installment Loans (Annual) | `loan_cons_annual` | YCP("MSFT","loan_cons_annual") |
| Cost of Goods Sold (Annual) | `cost_of_goods_sold_annual` | YCP("MSFT","cost_of_goods_sold_annual") |
| Cost of Goods Sold (TTM) | `cost_of_goods_sold_ttm` | YCP("MSFT","cost_of_goods_sold_ttm") |
| Cumulative Translation (Annual) | `com_eq_for_exch_annual` | YCP("MSFT","com_eq_for_exch_annual") |
| Current Assets, Other (Annual) | `assets_curr_oth_annual` | YCP("MSFT","assets_curr_oth_annual") |
| Current Deferred Tax Liability (Annual) | `deferred_tax_liability_current_annual` | YCP("MSFT","deferred_tax_liability_current_annual") |
| Current Portion of Long Term Debt (Annual) | `current_portion_debt_annual` | YCP("MSFT","current_portion_debt_annual") |
| Current Ratio (Annual) | `current_ratio_annual` | YCP("MSFT","current_ratio_annual") |
| Current Tax Payable (Annual) | `current_portion_taxes_payable_annual` | YCP("MSFT","current_portion_taxes_payable_annual") |
| Custody Securities (Annual) | `secs_custody_annual` | YCP("MSFT","secs_custody_annual") |
| Customer Liability On Acceptances (Assets) (Annual) | `cust_accept_annual` | YCP("MSFT","cust_accept_annual") |
| Days Inventory Outstanding (Annual) | `days_inventory_outstanding_annual` | YCP("MSFT","days_inventory_outstanding_annual") |
| Days Payables Outstanding (Annual) | `days_payables_outstanding_annual` | YCP("MSFT","days_payables_outstanding_annual") |
| Days Sales Outstanding (Annual) | `days_sales_outstanding_annual` | YCP("MSFT","days_sales_outstanding_annual") |
| Days of Payables Outstanding (Annual) | `pay_turn_days_annual` | YCP("MSFT","pay_turn_days_annual") |
| Debt To Assets (Annual) | `debt_to_assets_annual` | YCP("MSFT","debt_to_assets_annual") |
| Debt to Capital (Annual) | `debt_to_capital_annual` | YCP("MSFT","debt_to_capital_annual") |
| Debt to Equity Ratio (Annual) | `debt_equity_ratio_annual` | YCP("MSFT","debt_equity_ratio_annual") |
| Decrease in Deposits (Annual) | `deps_decr_cf_annual` | YCP("MSFT","deps_decr_cf_annual") |
| Decrease in Deposits (TTM) | `deps_decr_cf_ttm` | YCP("MSFT","deps_decr_cf_ttm") |
| Decrease in Loans (Annual) | `loan_decr_cf_annual` | YCP("MSFT","loan_decr_cf_annual") |
| Decrease in Loans (TTM) | `loan_decr_cf_ttm` | YCP("MSFT","loan_decr_cf_ttm") |
| Defensive Interval Ratio (Annual) | `defensive_interval_ratio_annual` | YCP("MSFT","defensive_interval_ratio_annual") |
| Deferred Charges (Annual) | `dfd_chrg_annual` | YCP("MSFT","dfd_chrg_annual") |
| Deferred Income (Annual) | `dfd_inc_annual` | YCP("MSFT","dfd_inc_annual") |
| Deferred Tax Assets (Annual) | `dfd_tax_db_annual` | YCP("MSFT","dfd_tax_db_annual") |
| Deferred Tax Liability - Untaxed Reserves (Annual) | `dfd_tax_rsrv_annual` | YCP("MSFT","dfd_tax_rsrv_annual") |
| Deferred Taxes & Investment Tax Credit (Annual) | `dfd_tax_cf_annual` | YCP("MSFT","dfd_tax_cf_annual") |
| Deferred Taxes & Investment Tax Credit (TTM) | `dfd_tax_cf_ttm` | YCP("MSFT","dfd_tax_cf_ttm") |
| Deferred Taxes (Annual) | `deferred_tax_annual` | YCP("MSFT","deferred_tax_annual") |
| Deferred Taxes (TTM) | `deferred_tax_ttm` | YCP("MSFT","deferred_tax_ttm") |
| Demand Deposits (Annual) | `deps_demand_annual` | YCP("MSFT","deps_demand_annual") |
| Deposits - Total (Annual) | `deps_annual` | YCP("MSFT","deps_annual") |
| Depreciation & Depletion (Cash Flow) (Annual) | `dep_exp_xamort_cf_annual` | YCP("MSFT","dep_exp_xamort_cf_annual") |
| Depreciation & Depletion (Cash Flow) (TTM) | `dep_exp_xamort_cf_ttm` | YCP("MSFT","dep_exp_xamort_cf_ttm") |
| Depreciation, Depletion And Amortization (Annual) | `dep_amort_exp_annual` | YCP("MSFT","dep_amort_exp_annual") |
| Depreciation, Depletion And Amortization (TTM) | `dep_amort_exp_ttm` | YCP("MSFT","dep_amort_exp_ttm") |
| Discontinued Operations (Annual) | `disc_oper_annual` | YCP("MSFT","disc_oper_annual") |
| Discontinued Operations (TTM) | `disc_oper_ttm` | YCP("MSFT","disc_oper_ttm") |
| Dividend (Annual) | `dividend_annual` | YCP("MSFT","dividend_annual") |
| Dividend Cover (Annual) | `dividend_cover_annual` | YCP("MSFT","dividend_cover_annual") |
| Dividend Per Share (Annual) | `dividend_per_share_annual` | YCP("MSFT","dividend_per_share_annual") |
| Dividend Per Share (TTM) | `dividend_per_share_ttm` | YCP("MSFT","dividend_per_share_ttm") |
| Dividends Paid (TTM) | `dividend_ttm` | YCP("MSFT","dividend_ttm") |
| Dividends Payable (Annual) | `dividends_payable_annual` | YCP("MSFT","dividends_payable_annual") |
| EBIT (Annual) | `ebit_annual` | YCP("MSFT","ebit_annual") |
| EBIT (Quarterly) | `ebit` | YCP("MSFT","ebit") |
| EBIT (TTM) | `ebit_ttm` | YCP("MSFT","ebit_ttm") |
| EBIT Margin (Annual) | `ebit_margin_annual` | YCP("MSFT","ebit_margin_annual") |
| EBIT Margin (Quarterly) | `ebit_margin` | YCP("MSFT","ebit_margin") |
| EBIT Margin (TTM) | `ebit_margin_ttm` | YCP("MSFT","ebit_margin_ttm") |
| EBIT Per Employee (Annual) | `ebit_per_employee_annual` | YCP("MSFT","ebit_per_employee_annual") |
| EBIT Per Share (TTM) | `ebit_per_share_ttm` | YCP("MSFT","ebit_per_share_ttm") |
| EBIT to Interest Expense (Annual) | `ebit_interest_expense_annual` | YCP("MSFT","ebit_interest_expense_annual") |
| EBIT to Interest Expense (TTM) | `ebit_interest_expense_ttm` | YCP("MSFT","ebit_interest_expense_ttm") |
| EBITDA (Annual) | `ebitda_annual` | YCP("MSFT","ebitda_annual") |
| EBITDA (Quarterly) | `ebitda` | YCP("MSFT","ebitda") |
| EBITDA (TTM) | `ebitda_ttm` | YCP("MSFT","ebitda_ttm") |
| EBITDA Margin (Annual) | `ebitda_margin_annual` | YCP("MSFT","ebitda_margin_annual") |
| EBITDA Margin (TTM) | `ebitda_margin_ttm` | YCP("MSFT","ebitda_margin_ttm") |
| EBITDA Per Employee (Annual) | `ebitda_per_employee_annual` | YCP("MSFT","ebitda_per_employee_annual") |
| EBITDA Per Share (TTM) | `ebitda_per_share_ttm` | YCP("MSFT","ebitda_per_share_ttm") |
| EBITDA To Assets (Annual) | `ebitda_to_assets_annual` | YCP("MSFT","ebitda_to_assets_annual") |
| EPS After Extraordinary Items (Annual) | `eps_aft_xord_annual` | YCP("MSFT","eps_aft_xord_annual") |
| EPS After Extraordinary Items (TTM) | `eps_aft_xord_ttm` | YCP("MSFT","eps_aft_xord_ttm") |
| EPS Basic (Annual) | `net_eps_basic_annual` | YCP("MSFT","net_eps_basic_annual") |
| EPS Basic (TTM) | `net_eps_basic_ttm` | YCP("MSFT","net_eps_basic_ttm") |
| EPS Diluted (Annual) | `eps_annual` | YCP("MSFT","eps_annual") |
| EPS Diluted (Quarterly) | `eps` | YCP("MSFT","eps") |
| EPS Diluted (TTM) | `eps_ttm` | YCP("MSFT","eps_ttm") |
| EPS Diluted from Continuing Operations (Annual) | `diluted_continuous_operations_annual` | YCP("MSFT","diluted_continuous_operations_annual") |
| EPS Diluted from Continuing Operations (TTM) | `diluted_continuous_operations_ttm` | YCP("MSFT","diluted_continuous_operations_ttm") |
| EPS Diluted from Extraordinaries (Annual) | `eps_dil_aft_xord_annual` | YCP("MSFT","eps_dil_aft_xord_annual") |
| EPS Diluted from Extraordinaries (TTM) | `eps_dil_aft_xord_ttm` | YCP("MSFT","eps_dil_aft_xord_ttm") |
| ESOP Debt Guarantee (Annual) | `com_stk_esop_annual` | YCP("MSFT","com_stk_esop_annual") |
| ESOP Guarantees - Preferred Stock (Annual) | `pfd_stk_esop_gtd_annual` | YCP("MSFT","pfd_stk_esop_gtd_annual") |
| EV to Assets (Annual) | `ev_assets_annual` | YCP("MSFT","ev_assets_annual") |
| EV to CFO (Annual) | `ev_cfo_annual` | YCP("MSFT","ev_cfo_annual") |
| EV to EBIT (Annual) | `ev_ebit_annual` | YCP("MSFT","ev_ebit_annual") |
| EV to EBITDA (Annual) | `ev_ebitda_annual` | YCP("MSFT","ev_ebitda_annual") |
| EV to Earnings (Annual) | `ev_earnings_annual` | YCP("MSFT","ev_earnings_annual") |
| EV to Free Cash Flow (Annual) | `ev_free_cash_flow_annual` | YCP("MSFT","ev_free_cash_flow_annual") |
| EV to Revenues (Annual) | `ev_revenues_annual` | YCP("MSFT","ev_revenues_annual") |
| Early Termination of Contracts (Annual) | `early_term_contract_annual` | YCP("MSFT","early_term_contract_annual") |
| Early Termination of Contracts (TTM) | `early_term_contract_ttm` | YCP("MSFT","early_term_contract_ttm") |
| Earnings Persistence (Annual) | `earn_perst_annual` | YCP("MSFT","earn_perst_annual") |
| Earnings Persistence (TTM) | `earn_perst_ttm` | YCP("MSFT","earn_perst_ttm") |
| Earnings Surprise (Annual) | `earnings_surprise_annual` | YCP("MSFT","earnings_surprise_annual") |
| Effective Tax Rate (Annual) | `effective_tax_rate_annual` | YCP("MSFT","effective_tax_rate_annual") |
| Effective Tax Rate (Quarterly) | `effective_tax_rate_quarterly` | YCP("MSFT","effective_tax_rate_quarterly") |
| Ending Cash (Annual) | `end_cash_annual` | YCP("MSFT","end_cash_annual") |
| Enterprise Value Per Employee (Annual) | `ev_per_employee_annual` | YCP("MSFT","ev_per_employee_annual") |
| Equipment Expense (Annual) | `equip_exp_annual` | YCP("MSFT","equip_exp_annual") |
| Equipment Expense (TTM) | `equip_exp_ttm` | YCP("MSFT","equip_exp_ttm") |
| Equity In Earnings (Annual) | `eq_aff_inc_annual` | YCP("MSFT","eq_aff_inc_annual") |
| Equity In Earnings (TTM) | `eq_aff_inc_ttm` | YCP("MSFT","eq_aff_inc_ttm") |
| Equity Securities Investment - Total (Annual) | `invest_eq_annual` | YCP("MSFT","invest_eq_annual") |
| Exceptional Provisions (Annual) | `xcept_prov_annual` | YCP("MSFT","xcept_prov_annual") |
| Exceptional Provisions (TTM) | `xcept_prov_ttm` | YCP("MSFT","xcept_prov_ttm") |
| Extraordinary Items (Annual) | `xord_cf_annual` | YCP("MSFT","xord_cf_annual") |
| Extraordinary Items (TTM) | `xord_cf_ttm` | YCP("MSFT","xord_cf_ttm") |
| Extraordinary Items, Income Statement (Annual) | `extraordinary_income_annual` | YCP("MSFT","extraordinary_income_annual") |
| Extraordinary Items, Income Statement (TTM) | `extraordinary_income_ttm` | YCP("MSFT","extraordinary_income_ttm") |
| FCF to Assets (Annual) | `free_cash_roa_annual` | YCP("MSFT","free_cash_roa_annual") |
| FCF to Assets (TTM) | `free_cash_roa_ttm` | YCP("MSFT","free_cash_roa_ttm") |
| FCF to Debt (Annual) | `fcf_to_debt_annual` | YCP("MSFT","fcf_to_debt_annual") |
| Fed Funds & Security Under Resale Agrmts (Annual) | `fed_repos_asset_annual` | YCP("MSFT","fed_repos_asset_annual") |
| Federal Agency Securities (Annual) | `secs_fed_annual` | YCP("MSFT","secs_fed_annual") |
| Federal Funds (Annual) | `fed_funds_annual` | YCP("MSFT","fed_funds_annual") |
| Fees (Annual) | `fees_annual` | YCP("MSFT","fees_annual") |
| Fees (TTM) | `fees_ttm` | YCP("MSFT","fees_ttm") |
| Financial Debt (Annual) | `financial_debt_annual` | YCP("MSFT","financial_debt_annual") |
| Financial Debt To EBITDA (Annual) | `financial_debt_to_ebitda_annual` | YCP("MSFT","financial_debt_to_ebitda_annual") |
| Financial Debt to Total Equity (Annual) | `financial_debt_to_total_equity_annual` | YCP("MSFT","financial_debt_to_total_equity_annual") |
| Financial Leverage (Annual) | `financial_leverage_annual` | YCP("MSFT","financial_leverage_annual") |
| Financing Interest Paid - Lease Liab (Annual) | `int_fin_cf_annual` | YCP("MSFT","int_fin_cf_annual") |
| Financing Interest Paid - Lease Liab (TTM) | `int_fin_cf_ttm` | YCP("MSFT","int_fin_cf_ttm") |
| Finished Goods Inventory (Annual) | `finished_goods_annual` | YCP("MSFT","finished_goods_annual") |
| Fixed Asset Turnover (Annual) | `fixed_asset_turnover_annual` | YCP("MSFT","fixed_asset_turnover_annual") |
| Fixed Asset Turnover (TTM) | `fixed_asset_turnover_ttm` | YCP("MSFT","fixed_asset_turnover_ttm") |
| Foreign Exchange Income (Annual) | `for_exch_inc_annual` | YCP("MSFT","for_exch_inc_annual") |
| Foreign Exchange Income (TTM) | `for_exch_inc_ttm` | YCP("MSFT","for_exch_inc_ttm") |
| Foreign Loans (Annual) | `loan_for_annual` | YCP("MSFT","loan_for_annual") |
| Foreign Office Deposits (Annual) | `deps_for_annual` | YCP("MSFT","deps_for_annual") |
| Free Cash Flow (TTM) | `free_cash_flow_ttm` | YCP("MSFT","free_cash_flow_ttm") |
| Free Cash Flow (Annual) | `free_cash_flow_annual` | YCP("MSFT","free_cash_flow_annual") |
| Free Cash Flow Margin (TTM) | `free_cash_flow_margin_ttm` | YCP("MSFT","free_cash_flow_margin_ttm") |
| Free Cash Flow Per Share (TTM) | `free_cash_flow_per_share_ttm` | YCP("MSFT","free_cash_flow_per_share_ttm") |
| Free Cash Flow Per Share (Annual) | `free_cash_flow_per_share_annual` | YCP("MSFT","free_cash_flow_per_share_annual") |
| Free Cash Flow Return on Invested Capital (Annual) | `free_cash_flow_roic_annual` | YCP("MSFT","free_cash_flow_roic_annual") |
| Free Cash Flow Yield (Annual) | `fcf_yld_annual` | YCP("MSFT","fcf_yld_annual") |
| Free Cash Flow Yield (TTM) | `fcf_yld_ttm` | YCP("MSFT","fcf_yld_ttm") |
| Free Cash Flow to Enterprise Value (TTM) | `free_cash_flow_ev_ttm` | YCP("MSFT","free_cash_flow_ev_ttm") |
| Free Cash Flow to Equity (TTM) | `free_cash_flow_equity_ttm` | YCP("MSFT","free_cash_flow_equity_ttm") |
| Free Cash Flow to Equity (Annual) | `free_cash_flow_equity_annual` | YCP("MSFT","free_cash_flow_equity_annual") |
| Free Cash Flow to Equity FCFE (TTM) | `free_cf_fcfe_ttm` | YCP("MSFT","free_cf_fcfe_ttm") |
| Free Cash Flow to Firm (TTM) | `free_cash_flow_firm_ttm` | YCP("MSFT","free_cash_flow_firm_ttm") |
| Free Cash Flow to Firm (Annual) | `free_cash_flow_firm_annual` | YCP("MSFT","free_cash_flow_firm_annual") |
| Fulmer H Factor (Annual) | `fulmer_h_score_annual` | YCP("MSFT","fulmer_h_score_annual") |
| Funds From Operations (Annual) | `funds_oper_gross_annual` | YCP("MSFT","funds_oper_gross_annual") |
| Funds From Operations (TTM) | `funds_oper_gross_ttm` | YCP("MSFT","funds_oper_gross_ttm") |
| Funds from Operations FFO (Annual) | `ffo_annual` | YCP("MSFT","ffo_annual") |
| Funds from Operations FFO (TTM) | `ffo_ttm` | YCP("MSFT","ffo_ttm") |
| GA Expense Per Employee (Annual) | `ga_exp_per_employee_annual` | YCP("MSFT","ga_exp_per_employee_annual") |
| General and Administrative Expense (Annual) | `general_and_administrative_expense_annual` | YCP("MSFT","general_and_administrative_expense_annual") |
| General and Administrative Expense (TTM) | `general_and_administrative_expense_ttm` | YCP("MSFT","general_and_administrative_expense_ttm") |
| Goodwill - Gross (Annual) | `gw_gross_annual` | YCP("MSFT","gw_gross_annual") |
| Goodwill and Intangibles (Annual) | `goodwill_and_intangible_annual` | YCP("MSFT","goodwill_and_intangible_annual") |
| Graham's Number (Annual) | `graham_number_annual` | YCP("MSFT","graham_number_annual") |
| Gross PP&E (Annual) | `gross_property_plant_equip_annual` | YCP("MSFT","gross_property_plant_equip_annual") |
| Gross Profit (Annual) | `gross_profit_annual` | YCP("MSFT","gross_profit_annual") |
| Gross Profit (Quarterly) | `gross_profit` | YCP("MSFT","gross_profit") |
| Gross Profit (TTM) | `gross_profit_ttm` | YCP("MSFT","gross_profit_ttm") |
| Gross Profit Margin (TTM) | `gross_profit_margin_ttm` | YCP("MSFT","gross_profit_margin_ttm") |
| Gross Profit Margin (Annual) | `gross_profit_margin_annual` | YCP("MSFT","gross_profit_margin_annual") |
| Impairment Expense (Capital Asset) (Annual) | `ppe_impair_annual` | YCP("MSFT","ppe_impair_annual") |
| Impairment Expense (Capital Asset) (TTM) | `ppe_impair_ttm` | YCP("MSFT","ppe_impair_ttm") |
| Impairment of Goodwill (Annual) | `gw_impair_annual` | YCP("MSFT","gw_impair_annual") |
| Impairment of Goodwill (TTM) | `gw_impair_ttm` | YCP("MSFT","gw_impair_ttm") |
| Inc/Dec In Fed Home Loan Advances (Annual) | `incr_fed_home_adv_cf_annual` | YCP("MSFT","incr_fed_home_adv_cf_annual") |
| Inc/Dec In Fed Home Loan Advances (TTM) | `incr_fed_home_adv_cf_ttm` | YCP("MSFT","incr_fed_home_adv_cf_ttm") |
| Income After Tax (Annual) | `income_after_tax_annual` | YCP("MSFT","income_after_tax_annual") |
| Income After Tax (TTM) | `income_after_tax_ttm` | YCP("MSFT","income_after_tax_ttm") |
| Income Attributable to Minority Interest (Annual) | `minority_interest_annual` | YCP("MSFT","minority_interest_annual") |
| Income Attributable to Minority Interest (TTM) | `minority_interest_ttm` | YCP("MSFT","minority_interest_ttm") |
| Income Statement Depreciation (Annual) | `depreciation_is_annual` | YCP("MSFT","depreciation_is_annual") |
| Income Statement Depreciation (TTM) | `depreciation_is_ttm` | YCP("MSFT","depreciation_is_ttm") |
| Income Tax - Current - Domestic (Annual) | `inc_tax_curr_dom_annual` | YCP("MSFT","inc_tax_curr_dom_annual") |
| Income Tax - Current - Domestic (TTM) | `inc_tax_curr_dom_ttm` | YCP("MSFT","inc_tax_curr_dom_ttm") |
| Income Tax - Current - Foreign (Annual) | `inc_tax_curr_for_annual` | YCP("MSFT","inc_tax_curr_for_annual") |
| Income Tax - Current - Foreign (TTM) | `inc_tax_curr_for_ttm` | YCP("MSFT","inc_tax_curr_for_ttm") |
| Income Tax - Deferred - Domestic (Annual) | `inc_tax_dfd_dom_annual` | YCP("MSFT","inc_tax_dfd_dom_annual") |
| Income Tax - Deferred - Domestic (TTM) | `inc_tax_dfd_dom_ttm` | YCP("MSFT","inc_tax_dfd_dom_ttm") |
| Income Tax - Deferred - Foreign (Annual) | `inc_tax_dfd_for_annual` | YCP("MSFT","inc_tax_dfd_for_annual") |
| Income Tax - Deferred - Foreign (TTM) | `inc_tax_dfd_for_ttm` | YCP("MSFT","inc_tax_dfd_for_ttm") |
| Income Tax Credits (Annual) | `itc_annual` | YCP("MSFT","itc_annual") |
| Income Tax Credits (TTM) | `itc_ttm` | YCP("MSFT","itc_ttm") |
| Income Tax Paid Supplemental Data (Annual) | `income_tax_paid_supplemental_data_annual` | YCP("MSFT","income_tax_paid_supplemental_data_annual") |
| Income Tax Paid Supplemental Data (TTM) | `income_tax_paid_supplemental_data_ttm` | YCP("MSFT","income_tax_paid_supplemental_data_ttm") |
| Income from Continuing Operations (Annual) | `income_bef_ex_items_and_disc_ops_annual` | YCP("MSFT","income_bef_ex_items_and_disc_ops_annual") |
| Income from Continuing Operations (TTM) | `income_bef_ex_items_and_disc_ops_ttm` | YCP("MSFT","income_bef_ex_items_and_disc_ops_ttm") |
| Income from Discontinued Operations (Annual) | `income_from_discontinued_ops_annual` | YCP("MSFT","income_from_discontinued_ops_annual") |
| Income from Discontinued Operations (TTM) | `income_from_discontinued_ops_ttm` | YCP("MSFT","income_from_discontinued_ops_ttm") |
| Increase in Deposits (Annual) | `deps_incr_cf_annual` | YCP("MSFT","deps_incr_cf_annual") |
| Increase in Deposits (TTM) | `deps_incr_cf_ttm` | YCP("MSFT","deps_incr_cf_ttm") |
| Increase in Loans (Annual) | `loan_incr_cf_annual` | YCP("MSFT","loan_incr_cf_annual") |
| Increase in Loans (TTM) | `loan_incr_cf_ttm` | YCP("MSFT","loan_incr_cf_ttm") |
| Increase/Decrease In Accounts Payable (Annual) | `pay_acct_cf_annual` | YCP("MSFT","pay_acct_cf_annual") |
| Increase/Decrease In Accounts Payable (TTM) | `pay_acct_cf_ttm` | YCP("MSFT","pay_acct_cf_ttm") |
| Insurance Reserves - Total (Annual) | `ins_liabs_pol_annual` | YCP("MSFT","ins_liabs_pol_annual") |
| Int Exp on Other Borrowed Funds (Annual) | `int_exp_oth_borr_annual` | YCP("MSFT","int_exp_oth_borr_annual") |
| Int Exp on Other Borrowed Funds (TTM) | `int_exp_oth_borr_ttm` | YCP("MSFT","int_exp_oth_borr_ttm") |
| Intangibles Turnover (Annual) | `intangibles_turnover_annual` | YCP("MSFT","intangibles_turnover_annual") |
| Intangibles Turnover (TTM) | `intangibles_turnover_ttm` | YCP("MSFT","intangibles_turnover_ttm") |
| Interbank Loans (Annual) | `loan_bk_annual` | YCP("MSFT","loan_bk_annual") |
| Interest Capitalized (Annual) | `int_cap_annual` | YCP("MSFT","int_cap_annual") |
| Interest Capitalized (TTM) | `int_cap_ttm` | YCP("MSFT","int_cap_ttm") |
| Interest Expense (Annual) | `interest_expense_annual` | YCP("MSFT","interest_expense_annual") |
| Interest Expense on Bank Deposits (Annual) | `int_exp_deps_annual` | YCP("MSFT","int_exp_deps_annual") |
| Interest Expense on Bank Deposits (TTM) | `int_exp_deps_ttm` | YCP("MSFT","int_exp_deps_ttm") |
| Interest Expense on Debt (Annual) | `int_exp_debt_annual` | YCP("MSFT","int_exp_debt_annual") |
| Interest Expense on Debt (TTM) | `int_exp_debt_ttm` | YCP("MSFT","int_exp_debt_ttm") |
| Interest Expense on Federal Funds (Annual) | `int_exp_fed_repos_annual` | YCP("MSFT","int_exp_fed_repos_annual") |
| Interest Expense on Federal Funds (TTM) | `int_exp_fed_repos_ttm` | YCP("MSFT","int_exp_fed_repos_ttm") |
| Interest Income on Bank Deposits (Annual) | `int_inc_deps_annual` | YCP("MSFT","int_inc_deps_annual") |
| Interest Income on Bank Deposits (TTM) | `int_inc_deps_ttm` | YCP("MSFT","int_inc_deps_ttm") |
| Interest Income on Federal Funds (Annual) | `int_inc_fed_funds_annual` | YCP("MSFT","int_inc_fed_funds_annual") |
| Interest Income on Federal Funds (TTM) | `int_inc_fed_funds_ttm` | YCP("MSFT","int_inc_fed_funds_ttm") |
| Interest Income on Loans (Annual) | `int_inc_loan_annual` | YCP("MSFT","int_inc_loan_annual") |
| Interest Income on Loans (TTM) | `int_inc_loan_ttm` | YCP("MSFT","int_inc_loan_ttm") |
| Interest Paid Supplemental Data (Annual) | `interest_paid_supplemental_data_annual` | YCP("MSFT","interest_paid_supplemental_data_annual") |
| Interest Paid Supplemental Data (TTM) | `interest_paid_supplemental_data_ttm` | YCP("MSFT","interest_paid_supplemental_data_ttm") |
| Interest Receivables (Annual) | `receiv_int_annual` | YCP("MSFT","receiv_int_annual") |
| Interest on Government Securities (Annual) | `int_inc_fed_repos_annual` | YCP("MSFT","int_inc_fed_repos_annual") |
| Interest on Government Securities (TTM) | `int_inc_fed_repos_ttm` | YCP("MSFT","int_inc_fed_repos_ttm") |
| Inv in Unconsolidated Subsidiaries (Annual) | `invest_aff_annual` | YCP("MSFT","invest_aff_annual") |
| Inventories (Annual) | `inventories_net_annual` | YCP("MSFT","inventories_net_annual") |
| Inventories - Days Held (Annual) | `inven_days_annual` | YCP("MSFT","inven_days_annual") |
| Inventories - Progress Payments & Other (Annual) | `inven_prog_paymt_annual` | YCP("MSFT","inven_prog_paymt_annual") |
| Inventory Turnover (Annual) | `inventory_turnover_annual` | YCP("MSFT","inventory_turnover_annual") |
| Inventory Turnover (TTM) | `inventory_turnover_ttm` | YCP("MSFT","inventory_turnover_ttm") |
| Invested Capital (Annual) | `invested_capital_annual` | YCP("MSFT","invested_capital_annual") |
| Investment Income (Annual) | `invest_inc_annual` | YCP("MSFT","invest_inc_annual") |
| Investment Income (TTM) | `invest_inc_ttm` | YCP("MSFT","invest_inc_ttm") |
| Investment Tax Credits (Cash Flow) (Annual) | `itc_cf_annual` | YCP("MSFT","itc_cf_annual") |
| Investment Tax Credits (Cash Flow) (TTM) | `itc_cf_ttm` | YCP("MSFT","itc_cf_ttm") |
| Investment Write Off (Annual) | `write_off_annual` | YCP("MSFT","write_off_annual") |
| Investment Write Off (TTM) | `write_off_ttm` | YCP("MSFT","write_off_ttm") |
| Issuance of Capital Stock (Annual) | `issuance_of_capital_stock_annual` | YCP("MSFT","issuance_of_capital_stock_annual") |
| Issuance of Capital Stock (TTM) | `issuance_of_capital_stock_ttm` | YCP("MSFT","issuance_of_capital_stock_ttm") |
| Issuance of Long-term Debt (Annual) | `debt_lt_iss_cf_annual` | YCP("MSFT","debt_lt_iss_cf_annual") |
| Issuance of Long-term Debt (TTM) | `debt_lt_iss_cf_ttm` | YCP("MSFT","debt_lt_iss_cf_ttm") |
| Land and Improvements (Annual) | `land_and_improvements_annual` | YCP("MSFT","land_and_improvements_annual") |
| Lease Financing Loans (Annual) | `loan_lease_fin_annual` | YCP("MSFT","loan_lease_fin_annual") |
| Leases (Annual) | `leases_annual` | YCP("MSFT","leases_annual") |
| Legal Claims Expense (Annual) | `legal_claim_exp_annual` | YCP("MSFT","legal_claim_exp_annual") |
| Legal Claims Expense (TTM) | `legal_claim_exp_ttm` | YCP("MSFT","legal_claim_exp_ttm") |
| Liabilities To Assets (Annual) | `liabilities_to_assets_annual` | YCP("MSFT","liabilities_to_assets_annual") |
| Loan Losses - Actual (Annual) | `loan_loss_act_annual` | YCP("MSFT","loan_loss_act_annual") |
| Loan Losses - Net (Annual) | `loan_loss_net_annual` | YCP("MSFT","loan_loss_net_annual") |
| Loan Losses - Recoveries (Annual) | `loan_loss_recov_annual` | YCP("MSFT","loan_loss_recov_annual") |
| Loans - Gross (Annual) | `loan_gross_annual` | YCP("MSFT","loan_gross_annual") |
| Loans - Net (Annual) | `loan_net_annual` | YCP("MSFT","loan_net_annual") |
| Long Term Debt Excl Lease Liab (Annual) | `debt_lt_xlease_annual` | YCP("MSFT","debt_lt_xlease_annual") |
| Long Term Deferred Tax Assets (Annual) | `deferred_tax_assets_long_term_annual` | YCP("MSFT","deferred_tax_assets_long_term_annual") |
| Long Term Deferred Tax Liabilities (Annual) | `deferred_tax_liab_long_term_annual` | YCP("MSFT","deferred_tax_liab_long_term_annual") |
| Long Term Investments (Annual) | `long_term_investments_annual` | YCP("MSFT","long_term_investments_annual") |
| Long Term Receivables (Annual) | `long_term_receivables_annual` | YCP("MSFT","long_term_receivables_annual") |
| Long-Term Insurance Reserves (Annual) | `ins_lt_rsrv_annual` | YCP("MSFT","ins_lt_rsrv_annual") |
| Long-Term Insurance Reserves (TTM) | `ins_lt_rsrv_ttm` | YCP("MSFT","ins_lt_rsrv_ttm") |
| Loss Settling Claims (Annual) | `loss_claim_exp_annual` | YCP("MSFT","loss_claim_exp_annual") |
| Loss Settling Claims (TTM) | `loss_claim_exp_ttm` | YCP("MSFT","loss_claim_exp_ttm") |
| Losses, Benefits, Adjusted & Long-Term Reserves (Annual) | `loss_claim_rsrv_annual` | YCP("MSFT","loss_claim_rsrv_annual") |
| Losses, Benefits, Adjusted & Long-Term Reserves (TTM) | `loss_claim_rsrv_ttm` | YCP("MSFT","loss_claim_rsrv_ttm") |
| Market Cap Per Employee (Annual) | `market_cap_per_employee_annual` | YCP("MSFT","market_cap_per_employee_annual") |
| Minimum Pension Liabilities (Annual) | `minimum_pension_liabilities_annual` | YCP("MSFT","minimum_pension_liabilities_annual") |
| Minority Interest Ownership (Annual) | `minority_interest_balance_sheet_annual` | YCP("MSFT","minority_interest_balance_sheet_annual") |
| Miscellaneous Current Assets (Annual) | `assets_curr_misc_annual` | YCP("MSFT","assets_curr_misc_annual") |
| Miscellaneous Current Liabilities (Annual) | `liabs_curr_misc_annual` | YCP("MSFT","liabs_curr_misc_annual") |
| Miscellaneous Funds (Annual) | `misc_funds_cf_annual` | YCP("MSFT","misc_funds_cf_annual") |
| Miscellaneous Funds (TTM) | `misc_funds_cf_ttm` | YCP("MSFT","misc_funds_cf_ttm") |
| Miscellaneous Non-Operating Expense (Annual) | `misc_exp_non_oper_annual` | YCP("MSFT","misc_exp_non_oper_annual") |
| Miscellaneous Non-Operating Expense (TTM) | `misc_exp_non_oper_ttm` | YCP("MSFT","misc_exp_non_oper_ttm") |
| Mortgage Backed Securities (Annual) | `mbs_annual` | YCP("MSFT","mbs_annual") |
| Mortgage, Policy & Other Loans (Annual) | `invest_mtge_annual` | YCP("MSFT","invest_mtge_annual") |
| NOPAT (Annual) | `nopat_annual` | YCP("MSFT","nopat_annual") |
| Net Change in Long Term Debt (Annual) | `net_long_term_debt_annual` | YCP("MSFT","net_long_term_debt_annual") |
| Net Change in Long Term Debt (TTM) | `net_long_term_debt_ttm` | YCP("MSFT","net_long_term_debt_ttm") |
| Net Common Buyback Yield (TTM) | `net_buyback_yield_ttm` | YCP("MSFT","net_buyback_yield_ttm") |
| Net Common Equity Issued (Purchased) (Annual) | `net_common_equity_issued_annual` | YCP("MSFT","net_common_equity_issued_annual") |
| Net Common Equity Issued (Purchased) (TTM) | `net_common_equity_issued_ttm` | YCP("MSFT","net_common_equity_issued_ttm") |
| Net Common Payout Yield (TTM) | `net_payout_yield_ttm` | YCP("MSFT","net_payout_yield_ttm") |
| Net Current Asset Value Per Share NCAVPS (Annual) | `ncavps_annual` | YCP("MSFT","ncavps_annual") |
| Net Debt (Annual) | `net_debt_annual` | YCP("MSFT","net_debt_annual") |
| Net Debt Issuance (Annual) | `debt_issuance_net_total_annual` | YCP("MSFT","debt_issuance_net_total_annual") |
| Net Debt Issuance (TTM) | `debt_issuance_net_total_ttm` | YCP("MSFT","debt_issuance_net_total_ttm") |
| Net Debt Paydown Yield (TTM) | `net_debt_paydown_yield_ttm` | YCP("MSFT","net_debt_paydown_yield_ttm") |
| Net Debt Paydown Yield (Annual) | `net_debt_paydown_yield_annual` | YCP("MSFT","net_debt_paydown_yield_annual") |
| Net Divestitures (Acquisitions) (Annual) | `net_acquisitions_divestitures_annual` | YCP("MSFT","net_acquisitions_divestitures_annual") |
| Net Divestitures (Acquisitions) (TTM) | `net_acquisitions_divestitures_ttm` | YCP("MSFT","net_acquisitions_divestitures_ttm") |
| Net Financial Debt (Annual) | `net_financial_debt_annual` | YCP("MSFT","net_financial_debt_annual") |
| Net Goodwill (Annual) | `gw_annual` | YCP("MSFT","gw_annual") |
| Net Income (Annual) | `net_income_cf_annual` | YCP("MSFT","net_income_cf_annual") |
| Net Income (TTM) | `net_income_ttm` | YCP("MSFT","net_income_ttm") |
| Net Income After Extraordinary Items (Annual) | `net_inc_aft_xord_annual` | YCP("MSFT","net_inc_aft_xord_annual") |
| Net Income After Extraordinary Items (TTM) | `net_inc_aft_xord_ttm` | YCP("MSFT","net_inc_aft_xord_ttm") |
| Net Income Attr to Common Stockholders (Annual) | `net_inc_basic_annual` | YCP("MSFT","net_inc_basic_annual") |
| Net Income Attr to Common Stockholders (TTM) | `net_inc_basic_ttm` | YCP("MSFT","net_inc_basic_ttm") |
| Net Income Per Employee (Annual) | `ni_per_employee_annual` | YCP("MSFT","ni_per_employee_annual") |
| Net Interest Income (Annual) | `interest_income_annual` | YCP("MSFT","interest_income_annual") |
| Net Interest Income (TTM) | `interest_income_ttm` | YCP("MSFT","interest_income_ttm") |
| Net Interest Income After Loan Loss Provision (Annual) | `int_inc_aft_prov_annual` | YCP("MSFT","int_inc_aft_prov_annual") |
| Net Interest Income After Loan Loss Provision (TTM) | `int_inc_aft_prov_ttm` | YCP("MSFT","int_inc_aft_prov_ttm") |
| Net Investment Income (Annual) | `ins_invest_inc_annual` | YCP("MSFT","ins_invest_inc_annual") |
| Net Investment Income (TTM) | `ins_invest_inc_ttm` | YCP("MSFT","ins_invest_inc_ttm") |
| Net Other Intangibles (Annual) | `intang_oth_annual` | YCP("MSFT","intang_oth_annual") |
| Net PP&E (Annual) | `net_ppe_annual` | YCP("MSFT","net_ppe_annual") |
| Net PP&E - Buildings (Annual) | `ppe_net_bldg_annual` | YCP("MSFT","ppe_net_bldg_annual") |
| Net PP&E - Comp Software & Equip (Annual) | `ppe_net_soft_equip_annual` | YCP("MSFT","ppe_net_soft_equip_annual") |
| Net PP&E - Other Property (Annual) | `ppe_net_oth_annual` | YCP("MSFT","ppe_net_oth_annual") |
| Net Shareholder Payout (Annual) | `net_shareholder_payout_annual` | YCP("MSFT","net_shareholder_payout_annual") |
| Net Shareholder Payout (TTM) | `net_shareholder_payout_ttm` | YCP("MSFT","net_shareholder_payout_ttm") |
| Net Total Long Term Debt (Annual) | `net_total_long_term_debt_annual` | YCP("MSFT","net_total_long_term_debt_annual") |
| Non-Cash Items (Annual) | `non_cash_annual` | YCP("MSFT","non_cash_annual") |
| Non-Cash Items (TTM) | `non_cash_ttm` | YCP("MSFT","non_cash_ttm") |
| Non-Current Portion of Long Term Debt (Annual) | `long_term_debt_annual` | YCP("MSFT","long_term_debt_annual") |
| Non-Equity Reserves (Annual) | `rsrv_noneq_annual` | YCP("MSFT","rsrv_noneq_annual") |
| Non-Interest Expense (Annual) | `non_int_exp_annual` | YCP("MSFT","non_int_exp_annual") |
| Non-Interest Expense (TTM) | `non_int_exp_ttm` | YCP("MSFT","non_int_exp_ttm") |
| Non-Interest Income (Annual) | `non_int_inc_annual` | YCP("MSFT","non_int_inc_annual") |
| Non-Interest Income (TTM) | `non_int_inc_ttm` | YCP("MSFT","non_int_inc_ttm") |
| Non-Operating Income (Annual) | `non_oper_inc_annual` | YCP("MSFT","non_oper_inc_annual") |
| Non-Operating Income (TTM) | `non_oper_inc_ttm` | YCP("MSFT","non_oper_inc_ttm") |
| Non-Operating Interest Expense (Annual) | `interest_expense_non_operating_annual` | YCP("MSFT","interest_expense_non_operating_annual") |
| Non-Operating Interest Expense (TTM) | `interest_expense_non_operating_ttm` | YCP("MSFT","interest_expense_non_operating_ttm") |
| Non-Operating Interest Income (Annual) | `int_inc_non_oper_annual` | YCP("MSFT","int_inc_non_oper_annual") |
| Non-Operating Interest Income (TTM) | `int_inc_non_oper_ttm` | YCP("MSFT","int_inc_non_oper_ttm") |
| Non-Performing Loans - Gross (Annual) | `loan_nonperf_annual` | YCP("MSFT","loan_nonperf_annual") |
| Non-Redeemable Preferred Stock (Annual) | `invest_pfd_nred_annual` | YCP("MSFT","invest_pfd_nred_annual") |
| Nonrecurring Operating Expense (Annual) | `oper_exp_oth_annual` | YCP("MSFT","oper_exp_oth_annual") |
| Nonrecurring Operating Expense (TTM) | `oper_exp_oth_ttm` | YCP("MSFT","oper_exp_oth_ttm") |
| Normalized Basic EPS (Annual) | `normalized_basic_eps_annual` | YCP("MSFT","normalized_basic_eps_annual") |
| Normalized Basic EPS (TTM) | `normalized_basic_eps_ttm` | YCP("MSFT","normalized_basic_eps_ttm") |
| Normalized Diluted EPS (Annual) | `normalized_eps_annual` | YCP("MSFT","normalized_eps_annual") |
| Normalized Diluted EPS (TTM) | `normalized_eps_ttm` | YCP("MSFT","normalized_eps_ttm") |
| Normalized Income (Annual) | `normalized_income_annual` | YCP("MSFT","normalized_income_annual") |
| Normalized Income (TTM) | `normalized_income_ttm` | YCP("MSFT","normalized_income_ttm") |
| Normalized Net Income Per Employee (Annual) | `norm_ni_per_employee_annual` | YCP("MSFT","norm_ni_per_employee_annual") |
| Normalized PE Ratio (Annual) | `norm_pe_ratio_annual` | YCP("MSFT","norm_pe_ratio_annual") |
| Ohlson Score (Annual) | `ohlson_score_annual` | YCP("MSFT","ohlson_score_annual") |
| Ohlson Score Default Probability (Annual) | `ohlson_score_prob_annual` | YCP("MSFT","ohlson_score_prob_annual") |
| Operating Assets (Annual) | `operating_assets_annual` | YCP("MSFT","operating_assets_annual") |
| Operating Expense Per Employee (Annual) | `op_exp_per_employee_annual` | YCP("MSFT","op_exp_per_employee_annual") |
| Operating Income (Annual) | `operating_income_annual` | YCP("MSFT","operating_income_annual") |
| Operating Income (Quarterly) | `operating_income` | YCP("MSFT","operating_income") |
| Operating Income (TTM) | `operating_income_ttm` | YCP("MSFT","operating_income_ttm") |
| Operating Income After Interest Expense (Annual) | `oper_inc_aft_int_annual` | YCP("MSFT","oper_inc_aft_int_annual") |
| Operating Income After Interest Expense (TTM) | `oper_inc_aft_int_ttm` | YCP("MSFT","oper_inc_aft_int_ttm") |
| Operating Income Before Depreciation Amortization OIBDA (Annual) | `oibda_annual` | YCP("MSFT","oibda_annual") |
| Operating Income Before Interest Expense (Annual) | `oper_inc_bef_int_annual` | YCP("MSFT","oper_inc_bef_int_annual") |
| Operating Income Before Interest Expense (TTM) | `oper_inc_bef_int_ttm` | YCP("MSFT","oper_inc_bef_int_ttm") |
| Operating Income Excluding Securities Gains (Annual) | `operating_income_excluding_securities_gains_annual` | YCP("MSFT","operating_income_excluding_securities_gains_annual") |
| Operating Income Excluding Securities Gains (TTM) | `operating_income_excluding_securities_gains_ttm` | YCP("MSFT","operating_income_excluding_securities_gains_ttm") |
| Operating Interest Expense (Annual) | `interest_expense_oper_annual` | YCP("MSFT","interest_expense_oper_annual") |
| Operating Interest Expense (TTM) | `interest_expense_oper_ttm` | YCP("MSFT","interest_expense_oper_ttm") |
| Operating Interest Income (Annual) | `int_inc_annual` | YCP("MSFT","int_inc_annual") |
| Operating Interest Income (TTM) | `int_inc_ttm` | YCP("MSFT","int_inc_ttm") |
| Operating Interest Paid - Lease Liab (Annual) | `int_oper_cf_annual` | YCP("MSFT","int_oper_cf_annual") |
| Operating Interest Paid - Lease Liab (TTM) | `int_oper_cf_ttm` | YCP("MSFT","int_oper_cf_ttm") |
| Operating Lease Commitments - Over 5 Years (Annual) | `oper_lease_commit_5yr_annual` | YCP("MSFT","oper_lease_commit_5yr_annual") |
| Operating Lease Commitments - Year 1 (Annual) | `oper_lease_commit_yr1_annual` | YCP("MSFT","oper_lease_commit_yr1_annual") |
| Operating Lease Commitments - Year 2 (Annual) | `oper_lease_commit_yr2_annual` | YCP("MSFT","oper_lease_commit_yr2_annual") |
| Operating Lease Commitments - Year 3 (Annual) | `oper_lease_commit_yr3_annual` | YCP("MSFT","oper_lease_commit_yr3_annual") |
| Operating Lease Commitments - Year 4 (Annual) | `oper_lease_commit_yr4_annual` | YCP("MSFT","oper_lease_commit_yr4_annual") |
| Operating Lease Commitments - Year 5 (Annual) | `oper_lease_commit_yr5_annual` | YCP("MSFT","oper_lease_commit_yr5_annual") |
| Operating Lease Commitments 2-5 Years (Annual) | `oper_lease_commit_2yr_5yr_annual` | YCP("MSFT","oper_lease_commit_2yr_5yr_annual") |
| Operating Lease Right-of-Use Assets (Annual) | `assets_lease_net_annual` | YCP("MSFT","assets_lease_net_annual") |
| Operating Margin (Annual) | `operating_margin_annual` | YCP("MSFT","operating_margin_annual") |
| Operating Margin (Quarterly) | `operating_margin` | YCP("MSFT","operating_margin") |
| Operating Margin (TTM) | `operating_margin_ttm` | YCP("MSFT","operating_margin_ttm") |
| Operating PE Ratio (Annual) | `operating_pe_ratio_annual` | YCP("MSFT","operating_pe_ratio_annual") |
| Operating Provisions (Annual) | `oper_prov_annual` | YCP("MSFT","oper_prov_annual") |
| Operating Provisions (TTM) | `oper_prov_ttm` | YCP("MSFT","oper_prov_ttm") |
| Ordinary Shares Number (Annual) | `ordinary_shares_number_annual` | YCP("MSFT","ordinary_shares_number_annual") |
| Other After-Tax Income (Expense) (Annual) | `misc_net_oth_annual` | YCP("MSFT","misc_net_oth_annual") |
| Other After-Tax Income (Expense) (TTM) | `misc_net_oth_ttm` | YCP("MSFT","misc_net_oth_ttm") |
| Other Appropriated Reserves (Annual) | `rsrv_appr_oth_annual` | YCP("MSFT","rsrv_appr_oth_annual") |
| Other Assets & Liabilities - Net Change (Annual) | `wkcap_assets_oth_annual` | YCP("MSFT","wkcap_assets_oth_annual") |
| Other Assets & Liabilities - Net Change (TTM) | `wkcap_assets_oth_ttm` | YCP("MSFT","wkcap_assets_oth_ttm") |
| Other Assets (incl. Intangibles)-Other (Annual) | `assets_oth_intang_annual` | YCP("MSFT","assets_oth_intang_annual") |
| Other Cash Flow Debt (Annual) | `debt_oth_cf_annual` | YCP("MSFT","debt_oth_cf_annual") |
| Other Cash Flow Debt (TTM) | `debt_oth_cf_ttm` | YCP("MSFT","debt_oth_cf_ttm") |
| Other Current Liabilities (Annual) | `liabs_curr_oth_annual` | YCP("MSFT","liabs_curr_oth_annual") |
| Other Funds (Annual) | `invest_activ_oth_annual` | YCP("MSFT","invest_activ_oth_annual") |
| Other Funds (TTM) | `invest_activ_oth_ttm` | YCP("MSFT","invest_activ_oth_ttm") |
| Other Funds - Financing (Annual) | `fin_activ_oth_cf_annual` | YCP("MSFT","fin_activ_oth_cf_annual") |
| Other Funds - Financing (TTM) | `fin_activ_oth_cf_ttm` | YCP("MSFT","fin_activ_oth_cf_ttm") |
| Other Insurance Reserves (Annual) | `ins_liabs_oth_annual` | YCP("MSFT","ins_liabs_oth_annual") |
| Other Intangibles - Impairment (Annual) | `intang_oth_impair_annual` | YCP("MSFT","intang_oth_impair_annual") |
| Other Intangibles - Impairment (TTM) | `intang_oth_impair_ttm` | YCP("MSFT","intang_oth_impair_ttm") |
| Other Interest Expense - Banks (Annual) | `int_exp_oth_annual` | YCP("MSFT","int_exp_oth_annual") |
| Other Interest Expense - Banks (TTM) | `int_exp_oth_ttm` | YCP("MSFT","int_exp_oth_ttm") |
| Other Interest or Dividend Income (Annual) | `int_inc_oth_annual` | YCP("MSFT","int_inc_oth_annual") |
| Other Interest or Dividend Income (TTM) | `int_inc_oth_ttm` | YCP("MSFT","int_inc_oth_ttm") |
| Other Investments (Annual) | `invest_oth_annual` | YCP("MSFT","invest_oth_annual") |
| Other Liabilities (Annual) | `liabs_oth_annual` | YCP("MSFT","liabs_oth_annual") |
| Other Liabilities (excl. Deferred Income) (Annual) | `liabs_oth_xdfd_rev_annual` | YCP("MSFT","liabs_oth_xdfd_rev_annual") |
| Other Non-Performing Assets (Annual) | `assets_nonperf_oth_annual` | YCP("MSFT","assets_nonperf_oth_annual") |
| Other Operating Expenses (Annual) | `oth_unusual_exp_annual` | YCP("MSFT","oth_unusual_exp_annual") |
| Other Operating Expenses (TTM) | `oth_unusual_exp_ttm` | YCP("MSFT","oth_unusual_exp_ttm") |
| Other Operating Income (Annual) | `oper_inc_oth_annual` | YCP("MSFT","oper_inc_oth_annual") |
| Other Operating Income (TTM) | `oper_inc_oth_ttm` | YCP("MSFT","oper_inc_oth_ttm") |
| Other Procds from Sale/Issuance Stock (Annual) | `stk_sale_xopt_cf_annual` | YCP("MSFT","stk_sale_xopt_cf_annual") |
| Other Procds from Sale/Issuance Stock (TTM) | `stk_sale_xopt_cf_ttm` | YCP("MSFT","stk_sale_xopt_cf_ttm") |
| Other Receivables (Annual) | `other_receivables_annual` | YCP("MSFT","other_receivables_annual") |
| Other SG&A Expense (Annual) | `sga_oth_annual` | YCP("MSFT","sga_oth_annual") |
| Other SG&A Expense (TTM) | `sga_oth_ttm` | YCP("MSFT","sga_oth_ttm") |
| Other Securities (Annual) | `secs_oth_annual` | YCP("MSFT","secs_oth_annual") |
| Other Sources - Financing (Annual) | `fin_sources_cf_annual` | YCP("MSFT","fin_sources_cf_annual") |
| Other Sources - Financing (TTM) | `fin_sources_cf_ttm` | YCP("MSFT","fin_sources_cf_ttm") |
| Other Sources - Investing (Annual) | `invest_sources_cf_annual` | YCP("MSFT","invest_sources_cf_annual") |
| Other Sources - Investing (TTM) | `invest_sources_cf_ttm` | YCP("MSFT","invest_sources_cf_ttm") |
| Other Special Charges (Annual) | `oth_xcept_chrg_annual` | YCP("MSFT","oth_xcept_chrg_annual") |
| Other Special Charges (TTM) | `oth_xcept_chrg_ttm` | YCP("MSFT","oth_xcept_chrg_ttm") |
| Other Uses - Financing (Annual) | `fin_uses_cf_annual` | YCP("MSFT","fin_uses_cf_annual") |
| Other Uses - Financing (TTM) | `fin_uses_cf_ttm` | YCP("MSFT","fin_uses_cf_ttm") |
| Other Uses - Investing (Annual) | `invest_uses_cf_annual` | YCP("MSFT","invest_uses_cf_annual") |
| Other Uses - Investing (TTM) | `invest_uses_cf_ttm` | YCP("MSFT","invest_uses_cf_ttm") |
| Owners' Cash Profits (Annual) | `ocp_annual` | YCP("MSFT","ocp_annual") |
| Owners' Cash Profits (TTM) | `ocp_ttm` | YCP("MSFT","ocp_ttm") |
| Owners' Cash Profits Margin (Annual) | `ocp_margin_annual` | YCP("MSFT","ocp_margin_annual") |
| Owners' Cash Profits Margin (TTM) | `ocp_margin_ttm` | YCP("MSFT","ocp_margin_ttm") |
| PE Ratio (Annual) | `pe_ratio_annual` | YCP("MSFT","pe_ratio_annual") |
| PP&E - Computer Software & Equipment (Annual) | `ppe_gross_soft_equip_annual` | YCP("MSFT","ppe_gross_soft_equip_annual") |
| PP&E - Construction in Progress (Annual) | `ppe_gross_constr_annual` | YCP("MSFT","ppe_gross_constr_annual") |
| PP&E - Construction in Progress- Net (Annual) | `ppe_net_constr_annual` | YCP("MSFT","ppe_net_constr_annual") |
| PP&E - Land & Improvements - Net (Annual) | `ppe_net_land_annual` | YCP("MSFT","ppe_net_land_annual") |
| PP&E - Leased Property (Annual) | `ppe_gross_leased_prop_annual` | YCP("MSFT","ppe_gross_leased_prop_annual") |
| PP&E - Leased Property- Net (Annual) | `ppe_net_leased_prop_annual` | YCP("MSFT","ppe_net_leased_prop_annual") |
| PP&E - Leases - Net (Annual) | `ppe_net_leases_annual` | YCP("MSFT","ppe_net_leases_annual") |
| PP&E - Machinery & Equipment - Net (Annual) | `ppe_net_equip_annual` | YCP("MSFT","ppe_net_equip_annual") |
| PP&E - Machinery and Equipment (Annual) | `ppe_gross_equip_annual` | YCP("MSFT","ppe_gross_equip_annual") |
| PP&E - Other (Annual) | `ppe_gross_oth_annual` | YCP("MSFT","ppe_gross_oth_annual") |
| PP&E - Transportation Equipment (Annual) | `ppe_gross_trans_equip_annual` | YCP("MSFT","ppe_gross_trans_equip_annual") |
| PP&E - Transportation Equipment - Net (Annual) | `ppe_net_trans_equip_annual` | YCP("MSFT","ppe_net_trans_equip_annual") |
| PS Ratio (Annual) | `ps_ratio_annual` | YCP("MSFT","ps_ratio_annual") |
| Payout Ratio (Annual) | `payout_ratio_annual` | YCP("MSFT","payout_ratio_annual") |
| Payout Ratio (TTM) | `payout_ratio_ttm` | YCP("MSFT","payout_ratio_ttm") |
| Piotroski F Score (Annual) | `f_score_annual` | YCP("MSFT","f_score_annual") |
| Piotroski F Score (TTM) | `f_score_ttm` | YCP("MSFT","f_score_ttm") |
| Policy and Contract Claims (Annual) | `pol_claims_annual` | YCP("MSFT","pol_claims_annual") |
| Pre-Tax Income (Annual) | `pre_tax_income_annual` | YCP("MSFT","pre_tax_income_annual") |
| Pre-Tax Income (TTM) | `pre_tax_income_ttm` | YCP("MSFT","pre_tax_income_ttm") |
| Preferred Stock (Annual) | `total_preferred_stock_annual` | YCP("MSFT","total_preferred_stock_annual") |
| Preferred Stock Dividend (Annual) | `preferred_stock_div_and_adj_annual` | YCP("MSFT","preferred_stock_div_and_adj_annual") |
| Preferred Stock Dividend (TTM) | `preferred_stock_div_and_adj_ttm` | YCP("MSFT","preferred_stock_div_and_adj_ttm") |
| Preferred Stock Issued For ESOP (Annual) | `pfd_stk_esop_annual` | YCP("MSFT","pfd_stk_esop_annual") |
| Premium Balance Receivables (Annual) | `prem_receiv_annual` | YCP("MSFT","prem_receiv_annual") |
| Premiums Earned (Annual) | `prem_earn_annual` | YCP("MSFT","prem_earn_annual") |
| Premiums Earned (TTM) | `prem_earn_ttm` | YCP("MSFT","prem_earn_ttm") |
| Prepaid Expenses (Annual) | `prepaid_expenses_annual` | YCP("MSFT","prepaid_expenses_annual") |
| Prepayment Turnover (Annual) | `prepayment_turnover_annual` | YCP("MSFT","prepayment_turnover_annual") |
| Prepayment Turnover (TTM) | `prepayment_turnover_ttm` | YCP("MSFT","prepayment_turnover_ttm") |
| Pretax Equity In Earnings (Annual) | `eq_aff_inc_ptx_annual` | YCP("MSFT","eq_aff_inc_ptx_annual") |
| Pretax Equity In Earnings (TTM) | `eq_aff_inc_ptx_ttm` | YCP("MSFT","eq_aff_inc_ptx_ttm") |
| Price to CFO Per Share (TTM) | `price_to_cfo_ttm` | YCP("MSFT","price_to_cfo_ttm") |
| Price to Earnings Less Cash (TTM) | `pe_less_cash_ratio_ttm` | YCP("MSFT","pe_less_cash_ratio_ttm") |
| Price to Free Cash Flow (TTM) | `price_to_cash_flow_ttm` | YCP("MSFT","price_to_cash_flow_ttm") |
| Price to Free Cash Flow (Annual) | `price_to_cash_flow_annual` | YCP("MSFT","price_to_cash_flow_annual") |
| Price to Normalized Earnings Less Cash (TTM) | `pne_less_cash_ratio_ttm` | YCP("MSFT","pne_less_cash_ratio_ttm") |
| Proceeds from Loans (Annual) | `loan_chg_cf_annual` | YCP("MSFT","loan_chg_cf_annual") |
| Proceeds from Loans (TTM) | `loan_chg_cf_ttm` | YCP("MSFT","loan_chg_cf_ttm") |
| Proceeds from Stock Option Exercised (Annual) | `proceeds_from_stock_option_exercised_annual` | YCP("MSFT","proceeds_from_stock_option_exercised_annual") |
| Proceeds from Stock Option Exercised (TTM) | `proceeds_from_stock_option_exercised_ttm` | YCP("MSFT","proceeds_from_stock_option_exercised_ttm") |
| Profit Margin (TTM) | `profit_margin_ttm` | YCP("MSFT","profit_margin_ttm") |
| Profit Margin (Annual) | `profit_margin_annual` | YCP("MSFT","profit_margin_annual") |
| Provision for Bad Debt (Annual) | `bdebt_annual` | YCP("MSFT","bdebt_annual") |
| Provision for Income Taxes (Annual) | `provision_for_income_taxes_annual` | YCP("MSFT","provision_for_income_taxes_annual") |
| Provision for Income Taxes (TTM) | `provision_for_income_taxes_ttm` | YCP("MSFT","provision_for_income_taxes_ttm") |
| Provision for Loan Losses (Annual) | `loan_loss_prov_annual` | YCP("MSFT","loan_loss_prov_annual") |
| Provision for Loan Losses (TTM) | `loan_loss_prov_ttm` | YCP("MSFT","loan_loss_prov_ttm") |
| Provisions for Risk and Charges (Annual) | `prov_risk_annual` | YCP("MSFT","prov_risk_annual") |
| Purchase of Investments (Annual) | `invest_purch_cf_annual` | YCP("MSFT","invest_purch_cf_annual") |
| Purchase of Investments (TTM) | `invest_purch_cf_ttm` | YCP("MSFT","invest_purch_cf_ttm") |
| Quality Ratio (Annual) | `quality_ratio_annual` | YCP("MSFT","quality_ratio_annual") |
| Quick Ratio (Annual) | `quick_ratio_annual` | YCP("MSFT","quick_ratio_annual") |
| R&D to Revenue (TTM) | `rnd_to_revenue_ttm` | YCP("MSFT","rnd_to_revenue_ttm") |
| Raw Materials Inventory (Annual) | `raw_materials_annual` | YCP("MSFT","raw_materials_annual") |
| Real Estate Assets (Annual) | `invest_re_annual` | YCP("MSFT","invest_re_annual") |
| Real Estate Mortgage Loans (Annual) | `loan_mtge_annual` | YCP("MSFT","loan_mtge_annual") |
| Realized Gains (Losses) (Annual) | `real_gain_annual` | YCP("MSFT","real_gain_annual") |
| Realized Gains (Losses) (TTM) | `real_gain_ttm` | YCP("MSFT","real_gain_ttm") |
| Receivables Days (Annual) | `receiv_turn_days_annual` | YCP("MSFT","receiv_turn_days_annual") |
| Receivables Turnover (Annual) | `receivables_turnover_annual` | YCP("MSFT","receivables_turnover_annual") |
| Receivables Turnover (TTM) | `receivables_turnover_ttm` | YCP("MSFT","receivables_turnover_ttm") |
| Redeemable Preferred Stock (Annual) | `invest_pfd_red_annual` | YCP("MSFT","invest_pfd_red_annual") |
| Reduction In Long-Term Debt (Annual) | `debt_lt_reduct_cf_annual` | YCP("MSFT","debt_lt_reduct_cf_annual") |
| Reduction In Long-Term Debt (TTM) | `debt_lt_reduct_cf_ttm` | YCP("MSFT","debt_lt_reduct_cf_ttm") |
| Rent and Landing Expense (Annual) | `rent_and_landing_fees_annual` | YCP("MSFT","rent_and_landing_fees_annual") |
| Rent and Landing Expense (TTM) | `rent_and_landing_fees_ttm` | YCP("MSFT","rent_and_landing_fees_ttm") |
| Rental Income (Annual) | `rent_inc_annual` | YCP("MSFT","rent_inc_annual") |
| Rental Income (TTM) | `rent_inc_ttm` | YCP("MSFT","rent_inc_ttm") |
| Repayments Of Operating Lease Liabilities (Annual) | `oper_lease_repay_annual` | YCP("MSFT","oper_lease_repay_annual") |
| Repayments Of Operating Lease Liabilities (TTM) | `oper_lease_repay_ttm` | YCP("MSFT","oper_lease_repay_ttm") |
| Repurchase of Capital Stock (Annual) | `repurchase_of_capital_stock_annual` | YCP("MSFT","repurchase_of_capital_stock_annual") |
| Repurchase of Capital Stock (TTM) | `repurchase_of_capital_stock_ttm` | YCP("MSFT","repurchase_of_capital_stock_ttm") |
| Research and Development Expense (Annual) | `r_and_d_expense_annual` | YCP("MSFT","r_and_d_expense_annual") |
| Research and Development Expense (TTM) | `r_and_d_expense_ttm` | YCP("MSFT","r_and_d_expense_ttm") |
| Reserve For Loan Losses (Annual) | `loan_rsrv_annual` | YCP("MSFT","loan_rsrv_annual") |
| Reserves - Increase/Decrease (Annual) | `rsrv_chg_annual` | YCP("MSFT","rsrv_chg_annual") |
| Reserves - Increase/Decrease (TTM) | `rsrv_chg_ttm` | YCP("MSFT","rsrv_chg_ttm") |
| Restricted Cash (Annual) | `restricted_cash_annual` | YCP("MSFT","restricted_cash_annual") |
| Restructuring / M&A Expense (Annual) | `restruct_exp_annual` | YCP("MSFT","restruct_exp_annual") |
| Restructuring / M&A Expense (TTM) | `restruct_exp_ttm` | YCP("MSFT","restruct_exp_ttm") |
| Restructuring of Debt (Annual) | `restruct_debt_annual` | YCP("MSFT","restruct_debt_annual") |
| Restructuring of Debt (TTM) | `restruct_debt_ttm` | YCP("MSFT","restruct_debt_ttm") |
| Retained Earnings (Annual) | `retained_earnings_annual` | YCP("MSFT","retained_earnings_annual") |
| Retention Ratio (Annual) | `retention_ratio_annual` | YCP("MSFT","retention_ratio_annual") |
| Return on Assets (Annual) | `return_on_assets_annual` | YCP("MSFT","return_on_assets_annual") |
| Return on Capital Employed (Annual) | `roce_annual` | YCP("MSFT","roce_annual") |
| Return on Equity (Annual) | `return_on_equity_annual` | YCP("MSFT","return_on_equity_annual") |
| Return on Invested Capital (Annual) | `return_on_invested_capital_annual` | YCP("MSFT","return_on_invested_capital_annual") |
| Return on Net Operating Assets (Annual) | `rnoa_annual` | YCP("MSFT","rnoa_annual") |
| Revaluation Reserve (Annual) | `rsrv_reval_annual` | YCP("MSFT","rsrv_reval_annual") |
| Revenue (Annual) | `revenues_annual` | YCP("MSFT","revenues_annual") |
| Revenue (Quarterly) | `revenues` | YCP("MSFT","revenues") |
| Revenue (TTM) | `revenues_ttm` | YCP("MSFT","revenues_ttm") |
| Revenue Per Employee (Annual) | `revenue_per_employee_annual` | YCP("MSFT","revenue_per_employee_annual") |
| Revenue Per Share (TTM) | `revenue_per_share_ttm` | YCP("MSFT","revenue_per_share_ttm") |
| SG&A (Annual) | `sga_annual` | YCP("MSFT","sga_annual") |
| SG&A (Quarterly) | `sga` | YCP("MSFT","sga") |
| SG&A (TTM) | `sga_ttm` | YCP("MSFT","sga_ttm") |
| SG&A Expense (Annual) | `sga_expense_annual` | YCP("MSFT","sga_expense_annual") |
| SG&A Expense (TTM) | `sga_expense_ttm` | YCP("MSFT","sga_expense_ttm") |
| SG&A to Revenue (TTM) | `sga_to_revenue_ttm` | YCP("MSFT","sga_to_revenue_ttm") |
| SGA Expense Per Employee (Annual) | `sga_exp_per_employee_annual` | YCP("MSFT","sga_exp_per_employee_annual") |
| ST Debt & Current Portion Of LT Debt (Annual) | `debt_st_annual` | YCP("MSFT","debt_st_annual") |
| Salary & Wage Expense (Annual) | `labor_exp_annual` | YCP("MSFT","labor_exp_annual") |
| Salary & Wage Expense (TTM) | `labor_exp_ttm` | YCP("MSFT","labor_exp_ttm") |
| Sale of Fixed Assets & Businesses (Annual) | `sale_assets_bus_cf_annual` | YCP("MSFT","sale_assets_bus_cf_annual") |
| Sale of Fixed Assets & Businesses (TTM) | `sale_assets_bus_cf_ttm` | YCP("MSFT","sale_assets_bus_cf_ttm") |
| Sale of PPE (Annual) | `sale_of_ppe_annual` | YCP("MSFT","sale_of_ppe_annual") |
| Sale of PPE (TTM) | `sale_of_ppe_ttm` | YCP("MSFT","sale_of_ppe_ttm") |
| Sale/Maturity of Investments (Annual) | `invest_sale_cf_annual` | YCP("MSFT","invest_sale_cf_annual") |
| Sale/Maturity of Investments (TTM) | `invest_sale_cf_ttm` | YCP("MSFT","invest_sale_cf_ttm") |
| Sales and Direct Financing Leases (Annual) | `dir_fin_lease_annual` | YCP("MSFT","dir_fin_lease_annual") |
| Sales and Marketing Expense (Annual) | `selling_and_marketing_expense_annual` | YCP("MSFT","selling_and_marketing_expense_annual") |
| Sales and Marketing Expense (TTM) | `selling_and_marketing_expense_ttm` | YCP("MSFT","selling_and_marketing_expense_ttm") |
| Savings/Other Time Deposits (Annual) | `deps_sav_annual` | YCP("MSFT","deps_sav_annual") |
| Securities Inventory (Annual) | `secs_invest_annual` | YCP("MSFT","secs_invest_annual") |
| Securities Purchased Under Resale Agreements (Annual) | `secs_resale_annual` | YCP("MSFT","secs_resale_annual") |
| Selling, Gen & Admin Expense & Other (Annual) | `sga_oth_exp_annual` | YCP("MSFT","sga_oth_exp_annual") |
| Selling, Gen & Admin Expense & Other (TTM) | `sga_oth_exp_ttm` | YCP("MSFT","sga_oth_exp_ttm") |
| Separate and Variable Account Assets (Annual) | `assets_sep_accts_annual` | YCP("MSFT","assets_sep_accts_annual") |
| Shareholder Yield (Annual) | `shareholder_yield_annual` | YCP("MSFT","shareholder_yield_annual") |
| Shareholder Yield (TTM) | `shareholder_yield_ttm` | YCP("MSFT","shareholder_yield_ttm") |
| Shareholders Equity (Annual) | `shareholders_equity_annual` | YCP("MSFT","shareholders_equity_annual") |
| Short-Term Receivables (Annual) | `receiv_st_annual` | YCP("MSFT","receiv_st_annual") |
| Springate Score (Annual) | `springate_score_annual` | YCP("MSFT","springate_score_annual") |
| State and Municipal Securities (Annual) | `secs_muni_annual` | YCP("MSFT","secs_muni_annual") |
| Stock Based Compensation (Annual) | `stock_based_compensation_annual` | YCP("MSFT","stock_based_compensation_annual") |
| Stock Based Compensation (TTM) | `stock_based_compensation_ttm` | YCP("MSFT","stock_based_compensation_ttm") |
| Stock Buyback (Annual) | `stock_buyback_annual` | YCP("MSFT","stock_buyback_annual") |
| Stock Buybacks (TTM) | `stock_buybacks_ttm` | YCP("MSFT","stock_buybacks_ttm") |
| Stock-Based Compensation Adjustment to Net Income (Annual) | `stk_opt_exp_adj_annual` | YCP("MSFT","stk_opt_exp_adj_annual") |
| Stock-Based Compensation Expense (Annual) | `stk_opt_exp_annual` | YCP("MSFT","stk_opt_exp_annual") |
| Tangible Book Value (Annual) | `book_value_of_tangible_equity_annual` | YCP("MSFT","book_value_of_tangible_equity_annual") |
| Tangible Book Value Per Share (Annual) | `bps_tang_annual` | YCP("MSFT","bps_tang_annual") |
| Tangible Common Equity Ratio (Annual) | `tangible_common_equity_ratio_annual` | YCP("MSFT","tangible_common_equity_ratio_annual") |
| Tangible Other Assets (Annual) | `assets_oth_tang_annual` | YCP("MSFT","assets_oth_tang_annual") |
| Taxes Other Than Income Taxes (Annual) | `tax_non_inc_annual` | YCP("MSFT","tax_non_inc_annual") |
| Taxes Other Than Income Taxes (TTM) | `tax_non_inc_ttm` | YCP("MSFT","tax_non_inc_ttm") |
| Tier 1 Capital (Annual) | `tier1_cap_annual` | YCP("MSFT","tier1_cap_annual") |
| Tier 2 Capital (Annual) | `tier2_cap_annual` | YCP("MSFT","tier2_cap_annual") |
| Times Interest Earned (Annual) | `times_interest_earned_annual` | YCP("MSFT","times_interest_earned_annual") |
| Tobin's Q (Approximate) (Annual) | `tobin_q_annual` | YCP("MSFT","tobin_q_annual") |
| Total Assets (Annual) | `assets_annual` | YCP("MSFT","assets_annual") |
| Total Capital Stock (Annual) | `capital_stock_annual` | YCP("MSFT","capital_stock_annual") |
| Total Capital, Including Short-Term Debt (Annual) | `tcap_annual` | YCP("MSFT","tcap_annual") |
| Total Common Dividends Paid (Annual) | `common_stock_dividends_paid_annual` | YCP("MSFT","common_stock_dividends_paid_annual") |
| Total Common Dividends Paid (TTM) | `common_stock_dividends_paid_ttm` | YCP("MSFT","common_stock_dividends_paid_ttm") |
| Total Current Assets (Annual) | `total_current_assets_annual` | YCP("MSFT","total_current_assets_annual") |
| Total Current Liabilities (Annual) | `total_current_liabilities_annual` | YCP("MSFT","total_current_liabilities_annual") |
| Total Debt (Annual) | `debt_annual` | YCP("MSFT","debt_annual") |
| Total Depreciation and Amortization (Annual) | `total_depr_and_amortization_annual` | YCP("MSFT","total_depr_and_amortization_annual") |
| Total Depreciation and Amortization (TTM) | `total_depr_and_amortization_ttm` | YCP("MSFT","total_depr_and_amortization_ttm") |
| Total Dividends Paid (Annual) | `total_stock_dividends_paid_annual` | YCP("MSFT","total_stock_dividends_paid_annual") |
| Total Dividends Paid (TTM) | `total_stock_dividends_paid_ttm` | YCP("MSFT","total_stock_dividends_paid_ttm") |
| Total Equity Including Minority Interest (Annual) | `total_equity_gross_minority_interest_annual` | YCP("MSFT","total_equity_gross_minority_interest_annual") |
| Total Equity Turnover (Annual) | `total_equity_turnover_annual` | YCP("MSFT","total_equity_turnover_annual") |
| Total Expenses (Annual) | `expenses_annual` | YCP("MSFT","expenses_annual") |
| Total Expenses (TTM) | `expenses_ttm` | YCP("MSFT","expenses_ttm") |
| Total Fixed Income Securities Investment (Annual) | `invest_fix_inc_annual` | YCP("MSFT","invest_fix_inc_annual") |
| Total Interest Expense (Quarterly) | `interest_expense` | YCP("MSFT","interest_expense") |
| Total Interest Expense (TTM) | `interest_expense_ttm` | YCP("MSFT","interest_expense_ttm") |
| Total Investments (Annual) | `bk_invest_tot_annual` | YCP("MSFT","bk_invest_tot_annual") |
| Total Liabilities (Annual) | `liabilities_annual` | YCP("MSFT","liabilities_annual") |
| Total Liabilities And Shareholders' Equity (Annual) | `liabs_shldrs_eq_annual` | YCP("MSFT","liabs_shldrs_eq_annual") |
| Total Long Term Debt (Annual) | `total_long_term_debt_annual` | YCP("MSFT","total_long_term_debt_annual") |
| Total Long Term Liabilities (Annual) | `total_long_term_liab_annual` | YCP("MSFT","total_long_term_liab_annual") |
| Total Net Change in Investments (Annual) | `net_change_in_invest_total_annual` | YCP("MSFT","net_change_in_invest_total_annual") |
| Total Net Change in Investments (TTM) | `net_change_in_invest_total_ttm` | YCP("MSFT","net_change_in_invest_total_ttm") |
| Total Non-Performing Assets (Annual) | `assets_nonperf_annual` | YCP("MSFT","assets_nonperf_annual") |
| Total Operating Expenses (Annual) | `exp_tot_annual` | YCP("MSFT","exp_tot_annual") |
| Total Operating Expenses (TTM) | `exp_tot_ttm` | YCP("MSFT","exp_tot_ttm") |
| Total Operating Lease Commitments (Annual) | `oper_lease_commit_tot_annual` | YCP("MSFT","oper_lease_commit_tot_annual") |
| Total Preferred Dividends Paid (Annual) | `preferred_stock_dividends_paid_annual` | YCP("MSFT","preferred_stock_dividends_paid_annual") |
| Total Preferred Dividends Paid (TTM) | `preferred_stock_dividends_paid_ttm` | YCP("MSFT","preferred_stock_dividends_paid_ttm") |
| Total Receivables (Annual) | `receivables_annual` | YCP("MSFT","receivables_annual") |
| Total Short-term Investments (Annual) | `invest_st_tot_annual` | YCP("MSFT","invest_st_tot_annual") |
| Trading Account Income (Annual) | `trade_inc_annual` | YCP("MSFT","trade_inc_annual") |
| Trading Account Income (TTM) | `trade_inc_ttm` | YCP("MSFT","trade_inc_ttm") |
| Trading Account Securities (Annual) | `trade_acct_annual` | YCP("MSFT","trade_acct_annual") |
| Treasury Securities (Annual) | `secs_treas_annual` | YCP("MSFT","secs_treas_annual") |
| Treasury Stock (Annual) | `treasury_stock_annual` | YCP("MSFT","treasury_stock_annual") |
| Trust & Fiduciary Inc, Comm & Fees (Annual) | `trust_commiss_inc_annual` | YCP("MSFT","trust_commiss_inc_annual") |
| Trust & Fiduciary Inc, Comm & Fees (TTM) | `trust_commiss_inc_ttm` | YCP("MSFT","trust_commiss_inc_ttm") |
| Trust Income (Annual) | `trust_inc_annual` | YCP("MSFT","trust_inc_annual") |
| Trust Income (TTM) | `trust_inc_ttm` | YCP("MSFT","trust_inc_ttm") |
| Unappropriated Reserves (Annual) | `rsrv_unappr_annual` | YCP("MSFT","rsrv_unappr_annual") |
| Underwriting Expense (Annual) | `underwriting_exp_annual` | YCP("MSFT","underwriting_exp_annual") |
| Underwriting Expense (TTM) | `underwriting_exp_ttm` | YCP("MSFT","underwriting_exp_ttm") |
| Unearned Income (Annual) | `inc_unearn_annual` | YCP("MSFT","inc_unearn_annual") |
| Unearned Premiums (Annual) | `prem_unearn_annual` | YCP("MSFT","prem_unearn_annual") |
| Unrealized Gain or Loss - Total (Annual) | `unrealized_gain_loss_annual` | YCP("MSFT","unrealized_gain_loss_annual") |
| Unrealized Gain/Loss - Bio Assets (Annual) | `unreal_gl_bio_assets_annual` | YCP("MSFT","unreal_gl_bio_assets_annual") |
| Unrealized Gain/Loss - Bio Assets (TTM) | `unreal_gl_bio_assets_ttm` | YCP("MSFT","unreal_gl_bio_assets_ttm") |
| Unrealized Gain/Loss - Hdgs/Derivs (Annual) | `unreal_gl_deriv_annual` | YCP("MSFT","unreal_gl_deriv_annual") |
| Unrealized Gain/Loss - Hdgs/Derivs (TTM) | `unreal_gl_deriv_ttm` | YCP("MSFT","unreal_gl_deriv_ttm") |
| Unrealized Gain/Loss - Inv. Prop. (Annual) | `unreal_gl_prop_annual` | YCP("MSFT","unreal_gl_prop_annual") |
| Unrealized Gain/Loss - Inv. Prop. (TTM) | `unreal_gl_prop_ttm` | YCP("MSFT","unreal_gl_prop_ttm") |
| Unrealized Gain/Loss - Inv. Sec. (Annual) | `unreal_gl_invest_annual` | YCP("MSFT","unreal_gl_invest_annual") |
| Unrealized Gain/Loss - Inv. Sec. (TTM) | `unreal_gl_invest_ttm` | YCP("MSFT","unreal_gl_invest_ttm") |
| Unrealized Gain/Loss - Other (Annual) | `unreal_gl_oth_annual` | YCP("MSFT","unreal_gl_oth_annual") |
| Unrealized Gain/Loss - Other (TTM) | `unreal_gl_oth_ttm` | YCP("MSFT","unreal_gl_oth_ttm") |
| Unrealized Gain/Loss - Total (Annual) | `unreal_gl_tot_annual` | YCP("MSFT","unreal_gl_tot_annual") |
| Unrealized Gain/Loss - Total (TTM) | `unreal_gl_tot_ttm` | YCP("MSFT","unreal_gl_tot_ttm") |
| Unspecified Deposits (Annual) | `deps_unspec_annual` | YCP("MSFT","deps_unspec_annual") |
| Unspecified/Other Loans (Annual) | `loan_oth_annual` | YCP("MSFT","loan_oth_annual") |
| Unusual Expense - Net (Annual) | `unusual_exp_annual` | YCP("MSFT","unusual_exp_annual") |
| Unusual Expense - Net (TTM) | `unusual_exp_ttm` | YCP("MSFT","unusual_exp_ttm") |
| Work in Process Inventory (Annual) | `work_in_process_annual` | YCP("MSFT","work_in_process_annual") |
| Working Capital (Annual) | `working_capital_annual` | YCP("MSFT","working_capital_annual") |
| Working Capital - Total (Net Working Capital) (Annual) | `wkcap_annual` | YCP("MSFT","wkcap_annual") |
| Working Capital Turnover (Annual) | `working_capital_turnover_annual` | YCP("MSFT","working_capital_turnover_annual") |
| Working Capital Turnover (TTM) | `working_capital_turnover_ttm` | YCP("MSFT","working_capital_turnover_ttm") |
| Zmijewski Score (Annual) | `zmijewski_score_annual` | YCP("MSFT","zmijewski_score_annual") |

---

## 6. Balance Sheet (Companies)

| Metric | Code | Example |
|---|---|---|
| Accounts Payable (% of Annual Assets) | `accounts_payable_annual_cs_ast` | YCP("MSFT","accounts_payable_annual_cs_ast") |
| Accounts Payable (% of Quarterly Assets) | `accounts_payable_cs_ast` | YCP("MSFT","accounts_payable_cs_ast") |
| Accounts Payable (Annual Per Share) | `accounts_payable_annual_per_share` | YCP("MSFT","accounts_payable_annual_per_share") |
| Accounts Payable (Annual) | `accounts_payable_annual` | YCP("MSFT","accounts_payable_annual") |
| Accounts Payable (Per Share Quarterly) | `accounts_payable_per_share` | YCP("MSFT","accounts_payable_per_share") |
| Accounts Payable (Quarterly) | `accounts_payable` | YCP("MSFT","accounts_payable") |
| Accounts Payable (Semi Annual) | `accounts_payable_sa` | YCP("MSFT","accounts_payable_sa") |
| Accounts Receivable (% of Annual Assets) | `accounts_receivable_annual_cs_ast` | YCP("MSFT","accounts_receivable_annual_cs_ast") |
| Accounts Receivable (% of Quarterly Assets) | `accounts_receivable_cs_ast` | YCP("MSFT","accounts_receivable_cs_ast") |
| Accounts Receivable (Annual Per Share) | `accounts_receivable_annual_per_share` | YCP("MSFT","accounts_receivable_annual_per_share") |
| Accounts Receivable (Annual) | `accounts_receivable_annual` | YCP("MSFT","accounts_receivable_annual") |
| Accounts Receivable (Per Share Quarterly) | `accounts_receivable_per_share` | YCP("MSFT","accounts_receivable_per_share") |
| Accounts Receivable (Quarterly) | `accounts_receivable` | YCP("MSFT","accounts_receivable") |
| Accounts Receivable (Semi Annual) | `accounts_receivable_sa` | YCP("MSFT","accounts_receivable_sa") |
| Book Value (% of Annual Assets) | `book_value_of_equity_annual_cs_ast` | YCP("MSFT","book_value_of_equity_annual_cs_ast") |
| Book Value (% of Quarterly Assets) | `book_value_of_equity_cs_ast` | YCP("MSFT","book_value_of_equity_cs_ast") |
| Book Value (Annual Per Share) | `book_value_of_equity_annual_per_share` | YCP("MSFT","book_value_of_equity_annual_per_share") |
| Book Value (Annual) | `book_value_of_equity_annual` | YCP("MSFT","book_value_of_equity_annual") |
| Book Value (Per Share Quarterly) | `book_value_of_equity_per_share` | YCP("MSFT","book_value_of_equity_per_share") |
| Book Value (Quarterly) | `book_value_of_equity` | YCP("MSFT","book_value_of_equity") |
| Book Value (Semi Annual) | `book_value_of_equity_sa` | YCP("MSFT","book_value_of_equity_sa") |
| Cash and Short Term Investments (% of Annual Assets) | `cash_on_hand_annual_cs_ast` | YCP("MSFT","cash_on_hand_annual_cs_ast") |
| Cash and Short Term Investments (% of Quarterly Assets) | `cash_on_hand_cs_ast` | YCP("MSFT","cash_on_hand_cs_ast") |
| Cash and Short Term Investments (Annual Per Share) | `cash_on_hand_annual_per_share` | YCP("MSFT","cash_on_hand_annual_per_share") |
| Cash and Short Term Investments (Annual) | `cash_on_hand_annual` | YCP("MSFT","cash_on_hand_annual") |
| Cash and Short Term Investments (Per Share Quarterly) | `cash_on_hand_per_share` | YCP("MSFT","cash_on_hand_per_share") |
| Cash and Short Term Investments (Quarterly) | `cash_on_hand` | YCP("MSFT","cash_on_hand") |
| Cash and Short Term Investments (Semi Annual) | `cash_on_hand_sa` | YCP("MSFT","cash_on_hand_sa") |
| Goodwill and Intangibles (% of Annual Assets) | `goodwill_and_intangible_annual_cs_ast` | YCP("MSFT","goodwill_and_intangible_annual_cs_ast") |
| Goodwill and Intangibles (% of Quarterly Assets) | `goodwill_and_intangible_cs_ast` | YCP("MSFT","goodwill_and_intangible_cs_ast") |
| Goodwill and Intangibles (Annual Per Share) | `goodwill_and_intangible_annual_per_share` | YCP("MSFT","goodwill_and_intangible_annual_per_share") |
| Goodwill and Intangibles (Annual) | `goodwill_and_intangible_annual` | YCP("MSFT","goodwill_and_intangible_annual") |
| Goodwill and Intangibles (Per Share Quarterly) | `goodwill_and_intangible_per_share` | YCP("MSFT","goodwill_and_intangible_per_share") |
| Goodwill and Intangibles (Quarterly) | `goodwill_and_intangible` | YCP("MSFT","goodwill_and_intangible") |
| Goodwill and Intangibles (Semi Annual) | `goodwill_and_intangible_sa` | YCP("MSFT","goodwill_and_intangible_sa") |
| Inventory Turnover (Annual) | `inventory_turnover_annual` | YCP("MSFT","inventory_turnover_annual") |
| Inventory Turnover (Quarterly) | `inventory_turnover` | YCP("MSFT","inventory_turnover") |
| Inventory Turnover (TTM) | `inventory_turnover_ttm` | YCP("MSFT","inventory_turnover_ttm") |
| Net Debt (% of Annual Assets) | `net_debt_annual_cs_ast` | YCP("MSFT","net_debt_annual_cs_ast") |
| Net Debt (% of Quarterly Assets) | `net_debt_cs_ast` | YCP("MSFT","net_debt_cs_ast") |
| Net Debt (Annual Per Share) | `net_debt_annual_per_share` | YCP("MSFT","net_debt_annual_per_share") |
| Net Debt (Annual) | `net_debt_annual` | YCP("MSFT","net_debt_annual") |
| Net Debt (Per Share Quarterly) | `net_debt_per_share` | YCP("MSFT","net_debt_per_share") |
| Net Debt (Quarterly) | `net_debt` | YCP("MSFT","net_debt") |
| Net Debt (Semi Annual) | `net_debt_sa` | YCP("MSFT","net_debt_sa") |
| Net Debt Paydown Yield (TTM) | `net_debt_paydown_yield_ttm` | YCP("MSFT","net_debt_paydown_yield_ttm") |
| Net Debt Paydown Yield (Annual) | `net_debt_paydown_yield_annual` | YCP("MSFT","net_debt_paydown_yield_annual") |
| Non-Current Portion of Long Term Debt (% of Annual Assets) | `long_term_debt_annual_cs_ast` | YCP("MSFT","long_term_debt_annual_cs_ast") |
| Non-Current Portion of Long Term Debt (% of Quarterly Assets) | `long_term_debt_cs_ast` | YCP("MSFT","long_term_debt_cs_ast") |
| Non-Current Portion of Long Term Debt (Annual Per Share) | `long_term_debt_annual_per_share` | YCP("MSFT","long_term_debt_annual_per_share") |
| Non-Current Portion of Long Term Debt (Annual) | `long_term_debt_annual` | YCP("MSFT","long_term_debt_annual") |
| Non-Current Portion of Long Term Debt (Per Share Quarterly) | `long_term_debt_per_share` | YCP("MSFT","long_term_debt_per_share") |
| Non-Current Portion of Long Term Debt (Quarterly) | `long_term_debt` | YCP("MSFT","long_term_debt") |
| Non-Current Portion of Long Term Debt (Semi Annual) | `long_term_debt_sa` | YCP("MSFT","long_term_debt_sa") |
| Retained Earnings (% of Annual Assets) | `retained_earnings_annual_cs_ast` | YCP("MSFT","retained_earnings_annual_cs_ast") |
| Retained Earnings (% of Quarterly Assets) | `retained_earnings_cs_ast` | YCP("MSFT","retained_earnings_cs_ast") |
| Retained Earnings (Annual Per Share) | `retained_earnings_annual_per_share` | YCP("MSFT","retained_earnings_annual_per_share") |
| Retained Earnings (Annual) | `retained_earnings_annual` | YCP("MSFT","retained_earnings_annual") |
| Retained Earnings (Per Share Quarterly) | `retained_earnings_per_share` | YCP("MSFT","retained_earnings_per_share") |
| Retained Earnings (Quarterly) | `retained_earnings` | YCP("MSFT","retained_earnings") |
| Retained Earnings (Semi Annual) | `retained_earnings_sa` | YCP("MSFT","retained_earnings_sa") |
| Shares Outstanding | `shares_outstanding` | YCP("MSFT","shares_outstanding") |
| Tangible Book Value (% of Annual Assets) | `book_value_of_tangible_equity_annual_cs_ast` | YCP("MSFT","book_value_of_tangible_equity_annual_cs_ast") |
| Tangible Book Value (% of Quarterly Assets) | `book_value_of_tangible_equity_cs_ast` | YCP("MSFT","book_value_of_tangible_equity_cs_ast") |
| Tangible Book Value (Annual Per Share) | `book_value_of_tangible_equity_annual_per_share` | YCP("MSFT","book_value_of_tangible_equity_annual_per_share") |
| Tangible Book Value (Annual) | `book_value_of_tangible_equity_annual` | YCP("MSFT","book_value_of_tangible_equity_annual") |
| Tangible Book Value (Per Share Quarterly) | `book_value_of_tangible_equity_per_share` | YCP("MSFT","book_value_of_tangible_equity_per_share") |
| Tangible Book Value (Quarterly) | `book_value_of_tangible_equity` | YCP("MSFT","book_value_of_tangible_equity") |
| Tangible Book Value (Semi Annual) | `book_value_of_tangible_equity_sa` | YCP("MSFT","book_value_of_tangible_equity_sa") |
| Total Equity Including Minority Interest (% of Annual Assets) | `total_equity_gross_minority_interest_annual_cs_ast` | YCP("MSFT","total_equity_gross_minority_interest_annual_cs_ast") |
| Total Equity Including Minority Interest (% of Quarterly Assets) | `total_equity_gross_minority_interest_cs_ast` | YCP("MSFT","total_equity_gross_minority_interest_cs_ast") |
| Total Equity Including Minority Interest (Annual Per Share) | `total_equity_gross_minority_interest_annual_per_share` | YCP("MSFT","total_equity_gross_minority_interest_annual_per_share") |
| Total Equity Including Minority Interest (Annual) | `total_equity_gross_minority_interest_annual` | YCP("MSFT","total_equity_gross_minority_interest_annual") |
| Total Equity Including Minority Interest (Per Share Quarterly) | `total_equity_gross_minority_interest_per_share` | YCP("MSFT","total_equity_gross_minority_interest_per_share") |
| Total Equity Including Minority Interest (Quarterly) | `total_equity_gross_minority_interest` | YCP("MSFT","total_equity_gross_minority_interest") |
| Total Equity Including Minority Interest (Semi Annual) | `total_equity_gross_minority_interest_sa` | YCP("MSFT","total_equity_gross_minority_interest_sa") |
| Total Equity Turnover (Annual) | `total_equity_turnover_annual` | YCP("MSFT","total_equity_turnover_annual") |
| Total Equity Turnover (TTM) | `total_equity_turnover` | YCP("MSFT","total_equity_turnover") |
| Working Capital (Annual) | `working_capital_annual` | YCP("MSFT","working_capital_annual") |
| Working Capital (Quarterly) | `working_capital` | YCP("MSFT","working_capital") |
| Working Capital Turnover (Annual) | `working_capital_turnover_annual` | YCP("MSFT","working_capital_turnover_annual") |
| Working Capital Turnover (Quarterly) | `working_capital_turnover` | YCP("MSFT","working_capital_turnover") |
| Working Capital Turnover (TTM) | `working_capital_turnover_ttm` | YCP("MSFT","working_capital_turnover_ttm") |

---

## 7. Cash Flow Statement (Companies)

| Metric | Code | Example |
|---|---|---|
| CAPEX To Revenue (TTM) | `capex_to_revenue_ttm` | YCP("MSFT","capex_to_revenue_ttm") |
| CAPEX to Revenue (Quarterly) | `capex_to_revenue` | YCP("MSFT","capex_to_revenue") |
| CAPEX to Revenue (Annual) | `capex_to_revenue_annual` | YCP("MSFT","capex_to_revenue_annual") |
| Capital Expenditures (Annual) | `capex_annual` | YCP("MSFT","capex_annual") |
| Capital Expenditures (Fixed Assets) (% of Annual Assets) | `capex_fix_annual_cs_ast` | YCP("MSFT","capex_fix_annual_cs_ast") |
| Capital Expenditures (Fixed Assets) (% of Annual Revenues) | `capex_fix_annual_cs_rev` | YCP("MSFT","capex_fix_annual_cs_rev") |
| Capital Expenditures (Fixed Assets) (% of Quarterly Assets) | `capex_fix_cs_ast` | YCP("MSFT","capex_fix_cs_ast") |
| Capital Expenditures (Fixed Assets) (% of Quarterly Revenues) | `capex_fix_cs_rev` | YCP("MSFT","capex_fix_cs_rev") |
| Capital Expenditures (Fixed Assets) (Annual Per Share) | `capex_fix_annual_per_share` | YCP("MSFT","capex_fix_annual_per_share") |
| Capital Expenditures (Fixed Assets) (Annual) | `capex_fix_annual` | YCP("MSFT","capex_fix_annual") |
| Capital Expenditures (Fixed Assets) (Per Share Quarterly) | `capex_fix_per_share` | YCP("MSFT","capex_fix_per_share") |
| Capital Expenditures (Fixed Assets) (Quarterly) | `capex_fix` | YCP("MSFT","capex_fix") |
| Capital Expenditures (Fixed Assets) (Semi Annual) | `capex_fix_sa` | YCP("MSFT","capex_fix_sa") |
| Capital Expenditures (Fixed Assets) (TTM) | `capex_fix_ttm` | YCP("MSFT","capex_fix_ttm") |
| Capital Expenditures (Other Assets) (% of Annual Assets) | `capex_oth_annual_cs_ast` | YCP("MSFT","capex_oth_annual_cs_ast") |
| Capital Expenditures (Other Assets) (% of Annual Revenues) | `capex_oth_annual_cs_rev` | YCP("MSFT","capex_oth_annual_cs_rev") |
| Capital Expenditures (Other Assets) (% of Quarterly Assets) | `capex_oth_cs_ast` | YCP("MSFT","capex_oth_cs_ast") |
| Capital Expenditures (Other Assets) (% of Quarterly Revenues) | `capex_oth_cs_rev` | YCP("MSFT","capex_oth_cs_rev") |
| Capital Expenditures (Other Assets) (Annual Per Share) | `capex_oth_annual_per_share` | YCP("MSFT","capex_oth_annual_per_share") |
| Capital Expenditures (Other Assets) (Annual) | `capex_oth_annual` | YCP("MSFT","capex_oth_annual") |
| Capital Expenditures (Other Assets) (Per Share Quarterly) | `capex_oth_per_share` | YCP("MSFT","capex_oth_per_share") |
| Capital Expenditures (Other Assets) (Quarterly) | `capex_oth` | YCP("MSFT","capex_oth") |
| Capital Expenditures (Other Assets) (Semi Annual) | `capex_oth_sa` | YCP("MSFT","capex_oth_sa") |
| Capital Expenditures (Other Assets) (TTM) | `capex_oth_ttm` | YCP("MSFT","capex_oth_ttm") |
| Capital Expenditures (Quarterly) | `capex` | YCP("MSFT","capex") |
| Capital Expenditures (TTM) | `capex_ttm` | YCP("MSFT","capex_ttm") |
| FCF to Debt (Annual) | `fcf_to_debt_annual` | YCP("MSFT","fcf_to_debt_annual") |
| FCF to Debt (TTM) | `fcf_to_debt` | YCP("MSFT","fcf_to_debt") |
| Free Cash Flow (TTM) | `free_cash_flow_ttm` | YCP("MSFT","free_cash_flow_ttm") |
| Free Cash Flow (% of Annual Assets) | `free_cash_flow_annual_cs_ast` | YCP("MSFT","free_cash_flow_annual_cs_ast") |
| Free Cash Flow (% of Annual Revenues) | `free_cash_flow_annual_cs_rev` | YCP("MSFT","free_cash_flow_annual_cs_rev") |
| Free Cash Flow (% of Quarterly Assets) | `free_cash_flow_cs_ast` | YCP("MSFT","free_cash_flow_cs_ast") |
| Free Cash Flow (% of Quarterly Revenues) | `free_cash_flow_cs_rev` | YCP("MSFT","free_cash_flow_cs_rev") |
| Free Cash Flow (Annual) | `free_cash_flow_annual` | YCP("MSFT","free_cash_flow_annual") |
| Free Cash Flow (Quarterly) | `free_cash_flow` | YCP("MSFT","free_cash_flow") |
| Free Cash Flow Margin (10Y) | `free_cash_flow_margin_10y` | YCP("MSFT","free_cash_flow_margin_10y") |
| Free Cash Flow Margin (1Y) | `free_cash_flow_margin_1y` | YCP("MSFT","free_cash_flow_margin_1y") |
| Free Cash Flow Margin (3Y) | `free_cash_flow_margin_3y` | YCP("MSFT","free_cash_flow_margin_3y") |
| Free Cash Flow Margin (5Y) | `free_cash_flow_margin_5y` | YCP("MSFT","free_cash_flow_margin_5y") |
| Free Cash Flow Margin (TTM) | `free_cash_flow_margin_ttm` | YCP("MSFT","free_cash_flow_margin_ttm") |
| Free Cash Flow Per Share (TTM) | `free_cash_flow_per_share_ttm` | YCP("MSFT","free_cash_flow_per_share_ttm") |
| Free Cash Flow Per Share (Annual) | `free_cash_flow_per_share_annual` | YCP("MSFT","free_cash_flow_per_share_annual") |
| Free Cash Flow Per Share (Quarterly) | `free_cash_flow_per_share` | YCP("MSFT","free_cash_flow_per_share") |
| Free Cash Flow Return on Invested Capital (10Y) | `free_cash_flow_roic_10y` | YCP("MSFT","free_cash_flow_roic_10y") |
| Free Cash Flow Return on Invested Capital (3Y) | `free_cash_flow_roic_3y` | YCP("MSFT","free_cash_flow_roic_3y") |
| Free Cash Flow Return on Invested Capital (5Y) | `free_cash_flow_roic_5y` | YCP("MSFT","free_cash_flow_roic_5y") |
| Free Cash Flow Return on Invested Capital (Annual) | `free_cash_flow_roic_annual` | YCP("MSFT","free_cash_flow_roic_annual") |
| Free Cash Flow Yield | `free_cash_flow_yield` | YCP("MSFT","free_cash_flow_yield") |
| Free Cash Flow Yield (% of Annual Assets) | `fcf_yld_annual_cs_ast` | YCP("MSFT","fcf_yld_annual_cs_ast") |
| Free Cash Flow Yield (% of Annual Revenues) | `fcf_yld_annual_cs_rev` | YCP("MSFT","fcf_yld_annual_cs_rev") |
| Free Cash Flow Yield (% of Quarterly Assets) | `fcf_yld_cs_ast` | YCP("MSFT","fcf_yld_cs_ast") |
| Free Cash Flow Yield (% of Quarterly Revenues) | `fcf_yld_cs_rev` | YCP("MSFT","fcf_yld_cs_rev") |
| Free Cash Flow Yield (Annual Per Share) | `fcf_yld_annual_per_share` | YCP("MSFT","fcf_yld_annual_per_share") |
| Free Cash Flow Yield (Annual) | `fcf_yld_annual` | YCP("MSFT","fcf_yld_annual") |
| Free Cash Flow Yield (Per Share Quarterly) | `fcf_yld_per_share` | YCP("MSFT","fcf_yld_per_share") |
| Free Cash Flow Yield (Quarterly) | `fcf_yld` | YCP("MSFT","fcf_yld") |
| Free Cash Flow Yield (Semi Annual) | `fcf_yld_sa` | YCP("MSFT","fcf_yld_sa") |
| Free Cash Flow Yield (TTM) | `fcf_yld_ttm` | YCP("MSFT","fcf_yld_ttm") |
| Free Cash Flow to Enterprise Value (10Y) | `free_cash_flow_ev_10y` | YCP("MSFT","free_cash_flow_ev_10y") |
| Free Cash Flow to Enterprise Value (1Y) | `free_cash_flow_ev_1y` | YCP("MSFT","free_cash_flow_ev_1y") |
| Free Cash Flow to Enterprise Value (3Y) | `free_cash_flow_ev_3y` | YCP("MSFT","free_cash_flow_ev_3y") |
| Free Cash Flow to Enterprise Value (5Y) | `free_cash_flow_ev_5y` | YCP("MSFT","free_cash_flow_ev_5y") |
| Free Cash Flow to Enterprise Value (TTM) | `free_cash_flow_ev_ttm` | YCP("MSFT","free_cash_flow_ev_ttm") |
| Free Cash Flow to Equity (TTM) | `free_cash_flow_equity_ttm` | YCP("MSFT","free_cash_flow_equity_ttm") |
| Free Cash Flow to Equity (Annual) | `free_cash_flow_equity_annual` | YCP("MSFT","free_cash_flow_equity_annual") |
| Free Cash Flow to Equity (Quarterly) | `free_cash_flow_equity` | YCP("MSFT","free_cash_flow_equity") |
| Free Cash Flow to Firm (TTM) | `free_cash_flow_firm_ttm` | YCP("MSFT","free_cash_flow_firm_ttm") |
| Free Cash Flow to Firm (Annual) | `free_cash_flow_firm_annual` | YCP("MSFT","free_cash_flow_firm_annual") |
| Free Cash Flow to Firm (Quarterly) | `free_cash_flow_firm` | YCP("MSFT","free_cash_flow_firm") |

---

## 8. Valuation Multiples (Companies)

| Metric | Code | Example |
|---|---|---|
| Dividend Yield | `dividend_yield` | YCP("MSFT","dividend_yield") |
| Enterprise Value | `enterprise_value` | YCP("MSFT","enterprise_value") |
| Market Cap | `market_cap` | YCP("MSFT","market_cap") |
| Market Cap Per Employee (Annual) | `market_cap_per_employee_annual` | YCP("MSFT","market_cap_per_employee_annual") |
| Market Cap Plus Net Liabilities | `market_cap_plus_net_liabilities` | YCP("MSFT","market_cap_plus_net_liabilities") |
| Market Cap Score | `market_cap_fractile` | YCP("MSFT","market_cap_fractile") |
| PE Ratio | `pe_ratio` | YCP("MSFT","pe_ratio") |
| PE Ratio (10y Mean) | `pe_ratio_10y_mean` | YCP("MSFT","pe_ratio_10y_mean") |
| PE Ratio (10y Median) | `pe_ratio_10y_mdn` | YCP("MSFT","pe_ratio_10y_mdn") |
| PE Ratio (3y Mean) | `pe_ratio_3y_mean` | YCP("MSFT","pe_ratio_3y_mean") |
| PE Ratio (3y Median) | `pe_ratio_3y_mdn` | YCP("MSFT","pe_ratio_3y_mdn") |
| PE Ratio (5y Mean) | `pe_ratio_5y_mean` | YCP("MSFT","pe_ratio_5y_mean") |
| PE Ratio (5y Median) | `pe_ratio_5y_mdn` | YCP("MSFT","pe_ratio_5y_mdn") |
| PE Ratio (7y Mean) | `pe_ratio_7y_mean` | YCP("MSFT","pe_ratio_7y_mean") |
| PE Ratio (7y Median) | `pe_ratio_7y_mdn` | YCP("MSFT","pe_ratio_7y_mdn") |
| PE Ratio (Annual) | `pe_ratio_annual` | YCP("MSFT","pe_ratio_annual") |
| PEG Ratio | `peg_ratio` | YCP("MSFT","peg_ratio") |
| Price to Book Value | `price_to_book_value` | YCP("MSFT","price_to_book_value") |
| Price to Book Value (10y Mean) | `price_to_book_value_10y_mean` | YCP("MSFT","price_to_book_value_10y_mean") |
| Price to Book Value (10y Median) | `price_to_book_value_10y_mdn` | YCP("MSFT","price_to_book_value_10y_mdn") |
| Price to Book Value (3y Mean) | `price_to_book_value_3y_mean` | YCP("MSFT","price_to_book_value_3y_mean") |
| Price to Book Value (3y Median) | `price_to_book_value_3y_mdn` | YCP("MSFT","price_to_book_value_3y_mdn") |
| Price to Book Value (5y Mean) | `price_to_book_value_5y_mean` | YCP("MSFT","price_to_book_value_5y_mean") |
| Price to Book Value (5y Median) | `price_to_book_value_5y_mdn` | YCP("MSFT","price_to_book_value_5y_mdn") |
| Price to Book Value (7y Mean) | `price_to_book_value_7y_mean` | YCP("MSFT","price_to_book_value_7y_mean") |
| Price to Book Value (7y Median) | `price_to_book_value_7y_mdn` | YCP("MSFT","price_to_book_value_7y_mdn") |
| Price to Free Cash Flow (TTM) | `price_to_cash_flow_ttm` | YCP("MSFT","price_to_cash_flow_ttm") |
| Price to Free Cash Flow (10y Median) | `price_to_cash_flow_10y_mdn` | YCP("MSFT","price_to_cash_flow_10y_mdn") |
| Price to Free Cash Flow (3y Median) | `price_to_cash_flow_3y_mdn` | YCP("MSFT","price_to_cash_flow_3y_mdn") |
| Price to Free Cash Flow (5y Median) | `price_to_cash_flow_5y_mdn` | YCP("MSFT","price_to_cash_flow_5y_mdn") |
| Price to Free Cash Flow (7y Median) | `price_to_cash_flow_7y_mdn` | YCP("MSFT","price_to_cash_flow_7y_mdn") |
| Price to Free Cash Flow (Annual) | `price_to_cash_flow_annual` | YCP("MSFT","price_to_cash_flow_annual") |

---

## 9. Company Info Fields (use with YCI)

| Field | Code | Example |
|---|---|---|
| Business Summary | `business_summary` | YCI("MSFT","business_summary") |
| CEO | `ceo` | YCI("MSFT","ceo") |
| CIK | `cik` | YCI("MSFT","cik") |
| Country | `country` | YCI("MSFT","country") |
| CUSIP | `cusip` | YCI("MSFT","cusip") |
| Currency | `currency` | YCI("MSFT","currency") |
| Employees | `employees` | YCI("MSFT","employees") |
| Exchange | `exchange` | YCI("MSFT","exchange") |
| Fiscal Year End | `fiscal_year_end` | YCI("MSFT","fiscal_year_end") |
| GICS Sector | `gics_sector` | YCI("MSFT","gics_sector") |
| Industry | `industry` | YCI("MSFT","industry") |
| ISIN | `isin` | YCI("MSFT","isin") |
| Last Fiscal Quarter End | `lfqe` | YCI("MSFT","lfqe") |
| Last Fiscal Year End | `lfye` | YCI("MSFT","lfye") |
| Name | `name` | YCI("MSFT","name") |
| Next Earnings Date | `next_earnings_date` | YCI("MSFT","next_earnings_date") |
| Sector | `sector` | YCI("MSFT","sector") |

_Note: This list is not exhaustive. Other YCI fields exist; consult YCharts documentation for the full set._

---

## 10. Macroeconomic Indicators

For macroeconomic series leave the `<calculation>` field blank, just pass the indicator's ticker.

| Use case | Formula |
|---|---|
| Latest value | `YCP("I:USGDP")` |
| Time series | `YCS("I:USGDP","2020-01-01","2024-12-31")` |

### Macro info fields (YCI)

| Field | Code | Example |
|---|---|---|
| Adjustment Type | `adjustment` | YCI("I:USGDP","adjustment") |
| Change Year Ago | `change_year_ago` | YCI("I:USGDP","change_year_ago") |
| Change Year Ago % | `change_year_ago_percent` | YCI("I:USGDP","change_year_ago_percent") |
| Currency Code | `currency_code` | YCI("I:USGDP","currency_code") |
| Data Type | `data_type` | YCI("I:USGDP","data_type") |
| Detailed Security Type | `detailed_security_type` | YCI("I:USGDP","detailed_security_type") |
| Display Symbol | `display_security_id` | YCI("I:USGDP","display_security_id") |
| Earliest Performance Date | `earliest_performance_date` | YCI("I:USGDP","earliest_performance_date") |
| Last Updated (Eastern) | `eastern_last_updated` | YCI("I:USGDP","eastern_last_updated") |
| Next Release (Eastern) | `eastern_next_release` | YCI("I:USGDP","eastern_next_release") |
| First Period Imported | `first_period_imported` | YCI("I:USGDP","first_period_imported") |
| Frequency | `frequency` | YCI("I:USGDP","frequency") |
| Last Change | `last_change` | YCI("I:USGDP","last_change") |
| Last Change % | `last_change_percent` | YCI("I:USGDP","last_change_percent") |
| Last Period | `last_period` | YCI("I:USGDP","last_period") |
| Last Updated | `last_updated` | YCI("I:USGDP","last_updated") |
| Last Value | `last_value` | YCI("I:USGDP","last_value") |
| Latest Performance Date | `latest_performance_date` | YCI("I:USGDP","latest_performance_date") |
| Next Release | `next_release` | YCI("I:USGDP","next_release") |
| Previous Value | `previous_value` | YCI("I:USGDP","previous_value") |
| Region | `region` | YCI("I:USGDP","region") |
| Report | `report` | YCI("I:USGDP","report") |
| Seasonally Adjusted Name | `seasonally_adjusted_name` | YCI("I:USGDP","seasonally_adjusted_name") |
| Security ID | `security_id` | YCI("I:USGDP","security_id") |
| Security Name | `security_name` | YCI("I:USGDP","security_name") |
| Source | `source` | YCI("I:USGDP","source") |
| Unit | `unit` | YCI("I:USGDP","unit") |
| Unit Shorthand | `unit_shorthand` | YCI("I:USGDP","unit_shorthand") |
| Watchlist Types | `watchlist_type` | YCI("I:USGDP","watchlist_type") |
| YCharts URL | `ycharts_url` | YCI("I:USGDP","ycharts_url") |

---

## 11. YCS Parameter Options

Reference for `<resample frequency>`, `<resample function>`, `<fill method>`, and `<aggregate function>` arguments in YCS.

### start_date / end_date

Format: `YYYY-MM-DD`

### resample_frequency

`daily`, `market_daily`, `weekly_mon`, `weekly_tue`, `weekly_wed`, `weekly_thu`, `weekly_fri`, `weekly_sat`, `weekly_sun`, `weekly`, `biweekly_mon`, `biweekly_tue`, `biweekly_wed`, `biweekly_thu`, `biweekly_fri`, `biweekly_sat`, `biweekly_sun`, `biweekly`, `monthly`, `bimonthly`, `market_monthly`, `quarterly`, `quarterly_dec`, `quarterly_nov`, `quarterly_oct`, `market_quarterly`, `yearly`, `semi_yearly`, `market_yearly`

### resample_function

`sum`, `std`, `max`, `min`, `median`, `first`, `mean`, `last`

### fill_method

`backward`, `forward`, `no_fill`

### aggregate_function

`sum`, `std`, `max`, `min`, `median`, `first`, `pct_change`, `mean`, `last`
