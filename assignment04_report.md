# Assignment 04 Interpretation Memo

**Student Name:** Nevaeh Marquez
**Date:** 13 February 2026
**Assignment:** REIT Annual Returns and Predictors (Simple Linear Regression)

---

## 1. Regression Overview

You estimated **three** simple OLS regressions of REIT *annual* returns on different predictors:

| Model | Y Variable | X Variable | Interpretation Focus |
|-------|------------|------------|----------------------|
| 1 | ret (annual) | div12m_me | Dividend yield |
| 2 | ret (annual) | prime_rate | Interest rate sensitivity |
| 3 | ret (annual) | ffo_at_reit | FFO to assets (fundamental performance) |

For each model, summarize the key results in the sections below.

---

## 2. Coefficient Comparison (All Three Regressions)

**Model 1: ret ~ div12m_me**
- Intercept (β₀): 0.1082 (SE: 0.0060, p-value: 0.0000)
- Slope (β₁): -0.0687 (SE: 0.0325, p-value: 0.0346)
- R²: 0.0018 | N: 2527

**Model 2: ret ~ prime_rate**
- Intercept (β₀): 0.1998 (SE: 0.0158, p-value: 0.0000)
- Slope (β₁): -0.0194 (SE: 0.0030, p-value: 0.0000)
- R²: 0.0164 | N: 2527

**Model 3: ret ~ ffo_at_reit**
- Intercept (β₀): 0.0973 (SE: 0.0092, p-value: 0.0000)
- Slope (β₁): 0.5770 (SE: 0.5675, p-value: 0.3093)
- R²: 0.0004 | N: 2518

*Note: Model 3 may have fewer observations if ffo_at_reit has missing values; statsmodels drops those rows.*

---

## 3. Slope Interpretation (Economic Units)

**Dividend Yield (div12m_me):**
- A 1 percentage point increase in dividend yield (12-month dividends / market equity) is associated with a -0.000687 change in annual return (about -0.07 percentage points).
- REITs that offer higher dividend yields tend to have slightly lower overall returns. I believe this might be because companies paying higher yields are sometimes more financially stressed or grow slower so investors want a higher pay out to help make yp for that added risk.

**Prime Loan Rate (prime_rate):**
- A 1 percentage point increase in the year-end prime rate is associated with a -0.0194 change in annual return (about -1.94 percentage points).
- The evidence shows that REIT returns tend to move in the opposite direction of interest rates. When the rates go up, REIT returns usually go down.

**FFO to Assets (ffo_at_reit):**
- A 1 unit increase in FFO/Assets (fundamental performance) is associated with a 0.5770 change in annual return (about 57.7 percentage points).
- The estimate points in a positive direction, meaning more profitable REITs might earn higher returns, but the evidence is weak so I can't confidently say that's true. 

---

## 4. Statistical Significance

For each slope, at the 5% significance level:
- **div12m_me:** Significant: Higher dividend yield is associated with slightly lower returns.
- **prime_rate:** Significant: Higher prime rates are associated with lower returns.
- **ffo_at_reit:** Not significant: The slope is imprecisely estimated and not different from zero.

**Which predictor has the strongest statistical evidence of a relationship with annual returns?** The prime_rate has the largest absolute t-stat and smallest p-value.

---

## 5. Model Fit (R-squared)

Compare R² across the three models:
- The prime_rate explains the most variation in annual REIT returns with its R-sqaured being 0.016 but that still really low even for it being the largest of the three. This explains that these single predictors don't do a good job of explaining changes in REIT returns. It shows the REIT performance is influenced many different factors like market conditions, economic trends, etc.

---

## 6. Omitted Variables

By using only one predictor at a time, we might be omitting:
- REIT size or leverage: Bigger REITs (or ones with more debt) can handle risk differently. Their financing structure can strongly impact how stable their returns are.
- Property type mix or sector exposure: Not all real estate sectors move the same way. Office, retail, industrial, and residential properties all respond differently to economic shifts, so mix really matters.
- Macroeconomic growth or inflation: Broader economic conditions influence everything like interest rates and property values for example. So, this means that they naturally affect REIT returns too.

**Potential bias:** If we leave out important variables that are related to both our independent variable and returns, our slope estimates could be misleading. For example, if overall economic growth is positively related to both the prime rate and stock returns, then the negative relationship we see between the prime rate and returns might look weaker than it really is. This can happen because growth is pushing returns up at the same time. 

---

## 7. Summary and Next Steps

**Key Takeaway:**
Prime rates have the clearest and most consistent relationship with REIT annual returns (negative). When interest rates go up, borrowing become more expensive and property values tend to fall. Dividend yeild shows a slight negative link (maybe signaling risk), while FFO/Assets has a small positive relationship. But, I don't think it's strong enough to draw firm concrete conclusions.

**What we would do next:**
- Extend to multiple regression (include two or more predictors)
- Test for heteroskedasticity and other OLS assumption violations
- Examine whether relationships vary by time period or REIT sector

---

## Reproducibility Checklist
- x Script runs end-to-end without errors
- x Regression output saved to `Results/regression_div12m_me.txt`, `regression_prime_rate.txt`, `regression_ffo_at_reit.txt`
- x Scatter plots saved to `Results/scatter_div12m_me.png`, `scatter_prime_rate.png`, `scatter_ffo_at_reit.png`
- x Report accurately reflects regression results
- x All interpretations are in economic units (not just statistical jargon)
