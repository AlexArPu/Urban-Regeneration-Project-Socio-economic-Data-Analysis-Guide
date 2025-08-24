---
title: TXX Socio-economic Data Guide
---

**Step 1 — [Data Cleaning & Preparation]((https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/socieoconomic-data-analysis-guide-1.html))**

In the first step, you load the household survey and core R libraries, then “x-ray” the data with quick structure and summary checks (head/tail/str/summary/dim). You quantify missing values and verify unique IDs, drop fields you won’t analyze, and coerce key variables into analysis-ready formats (e.g., map neighbourhood safety from text to a 1–5 scale and convert Yes/No indicators to 0/1). When a second survey file arrives, you repeat the same cleaning, reconcile column names, standardize category labels, and merge both into a single canonical dataset (complete_survey). You finish by grouping related variables and exporting the cleaned file so Steps 2–4 can build consistent analysis, visuals, and dashboards on one “canonical source.”

The original dataset (```household_survey_1```) can be found [here](https://docs.google.com/spreadsheets/d/1g9wLeMfwMVtUlpOOwIr0WYIpGN_ZXL4u/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true), and the additional dataset that will be used in the merging (```household_survey_2```) can be found [here](https://docs.google.com/spreadsheets/d/1UtXni8_V5ANcd4fOSCxJaMXZZvvrXqnC/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true). The [Data Dictionary](https://docs.google.com/spreadsheets/d/1BGSSNHbM8WzLIjpf4B2ypOuXvmSyZsJC/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true) contains information about the variables present in both files.

- **Step 2 — EDA:** [HTML](https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/socioeconomic-data-analysis-guide-2.html)
- **Step 3 — Stratified Analysis:** [HTML](https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/socioeconomic-data-analysis-guide-3.html)
- **Step 4 — Dashboard:** [HTML](https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/Dashboard.html)

