# Bicycle Retail Data Analysis (Interactive Dashboard created using MS Excel)
## Project Objective
This project transforms raw consumer transactional pipelines into an interactive **Bicycle Retail Performance & Customer Segmentation Dashboard**. Utilizing a database of 538 distinct consumer profiles across Europe, North America, and the Pacific regions, the project maps demographic behavior, commuting obstacles, and wealth brackets to isolate the exact variables that drive a customer to purchase a bicycle.

---
## Dataset Used
- <a href="https://github.com/OpokuManuel/Bicycle-Retail-Data-Analysis/blob/main/Bicycle_Retail_Performance.xlsx">Bicycle Data </a>

---

## Key Project Metrics (KPIs) & Findings
Based on the programmatic synthesis of the data modeling matrix, the final dashboard monitors several key performance indicators:
* **Target Audience Sweet Spot:** **Middle-Aged consumers** represent the core buying engine, capturing **185 out of the 231 total bike sales** (80.1%). 
* **The Income Gap:** Across all demographics, buyers possess a higher average income (**\$60,346**) compared to non-buyers (**\$57,491**).
* **Commute Friction Threshold:** Bike purchasing peaks heavily among individuals with a short commute of **0–1 miles (98 buyers)**, but falls off drastically past the **10+ miles mark (only 13 buyers)**.
* **Vehicle Clutter Correlation:** Individuals who do not buy a bicycle own a higher average number of cars (**1.64 cars**) compared to those who do (**1.13 cars**).

---
**Dashboard Interaction** <a href="https://github.com/OpokuManuel/Bicycle-Retail-Data-Analysis/blob/main/Dashboard.png">View Dashboard </a>

---
## Data Architecture & Tech Stack
* **Storage Engine:** Excel OpenXML Spreadsheet Structure (`.xlsx`)
* **ETL Pipeline:** **Power Query** (Used for schema standardization, text expansion, and variable-bucket clustering).
* **Data Modeling:** **Power Pivot** (Enforcing structural logic and cross-attribute profiling).
* **Visualization Layer:** Dynamic PivotTables, Integrated Slicers, and Grouped Performance Deltas.

---

## Data Cleaning & Transformation Pipeline
The raw extract contained shorthand variables and continuous floats that required rigid parsing in **Power Query** prior to modeling:
1. **Shorthand Standardization:** Expanded `Marital Status` (`M`/`S` -> `Married`/`Single`) and `Gender` (`F`/`M` -> `Female`/`Male`) schemas to guarantee cleaner presentation.
2. **Conditional Binning (Age Range):** Programmed a conditional column logic to bucket structural ages into discrete, highly targetable generational bands:
   * `Adolescent`: Age < 30
   * `Middle Age`: Age 30 to 54
   * `Old`: Age 55+
3. **Commute Distance Mapping:** Standardized text strings to ensure uniform layout structures across geographical data points (e.g., parsing `10+ Miles` cleanly to `More than 10 miles`).

---

## Deep-Dive Statistical Analysis & Insights
Analyzing the database across overlapping parameters highlights distinct behavioral, economic, and logistical correlations:

### 1. Income Dispersion vs. Conversion Lift
* **The Buyer Wealth Premium:** Across both gender segments, bike conversion rates share a positive correlation with higher income brackets. 
* **Gender Wealth Disparity:** Male buyers hold the highest average purchasing power at **\$61,300**, running \$2,041 ahead of Female buyers (\$59,259). This suggests premium marketing lines yield stronger conversions when targeted at high-earning male segments.

### 2. Vehicle Clutter & Inverse Purchase Correlation
* **Displacement Effect:** A clear inverse relationship exists between car ownership density and bicycle acquisition. 
* **Auto-Dependency Thresholds:** Non-buyers maintain a significantly higher average car density (**1.64 cars per household**) compared to buyers (**1.13 cars**). Households holding 4 cars average an income of **\$111,875**, yet almost universally reject bicycle purchasing due to strong systemic car dependency.

