---
title: Mastering pd.merge() in Pandas
emoji: 🔗
colorFrom: blue
colorTo: purple
sdk: static
pinned: false
---

# Mastering pd.merge() in Pandas

A complete, hands-on guide to merging DataFrames in Pandas using the **Chinook database** — a realistic sample dataset modelling a digital music store with customers, invoices, tracks, artists, and employees across 11 related tables.

All examples are written and tested in **Google Colab** with real data and real outputs.

📖 **Full article:** [Mastering pd.merge() in Pandas — datatodeploy.com](https://datatodeploy.com/mastering-pd-merge-in-pandas/)

---

## What You Will Learn

- How `pd.merge()` works and how it maps to SQL JOIN operations
- All four join types — inner, left, right, and outer — with real use cases
- Merging on differently named columns with `left_on` and `right_on`
- Handling duplicate column names with custom `suffixes`
- Multi-key merges across multiple tables
- Validating merge results with the `validate` parameter
- Performance tips for large DataFrames
- When to use `pd.merge()` vs `pd.concat()` vs `DataFrame.join()`
- A complete five-table analysis pipeline answering a real business question

---

## Dataset

This notebook uses the **Chinook database** — a free, open-source sample database representing a digital music store.

| Table | Rows | Description |
|---|---|---|
| `Customer` | 59 | Customer records |
| `Invoice` | 412 | Purchase invoices |
| `InvoiceLine` | 2,240 | Individual line items |
| `Track` | 3,503 | Music tracks |
| `Album` | 347 | Albums |
| `Artist` | 275 | Artists |
| `Genre` | 25 | Music genres |
| `Employee` | 8 | Staff records |

The database is downloaded automatically inside the notebook — no manual downloads needed.

Original source: [Chinook Database by Luis Rocha](https://github.com/lerocha/chinook-database)

---

## Getting Started

### Run in Google Colab (recommended)

Click the badge below to open the notebook directly in Google Colab — no setup required:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/arashhadadex/YOUR-REPO-NAME/blob/main/pd_merge_guide.ipynb)

### Run locally

**1. Clone the repo**

```bash
git clone https://github.com/arashhadadex/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
```

**2. Install dependencies**

```bash
pip install pandas numpy
```

**3. Open the notebook**

```bash
jupyter notebook pd_merge_guide.ipynb
```

The Chinook database is downloaded automatically in the first cell — no additional files needed.

---
---

## Key Takeaways

```python
# Basic merge syntax
pd.merge(left, right, how='inner', on='column_name')

# Differently named columns
pd.merge(df1, df2, left_on='customer_id', right_on='CustomerId')

# Custom suffixes
pd.merge(df1, df2, on='TrackId', suffixes=('_sold', '_catalog'))

# Validate relationship type
pd.merge(df1, df2, on='CustomerId', validate='1:m')
```

---

## Related Articles

This notebook is a standalone guide. Other articles in the datatodeploy.com Python and data science series:

- [Pandas DataFrame Visualization in One Line of Code](https://datatodeploy.com/exploring-pandas-dataframe-visualization-in-one-line-of-code/)
- [Building Interactive Dashboards with Plotly Dash](https://datatodeploy.com/plotly-dash-interactive-dashboards-python/)
- [Building a Sales Dashboard with Plotly Dash](https://datatodeploy.com/plotly-dash-sales-dashboard-tutorial/)

---

## License

MIT

---

*Built by [Arash](https://datatodeploy.com) — data science tutorials, Python guides, and deployment walkthroughs.*
