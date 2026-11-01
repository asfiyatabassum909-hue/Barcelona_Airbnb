# 🏖️ Barcelona Airbnb Market Analysis | Power BI

> **In this June 2026 snapshot, entire-home listings show about 5.7× the estimated annual revenue per listing of private rooms. The 10 highest-revenue host names account for 18% of estimated revenue.** This dashboard explores where those differences appear across Barcelona.

<img width="1811" height="1017" alt="Barcelona Airbnb Power BI dashboard" src="https://github.com/user-attachments/assets/a96ecf94-ba7b-45e8-8130-8309de20e208" />

A one-page Power BI analysis of **15,293 Barcelona Airbnb listings across 69 neighbourhoods**. It compares listing prices, review counts, estimated revenue, and host-name concentration in a point-in-time snapshot.

**Tools:** Power BI · Power Query · DAX  
**Data:** [Inside Airbnb](http://insideairbnb.com/get-the-data/), Barcelona listings. Snapshot scraped 24 June–3 July 2026. Monetary figures are shown in EUR.

> **Interpretation note:** These are descriptive comparisons from listing-level data. Estimated revenue per listing is not profit or a forecast, and differences between room types or areas do not establish that changing a listing’s room type or location would cause the same revenue change.

---

## ⚡ Key Findings

| # | Finding | Evidence in this snapshot |
|---|---|---|
| 1 | **Review counts are concentrated in Eixample.** | Eixample has 484K of 1,027K reviews (about 47%), nearly 4× the next neighbourhood group. Reviews are used as a demand proxy. |
| 2 | **Entire-home listings have higher estimated revenue per listing than private rooms.** | Average nightly price: €285 vs €101 (2.8×). Average estimated annual revenue: €27.2K vs €4.8K (5.7×). These are unadjusted group averages. |
| 3 | **Eixample listings have a higher average nightly price than the city-wide average.** | €309 vs €241, about 28% higher. |
| 4 | **Review volume and estimated revenue per listing do not rank areas the same way.** | Ciutat Vella is second by review count among the groups shown, while its average estimated revenue per listing is €13.7K, compared with €28.5K in Eixample. |
| 5 | **The mean price is above the median.** | Average €241 per night; median €178. This indicates a right-skewed price distribution; high-priced listings may contribute to the gap. |
| 6 | **Revenue is concentrated among the top host names.** | The 10 highest-revenue host names account for about €54.6M (18.0%) of estimated revenue. Names are not unique host identifiers. |

---

## 🎯 Questions

1. Where are listing supply and review counts concentrated?
2. How do average prices vary by neighbourhood and room type?
3. How does estimated revenue per listing vary across those groups?
4. What share of estimated revenue is associated with the highest-revenue host names?
5. What follow-up analysis could help hosts, investors, and strategy teams make better decisions?

---

## 📊 Dashboard Overview

| Section | Visuals | Purpose |
|---|---|---|
| **KPIs** | Total Listings, Median Price, Avg Revenue per Listing, Active Hosts, Top 10 Host Names’ Share | Summarise listing count, price, estimated revenue, and concentration |
| **Location** | Listing map, top 5 neighbourhood groups by review count | Show listing locations and review-count distribution |
| **Pricing** | Average price by room type matrix, top 5 neighbourhoods by average price | Compare listed prices by area and room type |
| **Revenue** | Average estimated revenue by room type matrix, top 10 host names by estimated revenue | Compare estimated revenue and host-name concentration |
| **Narrative** | Key Takeaways box | Summarise the main observations |

**Interactivity:** Neighbourhood Group and Room Type slicers filter the page.  
**Matrix scope:** The matrices show the five largest neighbourhood groups by listing count. City-wide KPI cards use the full filtered dataset.  
**Formatting:** Heatmap shading highlights higher values. The dashboard source line identifies the snapshot date, currency, and estimated nature of revenue.

---

## 🖼️ Two Charts Behind the Story

### 1. Estimated revenue by room type and neighbourhood group

<img width="1365" height="267" alt="Average estimated annual revenue by room type and neighbourhood group" src="https://github.com/user-attachments/assets/8ba5fe21-7cf9-40f1-938c-49bef219e3fe" />

**What it shows:** Average estimated annual revenue per listing (€K) for the five largest neighbourhood groups, split by room type.

**Observed patterns**

- In Eixample, the average is €34.7K for entire-home listings and €6.0K for private rooms (about 5.8×).
- Among the displayed groups, entire-home averages range from €17.2K in Ciutat Vella to €34.7K in Eixample.
- Private-room averages range from €3.2K to €6.0K across the displayed groups.
- Eixample and Gràcia have the highest displayed entire-home averages (€34.7K and €29.4K). Ciutat Vella is lower at €17.2K despite having the second-highest review count among these groups.

**How to read this:** The room-type averages differ substantially in this dataset, but they are not adjusted for listing capacity, availability, location within a group, quality, operating costs, or other factors. They describe listings in the snapshot; they do not estimate the result of converting a private room into an entire home.

*Some room-type cells have small samples (for example, hotel rooms in Sants-Montjuïc and shared rooms in Sant Martí). Treat those individual averages cautiously.*

---

### 2. Estimated revenue by host name

<img width="1355" height="707" alt="Top 10 host names by estimated revenue" src="https://github.com/user-attachments/assets/6b37271a-6a36-43bd-b4ec-53059a1dc140" />

**What it shows:** The ten host names with the highest estimated revenue in the dataset, led by Sweett (€12.39M).

**Observed patterns**

- The top 10 host names account for about €54.6M, or 18.0% of total estimated revenue.
- The top three account for about €27.7M, roughly half of the top-10 total.
- The highest-ranked name has about 4.8× the estimated revenue of the tenth-ranked name.

**How to read this:** This is concentration by the text in `host_name`, not a verified count of distinct operators or businesses. Different hosts can share a name, and one operator may use multiple names. Recalculate by `host_id` before treating this as operator-level concentration.

---

## 🔍 Additional Findings

**Review counts**

- Eixample (484K), Ciutat Vella (128K), Sants-Montjuïc (122K), Gràcia (116K), and Sant Martí (99K) have the highest review counts among the listed neighbourhood groups.
- Review counts are used as a proxy for guest activity; they are not booking counts and may reflect different listing ages or review rates.

**Prices**

- City-wide average nightly price is €241; median is €178.
- By room type, average nightly prices are: entire home/apt €285, hotel room €252, private room €101, and shared room €74.
- Highest average prices among the listed neighbourhoods: Diagonal Mar (€387), Dreta de l’Eixample (€353), Nova Esquerra de l’Eixample (€330), Sant Antoni (€313), and Marina del Prat Vermell (€307). Neighbourhood averages may be sensitive to sample size and listing mix.

**Estimated revenue**

- Average estimated revenue is €21.9K per listing with a non-missing revenue estimate.
- Among the five largest neighbourhood groups, average estimated revenue per listing is: Eixample €28.5K, Gràcia €23.9K, Sant Martí €23.5K, Sants-Montjuïc €21.6K, and Ciutat Vella €13.7K.
- By room type, entire-home listings average €27.2K, hotel rooms €22.8K, and private rooms €4.8K.

**Listings and hosts**

- The dataset contains 15,293 listings and 4,595 distinct `host_id` values (about 3.3 listings per host ID). This is an overall ratio; it does not show how listings are distributed among hosts.

---

## 💡 Implications and Follow-up Tests

| Audience | Observed pattern | Useful next step |
|---|---|---|
| **Investors** | Entire-home listings in Eixample and Gràcia have high estimated revenue averages in this snapshot. | Compare like-for-like listings and include acquisition, operating, tax, and regulatory costs before assessing returns. |
| **Investors** | Sant Martí’s average estimated revenue (€23.5K) is close to Gràcia’s (€23.9K), with 99K reviews. | Examine listing counts, uncertainty, prices, and availability before treating it as an alternative market. |
| **Hosts** | Prices vary by neighbourhood and room type. | Use the matrix as a descriptive benchmark, then compare similar listings and monitor actual booking outcomes. |
| **Hosts** | Entire-home and private-room averages differ substantially. | Treat any room-type conversion as a hypothesis; assess feasibility, costs, capacity, rules, and actual performance first. |
| **Strategy teams** | Review counts and estimated revenue per listing tell different stories across areas. | Segment areas by both measures and validate with booking or occupancy data where available. |
| **Risk teams** | Revenue attributed to the top host names is concentrated. | Recalculate using `host_id` and, where possible, verified operator identities before assessing dependency or regulatory exposure. |

**Suggested experiment:** For listings priced well above comparable neighbourhood × room-type peers, test a controlled price adjustment and compare booking or occupancy outcomes over 90 days. Review counts alone are a delayed and incomplete outcome measure.

---

## 🧹 Data Preparation (Power Query)

| Issue | Action | Reason |
|---|---|---|
| 90 columns in the raw file | Kept the 25 relevant to the analysis | Reduce model size and focus on the stated questions |
| Corrupted characters in names (for example, Gràcia and Sants-Montjuïc) | Corrected text encoding | Avoid split or mismatched category labels |
| `host_since` empty in the source | Dropped | No usable values for this analysis |
| Missing price, bedroom, and review values | Kept as null, not zero | Missing values should not be interpreted as zero |
| No ready-made time fields | Created `review_year`, `review_month`, and `month_number` | Support review-date analysis and month sorting |
| Source price display used `$`, while the source’s price values are in EUR | Formatted displayed monetary values as € | Keep report formatting consistent with the source currency |

---

## 🧮 DAX Measures

```
DAX
Total Listings =
COUNTROWS(Listings)

Median Price =
MEDIAN(Listings[price])

Total Revenue =
SUM(Listings[estimated_revenue_l365d])

Avg Revenue per Listing =
DIVIDE(
    [Total Revenue],
    COUNT(Listings[estimated_revenue_l365d])
)

Active Hosts =
DISTINCTCOUNT(Listings[host_id])

Top 10 Host Name Share % =
VAR RevenueByHostName =
    ADDCOLUMNS(
        VALUES(Listings[host_name]),
        "HostRevenue", [Total Revenue]
    )
VAR Top10HostNames =
    TOPN(10, RevenueByHostName, [HostRevenue], DESC)
RETURN
    DIVIDE(
        SUMX(Top10HostNames, [HostRevenue]),
        CALCULATE([Total Revenue], ALL(Listings[host_name]))
    )
```

- `Avg Revenue per Listing` divides total estimated revenue by the count of listings with a non-missing revenue estimate; missing estimates are not counted as zero.
- `estimated_revenue_l365d` is Inside Airbnb’s estimate for the previous 365 days, not a measure of actual host income.
- The concentration measure ranks `host_name` values. Recalculate it by `host_id` for a distinct-host analysis.
- The denominator removes the host-name filter while retaining other report filters, so the share reflects the current slicer selections.

---

## 🛠️ Skills Demonstrated

| Skill | Evidence in the project |
|---|---|
| Data preparation | Column selection, null handling, and text encoding cleanup |
| DAX | Median, ratios, distinct counts, and Top N share |
| Dashboard design | One-page layout, KPI hierarchy, matrices, and consistent formatting |
| Analysis | Mean vs. median, price vs. estimated revenue, and concentration |
| Communication | Findings, audience-specific follow-up actions, and limitations |

---

## ⚠️ Limitations

- **Revenue is estimated**, not actual host income. It is not profit and does not account for costs.
- **Review count is a proxy for guest activity**, not a count of bookings. Review rates and listing age can vary.
- **Group averages are unadjusted.** Differences may reflect listing mix, capacity, availability, location, or other factors.
- Averages exclude listings with missing values for the relevant measure.
- Some room-type cells and neighbourhood rankings may have small samples, making averages unstable.
- **Host names are not unique identifiers.** The concentration analysis groups by host name; verify it with `host_id` before making claims about distinct hosts or operators.
- The analysis uses a **point-in-time snapshot**, scraped 24 June–3 July 2026. It does not establish current market conditions or trends.

---

## ✅ Conclusion

This project turns 15,293 Airbnb listings into a snapshot of Barcelona’s short-term rental market. Three patterns stand out:

1. **Estimated revenue differs substantially by room type.** Entire-home listings average about 5.7× the estimated revenue per listing of private rooms (€27.2K vs €4.8K). Across the five largest neighbourhood groups, entire-home averages range from €17.2K to €34.7K. These are unadjusted comparisons, so they don’t show what would happen if a host changed room type or location.
2. **Review volume and estimated revenue per listing tell different stories.** Eixample leads in review count, with about 47% of reviews, and averages €28.5K in estimated revenue per listing. Ciutat Vella ranks second in reviews but averages €13.7K per listing, the lowest among the five largest groups.
3. **The price distribution and host-name revenue are concentrated.** The average nightly price (€241) is above the median (€178), and the top 10 host names account for 18% of estimated revenue. The host figure is based on names, which may not uniquely identify hosts or operators.

**For decision-makers**, the dashboard offers a starting point for comparing room types, neighbourhoods, and host-name concentration. Use these patterns alongside listing-level comparisons, operating costs, availability, and local regulations.

**Further analysis** could add calendar data to examine availability and occupancy, and review-level data to explore seasonality. These could help validate the patterns in this snapshot.

This project demonstrates my analytics workflow: cleaning and modelling data, creating DAX measures, designing a dashboard, and translating findings into practical questions for different audiences.
