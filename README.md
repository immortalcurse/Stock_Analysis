# NSE Portfolio Intelligence Platform
### Stock Market Analysis + Interactive Portfolio Optimiser

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Netlify-00C7B7?style=for-the-badge&logo=netlify)](https://lucent-elf-10044c.netlify.app/)
[![Tableau](https://img.shields.io/badge/Dashboard-Tableau-E97627?style=for-the-badge&logo=tableau)](https://public.tableau.com/app/profile/govardhan.ingle/viz/Stock_Analysis_16944014075480/Dashboard1?publish=yes)
[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python)](https://www.python.org/)

---

## 🔗 Links

| | |
|---|---|
| **Interactive Portfolio Optimiser** | [lucent-elf-10044c.netlify.app](https://lucent-elf-10044c.netlify.app/) |
| **Tableau Dashboard** | [View on Tableau Public](https://public.tableau.com/app/profile/govardhan.ingle/viz/Stock_Analysis_16944014075480/Dashboard1?publish=yes) |

---

## Overview

This project is an end-to-end NSE equity analysis platform covering **28 stocks across 10 sectors** (Jan 2020 – Jan 2023). It began as a sector trend analysis and evolved into a deployed interactive portfolio optimiser using Markowitz Mean-Variance framework.

---

## Part 1 — Sector Analysis

### Data Collection & Preprocessing
- Historical price and volume data collected from **Yahoo Finance (yfinance)**
- Data cleaned and preprocessed in Python (Pandas) — missing values handled, companies mapped to sectors
- 28 NSE-listed equities across 10 sectors: Banking, IT, Automobile, Pharma, Consumer Goods, Energy, Metals, Cement, Utilities, Telecom

### Key Findings

**Correlation Matrix**
- Cement and Banking sectors exhibit the **highest inter-sector dependency**
- Telecom has **minimal impact** on other sectors — acts as market-neutral

**Volume & Price Trends**
- Sector-level volume change and percentage price change visualised across the full period
- Patterns identified using dynamic Tableau dashboards with sector filters

**Quarterly Analysis**
- Trading volume peaks in **Q4** across most sectors — seasonal pattern with implications for portfolio rebalancing

**Inverse Relationships**
- Gold shows **inverse relationship** to broader equity market — explored as a hedging instrument

**COVID-19 Impact (Feb–Apr 2020)**
- Energy sector experienced the steepest drawdown
- Banking & Finance among the hardest hit
- Pharma sector showed **counter-cyclical resilience** and growth

---

## Part 2 — Portfolio Optimisation

**[→ Try the Live Interactive Dashboard](https://lucent-elf-10044c.netlify.app/)**

Built as an extension of the sector analysis using the same NSE dataset.

### Methodology
- Applied **Markowitz Mean-Variance Optimisation** across 10 sector representatives
- Ran **6,000 Monte Carlo simulations** to map the Efficient Frontier
- Used **Scipy** to solve for mathematically exact optimal portfolio weights
- Benchmarked against Nifty50 proxy (equal-weighted 28-stock portfolio)

### Results

| Portfolio | Annual Return | Volatility | Sharpe Ratio |
|---|---|---|---|
| **Max Sharpe (Optimised)** | **40.46%** | 27.35% | **1.242** |
| Min Variance | 22.03% | 18.93% | 0.820 |
| Equal-Weighted | 26.28% | 21.53% | 0.919 |
| Nifty50 Proxy | 24.98% | 21.29% | 0.868 |

**43% improvement in Sharpe Ratio** over Nifty50 proxy benchmark.

### Interactive Dashboard Features
- Investment amount input with risk profile selection (Conservative / Moderate / Aggressive)
- **Efficient Frontier** — 6,000 simulated portfolios coloured by Sharpe ratio
- **Sector Allocation** — interactive donut chart with per-sector investment breakdown
- **Wealth Projection** — Bull / Base / Bear scenario forecast over 1–20 year horizon

---

## Tech Stack

| Layer | Tools |
|---|---|
| Data Collection | Python, yfinance |
| Analysis | Pandas, NumPy, Scipy, Matplotlib, Seaborn |
| Optimisation | Scipy (SLSQP), Monte Carlo Simulation |
| Visualisation | Tableau, Recharts |
| Frontend | React.js |
| Deployment | Netlify |

---

## Project Structure

```
Stock_Analysis/
├── data.ipynb                         # Data extraction & cleaning
├── fa.ipynb                           # Sector & fundamental analysis
├── Portfolio_Optimisation_NSE.ipynb   # Markowitz optimisation notebook
├── stock_data.csv                     # Raw NSE price data (28 stocks)
├── adj_close.csv                      # Processed adjusted close prices
└── portfolio-optimiser/               # React dashboard (deployed on Netlify)
    └── src/
        └── App.js
```

---

## Author

**Govardhan Ingle**  
B.Tech, IIT Gandhinagar | WorldQuant BRAIN Gold Level  
[LinkedIn](#) · [GitHub](#) · [Tableau](https://public.tableau.com/app/profile/govardhan.ingle)
