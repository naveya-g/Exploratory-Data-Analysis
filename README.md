# 📊Exploratory Data Analysis - Sports & Startup Ecosystem

This project uses statistical analysis, data visualization, and hypothesis testing to uncover meaningful patterns and validate findings across two real-world domains: Basketball Sports Tournaments and the Global Startup Ecosystem.

---

### Project Objective

To understand what the data is telling us - by looking at patterns, spotting trends, and using statistical tests to confirm whether what we observe is actually true or just by chance. 
The goal is to **turn raw data into clear, actionable insights for making better investment and business decisions**.

---

### Dataset Summary

**Part 1 - Sports (Basketball Tournaments)**
- Basketball tournament records across multiple teams and seasons
- Key features: Games Played, Games Won, Games Lost, Baskets Scored, Baskets Given, Tournament Champion, Runner-up, Team Launch Year, Highest Position Held
- Key challenges: mixed data formats in TeamLaunch column, presence of `-` as missing values, data type inconsistencies

**Part 2 - Startup Ecosystem (Startup Battlefield)**
- Data from the world's pre-eminent startup competition - **Startup Battlefield**
- Key features: Company Name, Funding Raised, Operating State (Operating / Closed), Result (Winner / Contestant), Event Name & Year
- Key challenges: funding column in mixed formats (K, M, B), null values, and outliers in funding data

---

### Analysis Workflow
 
**Part 1 — Sports**
- Replaced `-` placeholders with NaN, converted object columns to float, and extracted only the launch year from the mixed-format `TeamLaunch` column
- Performed Univariate and Bivariate analysis using histograms and box plots; narrowed focus to the **Top 20 best-performing teams** sorted by wins
- Plotted a **correlation heatmap** and **multi-line plot** on top 20 teams — confirmed Team 1 as best overall performer with highest scores and lowest baskets given
- Computed **Win Probability (59.6%)** and Loss Probability per team; provided data improvement suggestions across **5V dimensions** (Quality, Quantity, Variety, Velocity, Veracity)
---
**Part 2 — Startup Ecosystem**
- Dropped rows with missing funding values and converted the `Funding` column from mixed string format (e.g. $500K, $2M, $1B) into a clean numerical `Funds_in_Million` column
- Detected and removed outliers using the **IQR upper fence method**; visualized funding distribution for Operating vs Closed companies using KDE plots
- Calculated the **percentage of winners still operating** vs **percentage of contestants still operating** to compare survival rates across both groups
- Filtered all events containing the keyword **"disrupt"** from **2013 onwards** using a row-wise lambda function

---

### Statistical Analysis & Hypothesis Testing

| Question | Test Used | Conclusion |
|---|---|---|
| Is there a significant difference in funds raised between Operating vs Closed companies? | Two-Sample Independent T-Test | No significant difference - funding alone does not determine survival |
| Is the proportion of operating companies different between Winners and Contestants? | Z-Test for Proportions + Chi-Square Test | Significant difference - winners have a higher operating rate than contestants |

---

### Tools Used

- Python, NumPy, Pandas, Matplotlib, Seaborn
- Statistical Testing: `scipy.stats` (T-Test, Chi-Square), `statsmodels` (Z-Test for Proportions)
- Visualization: Histograms, Box Plots, Bar Plots, Line Plots, Scatter Plots, Heatmaps, KDE Distribution Plots
- Environment: Google Colab

---

### 🔍 Use Case

**Part 1** helps sports investors and team managers identify consistently high-performing basketball teams based on historical data - enabling smarter sponsorship, scouting, and investment decisions.

**Part 2** helps venture capitalists and analysts understand what separates surviving startups from those that shut down - using competition results and funding patterns to guide investment strategy.
