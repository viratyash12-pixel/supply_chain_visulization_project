# 📦 DataCo Supply Chain Analysis

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-EDA-150458?logo=pandas&logoColor=white)
![Chart.js](https://img.shields.io/badge/Chart.js-Dashboard-FF6384?logo=chartdotjs&logoColor=white)
![Status](https://img.shields.io/badge/status-in%20progress-yellow)

Exploratory analysis and an interactive dashboard for the DataCo Global supply chain dataset (180,519 order line items). 🚚📊

👉 **Jump to:** [Dataset](#-dataset) · [Dashboard](#-interactive-dashboard) · [Findings](#-findings) · [Setup](#%EF%B8%8F-setup)

## 🗂️ Dataset

- **Source:** DataCo Global Supply Chain Dataset (CSV, not included because of its size)
- **Size:** 180,519 order line items, 53 columns
- **Covers:** orders, customers, products, shipping modes, delivery status, sales and profit across five markets (LATAM, Europe, Pacific Asia, USCA, Africa)

## 🖥️ Interactive Dashboard

Open `dataco_dashboard.html` in any browser. It's a single file with no server needed.

- 🎛️ **Filters:** market, shipping mode, year
- 🔢 **KPIs:** sales, profit, late delivery rate, average shipping days
- 📈 **Charts:** monthly sales and profit, late rate by shipping mode, top 10 categories by profit
- 🌙 **Theme:** follows light or dark mode

> ⚠️ Data is limited to Jan 2015 – Sep 2017. From Oct 2017 the dataset switches to one item per order, so later sales aren't comparable.

## 💡 Findings

| Metric | Result |
|---|---|
| ✅ Profitable order lines | 145,558 (80.6%) |
| ❌ Loss-making order lines | 33,784 (18.7%) |
| ⚖️ Breakeven order lines | 1,177 (0.7%) |
| 🚚 Late deliveries | 98,977 lines (54.8%) |
| ⏰ Mean profit, late orders | $21.62 |
| ✅ Mean profit, on-time orders | $22.40 |

- 🥇 **First Class is late 95.3% of the time** and Second Class 76.6%. Standard Class is late 38.1%.
- ⏱️ First Class is scheduled for 1 day but averages 2, and Second Class is scheduled for 2 but averages 4. Standard Class meets its 4-day promise.
- 🎣 Fishing is the top category by profit (about $756K).
- 📉 Late orders earn only $0.78 less per line, so delays alone don't explain the losses.

<details>
<summary>🔍 <b>What the notebook does</b> (click to expand)</summary>

1. 📥 **Load and inspect:** shape, dtypes, statistics, duplicates, missing values
2. 🧹 **Clean:** drop personal, redundant and single-valued columns; convert dates
3. 📊 **Profile categoricals:** payment type, shipping mode, delivery status, market
4. 🛠️ **Engineer features:** processing time, delayed flag, order month/day/hour, profit flag
5. 📈 **Analyze:** profit distribution and late vs on-time profit

</details>

<details>
<summary>🧰 <b>Tech stack</b> (click to expand)</summary>

Python 🐍, pandas 🐼, NumPy, matplotlib, seaborn, Chart.js

</details>

## ⚙️ Setup

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook supply_chain.ipynb
```

Download the CSV and set the path in the `pd.read_csv(...)` cell.

## 🚀 Next steps

- [ ] 🔎 Break profit down by shipping mode, category and market
- [ ] 📋 Add a detail table to the dashboard
- [ ] 🤖 Model late-delivery risk with a classifier

## 🔒 Data privacy

The raw file includes customer names and street addresses. Don't commit the CSV to a public repo. 🚫
