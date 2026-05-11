---
name: ycharts-excel-formulas
description: "Use whenever the user wants to pull data into Excel using the YCharts Add-in, any mention of YCharts, YCP, YCS, YCI, YCD, YCDS, YCH, or asks like \"get the price of X on date Y\", \"pull MSFT revenue\", \"fetch holdings of SPY\", \"daily OHLC for a ticker\", \"look up the YCharts code for [metric]\". Trigger on questions about YCharts formula syntax, calculation codes, ticker-prefix conventions (M:, P:, S:, Y:), array-entered formulas, or when the user wants to write/debug YCharts formulas in a workbook. Also use when the user has a Bloomberg-style ticker (e.g. \"MSFT US\") that YCharts is rejecting, this skill knows the SUBSTITUTE/TRIM workaround."
---

When to use
Invoke when the user asks anything about YCharts formulas in Excel: pulling a price, return, financial-statement line item, holdings list, or info field for a ticker; debugging a #VALUE! from a YCP/YCS formula; or asking which calculation code to use for a metric.

Looking up calculation codes
This SKILL.md covers the common metrics most workflows need (see "Common metric codes" below). For anything not listed there, the supplemental catalog at `references/ycharts_metrics_catalog.md` contains roughly 1,500 calculation codes pulled from the YCharts Excel Add-in formula syntax guide. The catalog is large, so do not load it whole. Read its first ~80 lines first (the table of contents lists each section with its starting line number); then use `view_range` to pull only the relevant section. If a metric still cannot be found after consulting the catalog, do not fabricate a calculation code, say it cannot be located and offer to search the YCharts documentation.

