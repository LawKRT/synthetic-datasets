# LuxDevHQ Week 9 Assignment — Introduction to Python

## Overview
This repository contains Python code and output files for Week 9 assignments
covering JSON data extraction, API consumption, and CSV export.

---

## Part 2 — Synthetic JSON Dataset from GitHub

**Tool used:** Mockaroo (mockaroo.com)  
**Dataset:** 100 synthetic employee records  
**Fields:** id, first_name, last_name, email, country, salary, department, hire_date  

**Process:**
1. Generated dataset on Mockaroo and exported as JSON
2. Uploaded JSON file to this GitHub repository
3. Used `requests.get()` to fetch the raw file from GitHub
4. Parsed the response with `response.json()` into a Python list
5. Converted to a pandas DataFrame using `pd.DataFrame()`
6. Cleaned date and salary columns
7. Exported final output as `mock_employees.csv`

**Output file:** `mock_employees.csv`

---

## Part 3 — DummyJSON API Endpoints

### Products — https://dummyjson.com/products
- Fetched all 194 products using `limit=0` parameter
- Flattened nested fields (dimensions, meta) using `pd.json_normalize()`
- Dropped list-type columns (images, tags, reviews) not suited for CSV
- Exported as `dummyjson_products.csv`

### Carts — https://dummyjson.com/carts
- Fetched all 20 carts
- Produced two output tables:
  - **Cart summary** — one row per cart with totals and user reference
  - **Cart items** — one row per product per cart (exploded from nested list)
- Exported as `dummyjson_carts_summary.csv` and `dummyjson_cart_items.csv`

---

## Files in This Repository

| File | Description |
|---|---|
| `MOCK_DATA.json` | Raw synthetic dataset from Mockaroo |
| `mock_employees.csv` | Cleaned output from Part 2 |
| `dummyjson_products.csv` | All products from DummyJSON API |
| `dummyjson_carts_summary.csv` | Cart-level totals from DummyJSON API |
| `dummyjson_cart_items.csv` | Individual items per cart from DummyJSON API |
| `week9_assignment.ipynb` | Full Jupyter Notebook with all code |

---

## Libraries Used
- `requests` — HTTP calls to GitHub raw URLs and DummyJSON API
- `pandas` — DataFrame construction, cleaning, and CSV export
- `json` — Raw response inspection

## How to Run
1. Clone this repository
2. Install dependencies: `pip install requests pandas`
3. Open `week9_assignment.ipynb` in Jupyter Notebook
4. Run all cells top to bottom