### 3. Logistical Friction & Commute Decay Models
* **The 2-to-5 Mile Spike:** While sheer conversion volume peaks at ultra-short distances (0–1 miles yielding 98 buyers), the actual *proportion* of conversions hits its peak velocity in the **2–5 miles segment** (44 buyers vs. 37 non-buyers). This indicates an ideal market sweet spot where the distance is too far to walk comfortably but highly efficient for cycling.
* **The 10+ Mile Drop-Off:** At 10+ miles, utility collapses completely—conversions plummet to a minor **20.6% success rate** (13 buyers out of 63 profiles), exposing a distance threshold where alternative regional transit dominates.

### 4. Generational Cohort Volume Deficits
* **Middle-Aged Dominance:** The middle-aged bracket is the absolute bedrock of the business, generating **380 out of 538 total marketplace interactions** and carrying an exceptional near-50% conversion velocity.
* **Senior Retention Collapse:** The conversion rate falls off a cliff in the "Old" demographic tier (55+), plummeting to a mere **25% conversion layout** (32 buyers vs. 96 non-buyers). Marketing budgets should be diverted away from senior outreach and focused entirely on middle-aged commuter profiles.

---

## Analytical Sandbox: Modeled Pivot Tables
The backend dataset structures and feeds five distinct data validation matrices:

### 1. Income Segmentation Layer (Average Income by Gender/Purchase Status)
*Shows that purchasing power tracks closely with the target acquisition variable.*
* **Female Buyers Average Income:** \$59,259
* **Male Buyers Average Income:** \$61,300

### 2. Vehicle Displacement Matrix (Average Car Ownership vs. Bike Status)
*Illustrates an inverse relationship between car reliance and bicycle conversions.*
* **Bike Buyers (Yes):** Average of **1.08 cars** (Female) | **1.18 cars** (Male)
* **Non-Buyers (No):** Average of **1.53 cars** (Female) | **1.72 cars** (Male)

### 3. Logistical Friction Grid (Commute Distance vs. Conversion Volatility)
*Isolates where the physical utility of a bicycle degrades for consumers.*
* **0–1 Miles:** 107 Non-Buyers | **98 Buyers**
* **1–2 Miles:** 50 Non-Buyers | **38 Buyers**
* **2–5 Miles:** 37 Non-Buyers | **44 Buyers** *(Peak Conversion Rate Percentage)*
* **5–10 Miles:** 63 Non-Buyers | **38 Buyers**
* **10+ Miles:** 50 Non-Buyers | **13 Buyers** *(Lowest Conversion Group)*

### 4. Vehicle vs. Wealth Scaling Matrix (Income Tiering per Household Car Volume)
*Tracks how household vehicle density maps to overall income brackets.*
* **0-Car Households:** \$46,802 Average Income

### 5. Generational Cohort Conversion Log (Age Range vs. Bike Conversions)
*Exposes a significant collapse in purchasing motivation as age parameters shift higher.*
* **Adolescent:** 16 No | **14 Yes**
* **Middle Age:** 195 No | **185 Yes** *(Primary Conversion Engine)*
* **Old:** 96 No | **32 Yes** *(Significant retention collapse)*

---
### Dashboard

<img width="743" height="309" alt="Dashboard" src="https://github.com/user-attachments/assets/e69e2463-70f1-446f-8564-bac230b84cfa" />

---

## How to Interface with the Dashboard
1. Clone this repository using your preferred command-line interface:
   ```bash
   git clone https://github.com
   ```
2. Navigate to the repository directory and open the primary workbook: `Bicycle_Retail_Performance.xlsx`.
3. Ensure **Data Connections** and external models are enabled to allow Power Pivot tables to parse correctly.
4. Utilize the **Region, Occupation, and Education Slicers** anchored on the visualization canvas to segment the demographic matrices in real time.
5. To inject fresh transactional logs, append entries directly to the background fact table and execute a global refresh shortcut: `Ctrl + Alt + F5`.

