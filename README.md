# supply_chain_visulization_project
Python data visualization of the DataCo supply chain dataset (180K orders): late delivery rates, shipping performance, # DataCo Supply Chain: Key Performance Overview

A visual analysis of the DataCo Global supply chain dataset (180,519 order line items, 2015 to Jan 2018) using pandas and matplotlib.

![Dashboard](dataco_overview.png)

## Key findings
- **Premium shipping underdelivers:** First Class is late 95.3% of the time and Second Class 76.6%. Standard Class is late 38.1%.
- **Promised vs. actual days:** First Class is scheduled for 1 day but averages 2, and Second Class is scheduled for 2 but averages 4. Standard Class meets its 4-day promise.
- **Sales are flat:** About $1M a month from 2015 to Sep 2017, with profit at roughly 10% of sales.
- **Fishing is the top category** by total profit (about $756K), ahead of Cleats and Camping & Hiking.

## Data note
From Oct 2017 the dataset changes from multiple items per order to one item per order, so sales after that point are not comparable. The trend chart stops at Sep 2017 for that reason.

## Run it
pip install pandas matplotlib seaborn
python dataco_overview.py

Download the dataset (DataCoSupplyChainDataset.csv) and update the file path at the top of the script.

## Tools
Python, pandas, matplotlib, seabornsales trends and category profit.
