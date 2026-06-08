# 🚀 Google Analytics E-Commerce Interactive Dashboard (Power BI)

A highly polished, interactive Power BI dashboard designed using a premium **Midnight Navy & Cyberpunk Neon** theme. This project analyzes user behavior, device categories, and geographic traffic distributions from Google Analytics e-commerce data under a strict **2-day rapid development timeline**.

---

## 📸 Dashboard Preview
<p align="center">
  <img src="https://github.com/La7hydar/Google-BigQuery-Analysis/blob/874c9a721263f4bd5986f32eff192c486c4a7fca/Google%20Analytics/Main%20Dashboard.png" alt="Power BI Dashboard Overview" width="100%">
</p>

<p align="center">
  <img src="[YOUR_IMAGE_URL_HERE](https://github.com/La7hydar/Google-BigQuery-Analysis/blob/874c9a721263f4bd5986f32eff192c486c4a7fca/Google%20Analytics/Dark%20Mode.png)" alt="Power BI Dashboard Dark Mode Overview" width="100%">
</p>

---

## 📌 Project Overview & Highlights
This dashboard transforms raw Google Analytics event logs into actionable business insights. To maximize visual appeal and storytelling, it skips standard generic templates in favor of bespoke, custom-engineered visual designs:
* **Custom Geometric Charts:** A unique 3-part Donut Chart featuring an invisible $1/4$ slice at the top-left to embed aesthetic metric titles and improve whitespace management.
* **True/False Gauge KPI:** A highly visual, calibrated Gauge Chart tracking `isMobile` traffic share, styled with Google's core dark-mode design language.
* **Ultra-Responsive Interactions:** Deep visual synchronization across all charts, cards, and custom multi-page navigation links.

---

## 📅 Timeline & Rapid Execution (Done in 2 Days)

This project was successfully engineered, cleaned, validated, and designed end-to-end within **48 hours**:
* **Day 1 (Data Engineering):** Data Ingestion, Schema Understanding, Missing Value Handling, and Core DAX Modeling.
* **Day 2 (UI/UX Design):** Interface Wireframing, Custom Geometric Visual Adjustments, Color Theming, and Interactivity QA.

---

## 📥 1. How the Data Was Sourced
The dataset originates from the official **Google Analytics Sample Dataset (BigQuery / Google Merchandise Store)**. 
* **Data Type:** Session and hit-level web analytics data.
* **Key Dimensions Extracted:** `deviceCategory`, `isMobile`, `country`, `date`.
* **Key Metrics Extracted:** `visitNumber`, `visitId` (used for unique traffic counts).

---

## 🧹 2. Data Cleaning & Preparation Process
To deliver clean, analytics-ready tables inside Power BI within the 2-day constraint, the following data engineering steps were performed:

### Data Ingestion & Transformation
1.  **Type Formatting:** Converted boolean strings into true system flags (e.g., transforming `isMobile` into absolute `TRUE/FALSE` format).
2.  **Granular Aggregation:** Filtered down huge event logs to focus on core visit markers (`visitNumber` and `visitId`) to optimize query loading times.
3.  **Top N Optimization:** Implemented visual-level filtering logic directly onto heavy dimensions like `country` to compute a dynamic **Top 7 Countries by Visit** layout, removing hundreds of low-impact rows from the main view canvas.

### Core DAX Modeling (The Logical Magic)
Rather than pulling raw columns directly into visual buckets, clean **DAX Measures** were written to bypass Power BI's default filtering limitations:
* **The 3-Piece Transparent Donut Tactic:** Calculated a `$25\%$` dummy slice proportional to total devices to simulate a physical open-gap geometry (`Donut_Sapi_Transparan = [Total_Semua_Device] * (1/3)`).
* **Safe Percentages:** Handled potential zero-division bugs elegantly when measuring mobile share metrics using `DIVIDE()`.

---

## 🌟 3. Key Advantages & Superpowers of This Dashboard
Why is this dashboard better than standard default reports?

1.  **Premium Dark Navy Palette (No Pure Black):** Built on an elegant `#0B0E14` (Midnight Navy) canvas with glowing accent colors (`#4D7CFF` and `#A370F7`). This avoids the high-contrast eye strain of default dark modes while maintaining a luxury tech feel.
2.  **Anti-Magnet Pixel-Perfect Layout:** Arranged entirely with custom manual boundaries by turning off native `Snap to Grid` limitations, ensuring layout symmetry.
3.  **Zero-Overhead Page Navigation:** Seamless page transitions bound directly to asset icons via local actions, removing the clutter of raw tabs.
4.  **Bulletproof Filter Synchronization:** Unified relational data tables ensuring that any user clicking a device slice instantly mirrors accurate visitor numbers into the main KPI Card.

---

## 🛠️ How to View the Project
1. Clone this repository or download the `.pbix` file.
2. Open the file using **Power BI Desktop**.
3. *Tip for local editing:* To test the navigation icons inside Power BI Desktop, hold the **`Ctrl` key and click** the image buttons!

---
*Developed with 💡 and 🚀 in just 2 Days.*
