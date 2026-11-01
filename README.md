# 🏖️ Barcelona Airbnb Market Analysis | Power BI

> **Entire homes earn ~5.7x more than private rooms in Barcelona, and just 10 hosts control 18% of the revenue.** This dashboard shows how I got there.

<img width="1811" height="1017" alt="BCN airbnb ss" src="https://github.com/user-attachments/assets/a96ecf94-ba7b-45e8-8130-8309de20e208" />

A one-page Power BI dashboard analysing **15,293 Barcelona Airbnb listings across 69 neighbourhoods**. It shows where demand, pricing, and revenue are concentrated and what that means for hosts, investors, and strategy teams.

**Tools:** Power BI · Power Query · DAX

**Data:** [Inside Airbnb](http://insideairbnb.com/get-the-data/), Barcelona listings, snapshot June 2026 (all prices and revenue in EUR)

---

## ⚡ Key Findings

| # | Finding | Evidence |
|---|---|---|
| 1 | **Demand is concentrated in one area.** Eixample holds nearly half of all reviews. | 484K of 1,027K reviews (~47%), almost 4x the next group |
| 2 | **Entire homes earn far more than their price premium suggests.** | Price 2.8x higher (€285 vs €101), estimated revenue 5.7x higher (€27.2K vs €4.8K) |
| 3 | **Location sets the price.** Eixample is ~28% above the city average. | Eixample €309 vs city average €241 |
| 4 | **High review volume does not mean high revenue.** Ciutat Vella is #2 for reviews but earns the least per listing of the top 5 groups. | €13.7K vs €28.5K in Eixample; also the lowest average price (€192) |
| 5 | **A few luxury listings pull averages up.** | Median price €178 vs average €241 |
| 6 | **Professional operators capture a large share of revenue.** | Top 10 hosts hold 18.0% of estimated revenue (~€54.6M) |

---

## 🎯 Business Questions
1. Where is guest demand concentrated?
2. Which areas and room types command premium prices?
3. Where is estimated revenue potential highest?
4. How concentrated is the market among hosts?
5. What should hosts and investors do with this?

---

## 📊 Dashboard Overview

| Section | Visuals | Purpose |
|---|---|---|
| **KPIs** | Total Listings, Median Price, Avg Revenue per Listing, Active Hosts, Top 10 Hosts' Share | Market size, price level and concentration at a glance |
| **Location** | Map of listings, Top 5 Neighbourhood Groups by Reviews | Where supply and demand sit |
| **Pricing** | Avg Price by Room Type (heatmap matrix), Top 5 Neighbourhoods by Avg Price | Price premiums by area and room type |
| **Revenue** | Avg Est. Annual Revenue by Room Type (heatmap matrix), Top 10 Hosts by Est. Revenue | Earning potential and host concentration |
| **Narrative** | Key Takeaways box | The story in four lines |

**Interactivity:** the Neighbourhood Group and Room Type slicers filter the whole page.

**Design choices**
- The matrices show the **top 5 groups by listings**, so city-wide totals stay in the KPI cards. This keeps the tables readable and avoids partial totals that disagree with the headline numbers.
- Heatmap shading highlights the highest values.
- A source line states the snapshot date, the currency and that revenue is estimated.

---

## 🖼️ Deep Dive: Two Charts That Drive the Story

### 1. Where the money is: revenue by room type and area
![Avg Est. Annual Revenue by Room Type](images/revenue-matrix.png)

**What it shows:** average estimated annual revenue per listing (€K) for the five largest neighbourhood groups, split by room type, with heatmap shading.

**What I found**
- **Room type matters more than location.** Within Eixample, an entire home earns **€34.7K** vs **€6.0K** for a private room (~5.8x). Across areas, entire homes vary only about 2x (€17.2K in Ciutat Vella to €34.7K in Eixample).
- **Private rooms earn little everywhere.** They stay in a narrow €3.2K to €6.0K band regardless of area, so a better neighbourhood does not fix a low-yield room type.
- **Eixample and Gràcia lead for entire homes** (€34.7K and €29.4K), while Ciutat Vella lags (€17.2K) despite being the #2 area for reviews.

**Business meaning**
- An **investor** should weigh unit type before neighbourhood: whole-unit rentals deliver far more revenue per listing.
- A **host** renting out single rooms can test converting them to whole-unit listings, since that is where the revenue gap is.
- A **strategy team** should treat high-review areas like Ciutat Vella as high-volume, lower-yield markets, not as high-revenue ones.

*Caution:* a few cells (for example hotel rooms in Sants-Montjuïc, shared rooms in Sant Martí) likely rest on small samples, so I did not base recommendations on them.

---

### 2. Who captures the revenue: host concentration
![Top 10 Hosts by Estimated Annual Revenue](images/top-hosts.png)

**What it shows:** the ten hosts with the highest estimated annual revenue, led by Sweett (€12.39M).

**What I found**
- The top 10 hosts account for **~€54.6M, or 18.0% of all estimated revenue**, while being about **0.2% of the 4,595 active hosts**.
- The **top 3 hosts alone earn ~€27.7M**, roughly half of the top-10 total.
- The #1 host earns **~4.8x** the #10 host, so revenue is steeply skewed even among the largest operators.

**Business meaning**
- The market is **professionalised**: management companies, not individual homeowners, capture a large share of revenue.
- For a **new host or investor**, competing on price and quality against operators with scale is hard, so niche positioning (a specific area or unit type) is more realistic.
- For **platform and strategy teams**, concentration is both a **partnership opportunity** (a few accounts drive large volume) and a **risk** (dependence on a handful of operators, plus regulatory exposure).

*Caution:* hosts are grouped by name, so a very common name could combine different people. A host ID-based check would confirm the figures.

---

## 🔍 More Insights

**Demand**
- Review volume ranks Eixample (484K), Ciutat Vella (128K), Sants-Montjuïc (122K), Gràcia (116K) and Sant Martí (99K).
- Review counts are used as a proxy for booking activity.

**Pricing**
- The city average is €241 per night, but the median is €178, so a small number of high-priced listings skew the average upward.
- By room type: entire home/apt €285, hotel room €252, private room €101, shared room €74.
- The top neighbourhoods by average price are Diagonal Mar (€387), Dreta de l'Eixample (€353), Nova Esquerra de l'Eixample (€330), Sant Antoni (€313) and Marina del Prat Vermell (€307).

**Revenue**
- Average estimated annual revenue is €21.9K per listing.
- Among the top 5 groups: Eixample €28.5K, Gràcia €23.9K, Sant Martí €23.5K, Sants-Montjuïc €21.6K, Ciutat Vella €13.7K.
- Entire homes average €27.2K vs €4.8K for private rooms. Hotel rooms (€22.8K) also out-earn private rooms.

**Supply**
- 4,595 active hosts operate 15,293 listings, about 3.3 listings per host, which confirms how common multi-property operators are.

---

## 💡 Recommendations

| Audience | Recommendation | Why |
|---|---|---|
| **Investors** | Prioritise entire-home listings in Eixample and Gràcia | Highest price and revenue per listing |
| **Investors** | Consider Sant Martí as a strong alternative | Revenue (€23.5K) close to Gràcia (€23.9K) with solid demand (99K reviews) |
| **Hosts** | Benchmark nightly rates against the neighbourhood × room-type matrix | Prices well above peers risk lower bookings |
| **Hosts** | Where possible, offer whole-unit rentals instead of single rooms | ~5.7x revenue gap |
| **Strategy teams** | Treat Ciutat Vella as a volume market and Eixample / Diagonal Mar as premium markets, with separate pricing | Similar demand, very different revenue per listing |
| **Strategy / risk** | Monitor the top professional hosts as partners or a concentration risk | Top 10 hold 18% of estimated revenue |

**Suggested next test:** adjust prices by ~10% on listings priced well above their neighbourhood × room-type average and compare bookings and reviews over 90 days.

---

## 🧹 Data Preparation (Power Query)

| Issue | Action | Reason |
|---|---|---|
| 90 columns in the raw file | Kept the 25 that support the questions | Lighter, faster model |
| Corrupted characters in names (Gràcia, Sants-Montjuïc) | Fixed the encoding | Prevents split or mismatched groups |
| `host_since` empty in source | Dropped | No analytical value |
| Nulls in price, bedrooms, reviews | **Kept as null, not 0** | Zeros would pull averages down |
| No ready-made time fields | Created `review_year`, `review_month`, `month_number` | Time analysis with correct month order |
| Price shown with "$" but quoted in EUR | Formatted all money as **€** | Matches the actual currency in the source price quotes |

---

## 🧮 DAX Measures

```DAX
Total Listings = COUNTROWS(Listings)

Median Price = MEDIAN(Listings[price])

Total Revenue = SUM(Listings[estimated_revenue_l365d])

Avg Revenue per Listing =
DIVIDE([Total Revenue], COUNT(Listings[estimated_revenue_l365d]))

Active Hosts = DISTINCTCOUNT(Listings[host_id])

Top 10 Host Share % =
DIVIDE(
    SUMX(
        TOPN(10, VALUES(Listings[host_name]), [Total Revenue]),
        [Total Revenue]
    ),
    CALCULATE([Total Revenue], ALL(Listings[host_name]))
)
```

- `Avg Revenue per Listing` divides by the **count of listings that have a revenue estimate**, so listings without one are not treated as zero earnings.
- `estimated_revenue_l365d` is Inside Airbnb's revenue estimate for the last 365 days.

---

## 🛠️ Skills Demonstrated

| Skill | Where it shows |
|---|---|
| Data cleaning and modelling | Power Query steps, null handling, encoding fixes |
| DAX | Median, ratio, distinct count and Top N share measures |
| Dashboard design | One-page layout, KPI hierarchy, heatmaps, consistent formatting |
| Analytical thinking | Median vs average, price vs revenue, concentration analysis |
| Business communication | Key findings, recommendations by audience, limitations |

---

## ⚠️ Limitations
- **Revenue is an estimate**, not actual host income. Inside Airbnb does not publish bookings or payouts.
- **Review count is a proxy for demand**, not a count of bookings.
- Averages exclude listings with missing price or revenue data.
- Some room-type cells have few listings (shown blank where there are none), so single values can be unstable.
- **Host names are not unique identifiers.** The concentration analysis groups by host name, so very common names may be combined.
- The data is a **point-in-time snapshot** (scraped 24 June to 3 July 2026).

## 🚀 Next Steps
- Add the **calendar** table (availability and occupancy) to validate revenue estimates
- Add the **reviews** table for seasonality and sentiment analysis
- Test price against review scores to explore value for money
- Add a minimum-listings rule to neighbourhood price rankings to reduce small-sample effects

---

## 📁 Repository
```
├── Barcelona_Airbnb.pbix
├── data/                  # or a link to Inside Airbnb
├── images/
│   ├── dashboard.png
│   ├── revenue-matrix.png
│   └── top-hosts.png
└── README.md
```

## 👩‍💻 About Me
**Asfiya Tabassum**: Data / BI Analyst | B.Sc. Computer Science | 2+ years in KYC, compliance and fraud investigation at Accenture, where I worked with large datasets and risk-based decision-making. I now apply that analytical mindset to turning data into business insight.

📧 asfiyatabassum909@gmail.com · [LinkedIn](https://linkedin.com/in/asfiya-tabassum-554a3035b) · [GitHub](https://github.com/asfiyatabassum909-hue)

⭐ *If you found this useful, feel free to star the repo!*
