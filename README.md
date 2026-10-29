# Forecasting FTSE 100 Returns: U.S. Equities, UK Bond Yields and GBP/USD

Time series econometrics project testing what drives UK stock market returns, and whether past movements in U.S. stocks, UK bond yields and the pound help forecast them.

**Tools:** EViews, Excel
**Methods:** ADF unit root tests, OLS regression, ARCH test, VAR(1), Granger causality, impulse responses, Johansen cointegration
**Data:** 25 years of FTSE 100, S&P 500, UK 10-year bond yield and GBP/USD data (2001–2025)

## Research Question

Do past movements in the S&P 500, UK 10-year bond yields and the GBP/USD exchange rate help forecast FTSE 100 returns?

## Key Findings

- **Strong same-month link to the U.S. market.** A 1% rise in S&P 500 monthly returns is associated with a ~0.75% rise in FTSE 100 returns. The model explains about 63% of FTSE return variation (R² = 0.63).
- **A stronger pound is linked to lower FTSE returns.** Many FTSE 100 companies earn much of their revenue in dollars, so when the pound strengthens, those earnings are worth less in pounds.
- **UK bond yields had no significant effect,** in the full model or on their own.
- **Limited forecasting power.** U.S. shocks fade within 2–3 months. Past S&P 500 returns give only weak evidence (10% level), and past bond yield and currency moves do not forecast FTSE returns.
- **No long-run relationship.** The Johansen test found no cointegration, so a VAR in returns was used instead of a VEC model.

**In simple terms:** the UK market moves closely with the U.S. market in the same month, but last month's U.S., bond or currency movements don't reliably predict next month's FTSE return.

## Project Structure

| File | What it covers |
|---|---|
| `01-FTSE100-Quarterly-Regression.pdf` | **Part 1.** Quarterly data (2001Q2–2025Q4, 99 observations). OLS regression of FTSE 100 returns on S&P 500 returns and UK bond yield changes, with ADF, correlation, residual and ARCH diagnostics. |
| `02-FTSE100-Monthly-VAR-Forecasting.pdf` | **Part 2.** Monthly data (2001M03–2025M12, 298 observations). Adds GBP/USD and tests forecasting power with VAR(1), Granger causality, impulse responses and Johansen cointegration. |
| `03-Executive-Summary.pdf` | One-page summary of Part 2 results for a non-technical reader. |

## Approach

1. Downloaded index levels, bond yields and exchange rates and cleaned them in Excel
2. Tested the levels for stationarity (ADF). All four were nonstationary.
3. Converted index and exchange-rate levels into percent returns and the bond yield into changes, then confirmed stationarity
4. Ran OLS to measure same-period relationships, checking residuals for autocorrelation and ARCH effects
5. Selected lag length (LR, FPE and AIC chose 1 lag) and estimated a VAR(1)
6. Ran Granger causality tests and impulse responses to test forecasting power
7. Ran the Johansen test to decide between VAR and VEC

## Data Sources

FTSE 100, S&P 500, UK 10-year bond yield and GBP/USD data from Investing.com (accessed May 2026), used for academic, non-commercial purposes. Raw data is not included, in line with the provider's terms. 

- FTSE 100 index
- S&P 500 index
- United Kingdom 10-year government bond yield
- GBP/USD exchange rate

## Limitations and Next Steps

- Results show statistical relationships, not causation
- Monthly data may miss daily market reactions
- Possible extensions: crisis-period dummies (2008, Brexit, COVID-19) and UK inflation or Bank of England policy rate
