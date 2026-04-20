# Human-Capital-Adjusted Kelly Framework

## Overview
This document explains a simple human-capital-adjusted Kelly framework with financing-cost-aware leverage and valuation buckets for a long-horizon investor.

## Inputs
- Financial Capital (F)
- Risk-adjusted Human Capital (H = q * PV(after-tax labor income))
- Beta_H (equity-like share of human capital)
- Target risky share of economic wealth (w_t = c * ((mu_t - r_f) / sigma^2))
- Raw portfolio exposure (x_raw = (w_t*(F+H) - beta_H*H)/F)
- Final target exposure (x_target = MIN(x_max_policy, MAX(0, x_raw)))
- Leverage gate tied to financing cost where x_max_policy is 1.00 if mu_t <= r_b, otherwise user-set cap such as 1.10 to 1.25.

## Core formulas
1. 
   H = q * PV(after-tax labor income)
2. 
   w_t = c * ((mu_t - r_f) / sigma^2)
3. 
   x_raw = (w_t*(F+H) - beta_H*H)/F
4. 
   x_target = MIN(x_max_policy, MAX(0, x_raw))

## Suggested default assumptions
- sigma: 17%
- r_f: 3%
- r_b: 5%
- Kelly fraction (c): 0.5
- q: 0.6
- beta_H: 0.4
- Financial capital example: 250000 SEK
- Monthly gross income example: 62000 SEK
- After-tax annual income example: 582000 SEK
- Retirement horizon example: 30 years
- Discount rate: 4%
- Income growth: 1%

## How to use in Google Sheets
1. Paste the contents of assumptions.tsv into a sheet named `assumptions`.
2. Paste the contents of calculator.tsv into a sheet named `calculator`.

## Interpretation notes
- Be aware that actual Google Sheet creation is not automated; these files are import-ready.

## Caveats
- Adjust assumptions based on real market data and personal financial situations.