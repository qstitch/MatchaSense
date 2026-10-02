````markdown
# MatchaSense

A data pipeline and pricing model for matcha products: collecting a custom
dataset, cleaning and analyzing it with pandas and numpy, and predicting
price per gram with scikit-learn.

## Motivation & Question

Matcha prices vary widely across brands, grades, and origins, and it's
hard to tell what's actually driving the price of a given product. This
project asks: **what factors drive matcha price per gram, and can we
predict it from product attributes?**

## Data

- **Source(s):** Manually collected from online matcha retailers into a
  Google Sheet, then exported to CSV. Source URL, date collected, and
  currency are recorded per row.
- **Size:** 50 products (initial collection; more rows are being added to
  improve coverage across grades and origins — see Limitations).
- **Data dictionary:**

| Column | Type | Description |
|---|---|---|
| brand | string | Brand or producer name |
| product_name | string | Product/listing name |
| grade | string | Matcha grade (e.g. ceremonial, premium, culinary) |
| weight | numeric | Net weight of the product (g) |
| origin | string | Country of origin |
| region | string | Growing region within the origin country |
| organic | boolean | Whether the product is certified organic |
| price | numeric | Listed price |
| rating | numeric | Average customer rating |
| num_reviews | numeric | Number of customer reviews |
| notes | string | Free-text notes |

- **Limitations:** Small initial sample (n=50); online-retailer selection
  bias; prices are a snapshot at time of collection and may not reflect
  current pricing.

## Project Structure

````
data/raw/           raw, unmodified exports (never hand-edited)
data/processed/      cleaned data produced by src/clean.py
notebooks/           exploratory analysis and modeling notebooks
src/                 reusable pipeline code (cleaning, features, modeling)
reports/figures/     saved plots and visualizations
````

## Setup & Usage

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Pipeline commands (added as each stage is built):

```bash
python src/clean.py          # data/raw -> data/processed
jupyter notebook notebooks/   # EDA and modeling
```

## Methodology

_To be filled in as cleaning, feature engineering, and modeling decisions
are made._

## Results

_To be filled in once the model is trained and evaluated._

## Limitations & Future Work

- Current sample size (n=50) limits how well the model generalizes;
  collection is ongoing toward ~100-150 rows.
- Online-only sourcing may not represent the full matcha market.
- Price is a single snapshot in time, not tracked over time.

## Status

- [x] Data collection (initial)
- [ ] Data cleaning
- [ ] Exploratory data analysis
- [ ] Predictive model
- [ ] Final write-up
````