Function reference, the six YCharts formulas
All formulas live in cells. Array formulas (those returning more than one value) must be entered with Ctrl+Shift+Enter on Windows or Cmd+Shift+Enter on Mac (shown below as {= ... }).
YCP, single data point
=YCP(<ticker>, <calculation>, <date>, <retrieve date>, <transpose>, <fill null>)
•	<ticker> (req): security ticker, e.g. "MSFT", "SPY", "M:AWSHX"
•	<calculation> (req): metric code, e.g. "price", "pe_ratio", "high_price". Leave blank for macroeconomic indicators.
•	<date> (opt): defaults to most recent. Best practice is to reference a cell.
•	<retrieve date> (opt): "Y" to also return the as-of date.
•	<transpose> (opt): "Y" for row layout (only relevant when retrieving a date).
•	<fill null> (opt): what to display on null. Defaults to "ERR: NO DATA".
Examples:
•	=YCP("WMT","price"), most recent close
•	=YCP("WMT","price","2019-12-31",,,"N/A"), close on a specific date
•	{=YCP("WMT","revenues_annual",,"y")}, latest annual revenue and the date
YCS, data series across dates (array formula)
{=YCS(<ticker>, <calculation>, <sdate>, <edate>, <reverse>, <transpose>, <retrieve date>, <fill null>, <resample frequency>, <resample function>, <fill method>, <aggregate function>)}
•	<sdate>/<edate>: dates, or negative numbers for "look back N calendar days" (e.g. -30).
•	<reverse>: "Y" for newest-to-oldest.
•	<resample frequency>: e.g. "daily", "weekly", "monthly", "quarterly", "annual".
•	<aggregate function>: e.g. "max", "min", "median", "mean", "pct_change".
Examples:
•	{=YCS("WMT","price","2020-06-05","2020-06-15",,"Y","Y")}, daily closes with dates, transposed
•	{=YCS("WMT","price","2019-06-30","2019-12-31",,"Y","Y",,"monthly")}, monthly closes
•	{=YCS("WMT","price","2019-05-31","2020-05-31",,,"Y",,,,,"max")}, max price + date in window
YCI, info field (string/static data)
=YCI(<ticker>, <info field>, <transpose>, <show headers>, <fill null>)
Returns text by default. Use DATEVALUE(...) to convert a date string to a serial.
Examples:
•	=YCI("AAPL","industry",,,"N/A") → "Technology Hardware, Storage & Peripherals"
•	=YCI("AAPL","lfqe") → last fiscal quarter end as text; wrap in DATEVALUE for a real date
YCD, date associated with a metric
=YCD(<ticker>, <calculation>, <date>)
Returns the as-of date (as text) for the most recent data point, or for a specific look-up date. Wrap in DATEVALUE to convert to a serial.
•	=YCD("M:DODGX","energy_exposure") → most recent sector-exposure date
•	=YCD("WMT","revenues","2020-06-01") → date of most recent revenue as of 6/1/2020
YCDS, series of dates (array formula)
{=YCDS(<ticker>, <calculation>, <sdate>, <edate>, <reverse>, <transpose>)}
Common use: dynamic list of a company's quarter ends.
•	{=YCDS("WMT","revenues","2019-06-01","2020-06-01","Y","Y")} → newest-to-oldest quarter ends, horizontal
YCH, holdings list (array formula)
{=YCH(<ticker>, <show weights>, <weight type>, <transpose>, <show headers>)}
•	<show weights>: "Y" to include weight column.
•	<weight type>: "current" (default) or "target" (model portfolios only).
•	{=YCH("SPY","Y",,,"Y")} → top holdings of SPY with weights and headers
•	{=YCH("P:12345","Y","target")} → target weights of a model portfolio
Ticker prefix conventions
Security type	Prefix	Example
Public company / equity	(none)	MSFT, AAPL
Mutual fund	M:	M:AWSHX
Separate account	S:	S:0P0000JCML
Model portfolio	P:	P:12345
Custom security / index	Y:	Y:1234
Macroeconomic indicator	(varies)	I:USRGDP, etc., leave <calculation> blank
Bloomberg-style suffix gotcha: YCharts rejects tickers like "MSFT US". If a column has these, strip the suffix in-formula:
excel
=YCP(TRIM(SUBSTITUTE($B2,"US","")), "price", $C$2)
Daily OHLC quick reference
For Companies and ETFs/CEFs only, mutual funds, separate accounts, and model portfolios expose only a daily close (price or level).
Field	Code	Example
Open	open_price	=YCP("MSFT","open_price","2024-06-14")
High	high_price	=YCP("MSFT","high_price","2024-06-14")
Low	low_price	=YCP("MSFT","low_price","2024-06-14")
Close	price	=YCP("MSFT","price","2024-06-14")
For a date range of any of these, swap to YCS:
excel
{=YCS("MSFT","high_price","2024-06-01","2024-06-30",,,"Y")}
Common metric codes (memorize these)
Prices & returns (Companies, ETFs, indexes via ETF):
•	Close: price · Open: open_price · High: high_price · Low: low_price · Volume: volume
•	1-day return: roc_1_close · 1M / 3M / 6M / YTD / 1Y / 3Y / 5Y / 10Y daily-cumulative price returns: one_month_return, three_month_return, six_month_return, ytd_return, one_year_return, three_year_return, five_year_return, ten_year_return
•	52-week / all-time: year_high, year_low, all_time_high, all_time_low
Income statement (Companies):
•	Revenue: revenues (TTM), revenues_quarterly, revenues_annual
•	Gross profit: gross_profit · Gross margin: gross_margin
•	Operating income: operating_income · Op. margin: operating_margin
•	EBIT / EBITDA: ebit, ebitda
•	Net income: net_income · Net margin: net_profit_margin
•	EPS: eps_diluted, eps_basic
Balance sheet (Companies):
•	total_assets, current_assets, cash_on_hand, cash_st_investments
•	total_liabilities, current_liabilities, long_term_debt, short_term_debt, total_debt, net_debt
•	total_equity, book_value, tangible_book_value
•	shares_outstanding
Cash flow (Companies):
•	cash_from_operations, cash_from_investing, cash_from_financing
•	free_cash_flow, capital_expenditures, dividends_paid
Valuation (Companies):
•	market_cap, enterprise_value
•	pe_ratio, price_to_book, price_to_sales, peg_ratio
•	ev_to_ebitda, ev_to_revenue, ev_to_ebit
•	dividend_yield
Info fields (use with YCI):
•	name, industry, sector, gics_sector, country, exchange, currency
•	cusip, isin, cik
•	fiscal_year_end, lfqe (last fiscal quarter end), lfye (last fiscal year end), next_earnings_date
•	business_summary, employees, ceo
For any metric not listed above, consult `references/ycharts_metrics_catalog.md` (read the first ~80 lines for the TOC, then `view_range` the specific section).
Workflow when writing YCharts formulas
1.	Confirm the ticker format, does it need a prefix (M:, P:, S:, Y:)? Does it have a Bloomberg " US" suffix to strip?
2.	Pick the right function, single value → YCP; date range → YCS; static text/info → YCI; date of a metric → YCD; list of dates → YCDS; holdings → YCH.
3.	Reference cells, don't hardcode, put ticker, date, and date range in their own cells so formulas can be dragged. The user's workbook should look like:
   B2: MSFT          (ticker)
   C2: 2026-05-07    (date)
   D2: =YCP($B2, "open_price", $C2)
   E2: =YCP($B2, "high_price", $C2)
   F2: =YCP($B2, "low_price",  $C2)
   G2: =YCP($B2, "price",      $C2)
4.	Array-enter YCS, YCDS, YCH when they return multiple values. In modern Excel (365), dynamic arrays handle this automatically; in older Excel, use Ctrl+Shift+Enter.
5.	Verify, read back the cells and check for #VALUE!, #NAME?, or ERR: NO DATA. Common causes:
o	#NAME? → the YCharts add-in isn't loaded/signed in
o	ERR: NO DATA → ticker rejected (check prefix/suffix), wrong calc code, or date before inception
o	#VALUE! → date arg is text where a number is expected, or vice versa
Done when
•	Every formula written returns a real value (not ERR: NO DATA or an error code), OR
•	The user has been told explicitly which cells failed and why, with a suggested fix (ticker format, calc code, date range), OR
•	The user asked a syntax question and you've given them the formula template plus a worked example using their ticker.
