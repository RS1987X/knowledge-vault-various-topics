# Portfolio theory connections to energy trading & real-world energy assets (brainstorm)

**Date:** 2026-02-17 09:26:58  
**User:** RS1987X  

## Context
Discussion on how classic portfolio theory (Markowitz / CAPM / factor models / risk budgeting) maps to optimizing a portfolio of real-world energy assets, then narrowed to a non-operations setting: software making trading/usage decisions (no build decisions; can choose usage/dispatch; can buy/sell contracts).

---

## Key bridges: portfolio theory → energy assets / trading book

### Mean–variance → risk/return of cashflows (not just prices)
- Treat each asset/instrument/strategy as a distribution of **cashflows / P&L**.
- “Return” can be expected EBITDA/NPV (asset) or expected P&L (trading).
- “Risk” can be variance, but often better: **CVaR / stress loss / drawdown / margin-at-risk**.

### Diversification → shared physical/market drivers (covariance comes from factors)
- Energy portfolios are driven by common factors (often unstable correlations):
  - Power hub/system price level
  - Gas hub price; spark/dark spread
  - Location/basis/congestion (nodal vs hub)
  - Shape (peak/off-peak; hourly blocks)
  - Weather regimes (HDD/CDD, wind/solar)
  - Policy/carbon; volatility regime

### Factor models > raw covariance for practical construction
- Manage and budget **factor exposures** rather than only instrument weights.
- Example constraints: limit basis exposure; cap winter gas exposure; avoid single-driver concentration.

### Downside risk (CVaR) + stress testing are central
- Tail events dominate: scarcity pricing, negative price regimes, outages, transmission constraints, weather extremes.
- Prefer CVaR/ES and explicit stress scenarios to plain variance.

### Constraints & indivisibility
- Physical/contract constraints create a feasible set far from simple “weights sum to 1” problems:
  - usage/nominations limits
  - position limits
  - margin/liquidity constraints
  - credit limits

### Strategy portfolio (alpha engine + risk allocator)
- Separate:
  1. **Alpha/signal** for expected returns of instruments/strategies
  2. **Risk model** (factor + scenario losses)
  3. **Allocator**: maximize expected P&L minus risk penalty under constraints

### Benchmark-relative framing (optional)
- If optimizing relative to a benchmark (flat hub exposure, hedging program, market-neutral), use tracking-error style objectives.

---

## Why many energy “assets” are option-like
A position is **option-like** when value comes from a *right to decide later* (how much to use, when to use) after uncertainty resolves—i.e., “right but not obligation.” This creates nonlinear (convex) P&L sensitive to volatility/tails.

Examples:
- Storage
- Swing contracts (min/max takes)
- Tolling / dispatch rights (spark spread exercise)
- Curtailable load (avoid buying at spikes)

### Why it matters
Option-like positions:
- have **nonlinear P&L** (convexity)
- depend on **volatility and tails**, not just mean/correlation
- show **state-dependent correlation** (things correlate more in stress)

---

## Battery dispatch: is the decision option-like or only the value?
**Both.** The option-like payoff is created by the *ability to choose* charge/discharge/idle over time (exercise strategy). The battery’s value is the expected payoff from applying an optimal (or chosen) dispatch policy under uncertainty.

### Battery as an option on time spreads
For arbitrage, the battery resembles a strip/portfolio of options on intertemporal spreads:
- Charge when price is low; discharge when price is high later.
- With round-trip efficiency \(\eta\) and degradation/variable cost \(c\), an idealized opportunity resembles:

\[ \max\big(P_{t+k} - \tfrac{1}{\eta} P_t - c,\ 0\big) \]

The **max(…,0)** captures the option feature: you can choose not to cycle.

### Dispatch is “exercise” with time value
At each interval, the decision can be described via a threshold policy based on the **marginal value of stored energy** (shadow price of state of charge, SoC), \(V_t\):

- **Charge** if \(P_t\) is sufficiently below the value of keeping energy for the future.
- **Discharge** if \(P_t\) is sufficiently above it.
- **Idle** in a middle band.

Illustrative threshold form (not a full model):
- Charge if \(P_t < \eta V_t - c\)
- Discharge if \(P_t > V_t + c\)
- Else idle

\(V_t\) depends on: SoC, time remaining, expected future prices, volatility/scarcity probability, and constraints (power/energy/cycle limits).

### Key intuition
- If you fix a schedule (charge noon, discharge 6pm) you lose much of the convexity.
- The convexity/value comes from adapting actions to realized prices and preserving flexibility for rare high-value events.

---

## Practical objective (representative)
A common construction for trading + optional rights:

\[ \max_{w,\theta}\ \mathbb{E}[P\&L(w,\theta)] - \lambda\,CVaR_\alpha(P\&L(w,\theta)) \]

Subject to:
- position bounds
- factor exposure bounds
- margin/liquidity constraints
- physical feasibility of usage policy \(\theta\)

Where \(w\) are tradable positions and \(\theta\) parameterizes the usage/dispatch strategy.

---

## Open follow-ups (not answered yet)
To specialize the framework, clarify:
- instrument set (battery only vs battery + spreads/options/FTRs)
- market (ERCOT/PJM/CAISO/etc.), DA vs RT
- horizon (intraday vs multi-day vs seasonal)
- risk metric (CVaR, drawdown, stress loss, margin-at-risk)