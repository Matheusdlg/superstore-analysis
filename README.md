# Superstore Project — Sales and Profitability Analysis

Exploratory analysis of Superstore sales data (2014–2017), focused on understanding not just how much the company sells, but whether that growth translates into healthy profitability.

## Business question

The company sells a lot, but is it turning that into profit efficiently? Or is sales growth masking profitability problems in specific parts of the business?

---

## Key Findings

### 1. Sales, profit, and quantity grew year over year

![Annual Sales, Quantity and Profit](images/ss_chart1_annual.png)

| Year | Sales   | Quantity | Profit |
|------|---------|----------|--------|
| 2014 | 484,247 | 7,581    | 49,543 |
| 2015 | 470,532 | 7,979    | 61,618 |
| 2016 | 609,205 | 9,837    | 81,795 |
| 2017 | 733,215 | 12,476   | 93,439 |

Growth accelerates from 2016 onward and is accompanied by a real increase in units sold — not just a price effect.

---

### 2. Profit margin, however, stayed flat (~12%)

![Profit Margin by Year](images/ss_chart2_margin.png)

| Year | Margin |
|------|--------|
| 2014 | 11.81% |
| 2015 | 11.75% |
| 2016 | 12.97% |
| 2017 | 11.59% |

This shows the company grew in **scale**, but not in **efficiency**: profit went up because more was sold, not because each sale became more profitable.

---

### 3. The problem is concentrated in Furniture

![Profit by Furniture Subcategory](images/ss_chart3_furniture.png)

- **Technology**: highest sales volume and good margin — healthy growth
- **Office Supplies**: balanced behavior across sales, profit, and margin
- **Furniture**: high sales volume, but compromised profitability

Within Furniture, at the subcategory level:

- **Chairs**: highest volume, positive profit (+26.5k)
- **Furnishings**: lower sales, positive profit
- **Bookcases**: negative profit (-3.4k)
- **Tables**: significant loss (-17.7k)

Average discount is higher in these problematic subcategories, but discount alone doesn't explain the negative result.

---

### 4. Category trajectories diverge over time

![Sales Evolution by Category](images/ss_chart4_categories.png)

Technology and Office Supplies show steady, healthy growth year over year. Furniture's trajectory is more volatile and lags behind the other two categories — reinforcing that its profitability issue isn't a one-off, but a sustained pattern across the analyzed period.

---

### 5. Clear seasonality, concentrated in Q4

![Monthly Seasonality](images/ss_chart5_seasonality.png)

Sales are lowest in January and February, and rise consistently in the last quarter (September–December), likely driven by year-end purchases. This pattern repeats across the years in the dataset, suggesting it's structural and can be planned for.

---

### 6. A small group of subcategories drives most of the profit

![Top 10 Subcategories by Profit](images/ss_chart6_top10.png)

The top 10 subcategories by profit are dominated by Technology and Office Supplies items, with Chairs as the strongest Furniture performer. This concentration reinforces where investment and attention are already paying off — and highlights, by contrast, how much Tables and Bookcases are dragging down the Furniture category.

---

## Conclusion

The company shows consistent growth, but there are clear opportunities to improve financial efficiency. The analysis pinpointed the problem: the Tables (-17.7k profit) and Bookcases (-3.4k profit) subcategories are generating losses that drag down the overall margin. Meanwhile, Chairs (+26.5k profit) and the Technology category show that growing profitably is possible — the problem isn't structural, it's specific.

Based on this, next steps would be to:

- **Review pricing and discount policy for Tables and Bookcases**, since these subcategories have relevant sales volume but are in the red — fixing this has direct potential to turn losses into profit.
- **Direct more investment and attention toward Technology and Chairs**, replicating what's working there across the rest of the portfolio.
- With these two actions, the goal is to **raise the profit margin beyond the current 12%** in upcoming cycles, without relying solely on higher sales volume.

---

## About the dataset

- **9,994 rows** and **21 columns**
- No null values and no duplicate records
- Each row represents an item within an order (a single `Order ID` can repeat when an order contains more than one product)
- This is the classic **Sample Superstore** dataset (widely used for Tableau/Power BI practice, sourced from Kaggle), not real company data

---

## Repository structure

```
superstore-analysis
│
├── data/
│   └── Sample - Superstore.csv       # Original dataset used in the analysis
│
├── notebooks/
│   ├── 01_eda.ipynb                  # Initial exploratory data analysis and cleaning
│   ├── 02_category_analysis.ipynb    # Deep dive into categories and subcategories
│   └── 03_time_analysis.ipynb        # Time trend and seasonality analysis
│
├── images/
│   ├── ss_chart1_annual.png
│   ├── ss_chart2_margin.png
│   ├── ss_chart3_furniture.png
│   ├── ss_chart4_categories.png
│   ├── ss_chart5_seasonality.png
│   └── ss_chart6_top10.png
│
└── README.md
```

---

## Tools used

- Python
- Pandas
- Matplotlib
- Google Colab

---

## How to run

1. Clone the repository
2. Open `notebooks/01_eda.ipynb` in Google Colab or Jupyter (then `02_category_analysis.ipynb` and `03_time_analysis.ipynb`, in order)
3. Adjust the CSV read path to `data/Sample - Superstore.csv`
4. Run the cells in order
