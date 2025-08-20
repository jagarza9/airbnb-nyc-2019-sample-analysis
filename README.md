# airbnb-nyc-2019-sample-analysis
Data analysis of Sample Airbnb NYC 2019 using Python and Tableau
## 📌 Business Questions & Key Insights (NYC 2019)

### 1) Which boroughs/neighbourhoods have the highest average nightly price?
- **Top Boroughs (avg price):** Manhattan, Brooklyn, Queens.  
- **Top Neighbourhoods (≥100 listings):** Tribeca, Gramercy, Midtown, Arverne, Financial District.  
- **Evidence:** `reports/figures/borough_avg_price.png`, `data/processed/borough_price_stats.csv`  
- *Note:* Rankings use mean price and exclude extreme outliers (top 1%).

---

### 2) How does room type impact price and availability?
- **Price gap:** *Entire home/apt* averages **~2–3×** the price of *Private room*.  
- **Availability:** High‑price and low‑price listings appear across the full availability range—no clear link between price and `availability_365`.  
- **Business takeaways:**  
  - *Travelers:* Private rooms = best budget value with wide availability.  
  - *Hosts:* Entire home/apt maximizes nightly revenue, but may book fewer nights.  
- **Evidence:** `reports/figures/room_type_share.png`, optional box/scatter by room type.

---

### 3) What’s the relationship between number_of_reviews and price?
- **Insight:** No strong linear relationship—budget listings tend to accumulate more reviews; luxury listings fewer.  
- **(Optional) Add the number:** Pearson r = **`<fill_after_analysis>`**.  
- **Evidence:** `reports/figures/price_vs_reviews.png`.

---

### 4) Which neighbourhoods are the top priced (with sufficient listings)?
- **Premium (>$150):** e.g., **Hell’s Kitchen** and other Manhattan cores (high convenience/attractions).  
- **Mid‑range ($100–130):** **Williamsburg, Harlem** (strong demand, diverse supply).  
- **Budget (<$100):** **Bedford‑Stuyvesant, Bushwick** (popular with younger travelers).  
- **Method:** Ranked by mean price with a **min 100 listings** threshold to avoid small‑sample noise.  
- **Evidence:** `reports/figures/price_box_by_borough.png`, `data/processed/top_neighbourhoods_by_avg_price.csv`.

---

### 🧪 Methods & Assumptions (short)
- Columns standardized; dates/numerics coerced; malformed rows skipped.  
- Prices trimmed at the **99th percentile** to reduce outlier distortion.  
- Analyses based on **NYC 2019** snapshot from InsideAirbnb; results reflect that period only.
  
## 🛠 Tech Stack

- **Python**: Data cleaning, aggregation, visualization  
  - Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`  
- **Jupyter Notebook**: Step-by-step analysis workflow  
- **Tableau**: Interactive dashboard for business storytelling  
- **GitHub**: Version control and portfolio presentation

---

## 📂 Project Structure
airbnb-nyc-2019-analysis/
├─ README.md <- project overview & findings
├─ requirements.txt <- dependencies list
├─ data/
│ ├─ raw/ <- original CSV (not tracked in git)
│ ├─ interim/ <- optional intermediate data
│ └─ processed/ <- clean data for analysis + Tableau
├─ notebooks/
│ └─ 01_airbnb_nyc_2019.ipynb <- main analysis workflow
├─ src/
│ ├─ io_utils.py <- load/save helpers
│ ├─ clean.py <- cleaning & feature engineering
│ └─ viz.py <- plotting utilities
└─ reports/
├─ figures/ <- exported PNGs for README
└─ tableau/ <- Tableau packaged workbook (.twbx)
