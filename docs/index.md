<style>
.ocp-box{
  border:3px dotted #FF9900;   /* orange spotted line */
  border-radius:6px;
  padding:12px 16px;
  background:#fff7e6;          /* soft tint, optional */
  margin:1rem 0;
}
</style>

# TXX Socio-economic Data Guide

<div class="ocp-box"> 
**Description** This tool provides a step-by-step, R Markdown–based workflow to (1) clean, merge and document household-survey data, (2) explore and visualise it, (3) stratify results by key socio-economic dimensions, and (4) publish an interactive dashboard. It turns raw records into policy-ready indicators and graphics on poverty, access to services, rent burden, safety perception, education, commuting and more. 

**Participants** Developed by the project lead and municipal technical team (urban planning/economy, statistics/data/monitoring), with optional support from national statistics offices, NGOs and university partners. Intended users include local economic development practitioners, urban planners and policy makers who need a reproducible, code-based evidence pipeline.
</div>

**Step 1 — [Data Cleaning & Preparation](([https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/socieoconomic-data-analysis-guide-1.html](https://github.com/AlexArPu/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/blob/3baee80387142d4a2ae0625eff8796b49f1afcb6/docs/socieoconomic-data-analysis-guide-1.html)))**

In the first step, you load the household survey and core R libraries, then “x-ray” the data with quick structure and summary checks (head/tail/str/summary/dim). You quantify missing values and verify unique IDs, drop fields you won’t analyze, and coerce key variables into analysis-ready formats (e.g., map neighbourhood safety from text to a 1–5 scale and convert Yes/No indicators to 0/1). When a second survey file arrives, you repeat the same cleaning, reconcile column names, standardize category labels, and merge both into a single canonical dataset (complete_survey). You finish by grouping related variables and exporting the cleaned file so Steps 2–4 can build consistent analysis, visuals, and dashboards on one “canonical source.”

The original dataset (```household_survey_1```) can be found [here](https://docs.google.com/spreadsheets/d/1g9wLeMfwMVtUlpOOwIr0WYIpGN_ZXL4u/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true), and the additional dataset that will be used in the merging (```household_survey_2```) can be found [here](https://docs.google.com/spreadsheets/d/1UtXni8_V5ANcd4fOSCxJaMXZZvvrXqnC/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true). The [Data Dictionary](https://docs.google.com/spreadsheets/d/1BGSSNHbM8WzLIjpf4B2ypOuXvmSyZsJC/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true) contains information about the variables present in both files.

**Step 2 — [Exploratory Data Analysis]([https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/socioeconomic-data-analysis-guide-2.html](https://github.com/AlexArPu/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/blob/3baee80387142d4a2ae0625eff8796b49f1afcb6/docs/socioeconomic-data-analysis-guide-2.html))**

During the EDA, you load the [cleaned dataset](https://docs.google.com/spreadsheets/d/1mQD6g_noSQiHN-os1dnByc0CcJYl2JRm/edit?usp=drive_link&ouid=105664068897260112805&rtpof=true&sd=true) that was generated in the previous step plus the core libraries, profile the sample by district and nationality, and split variables into numeric vs. categorical to choose the right summaries and charts. For numeric fields you compute central tendency, dispersion and range measures, then inspect distributions with boxplots, histograms, and density plots; for categoricals you build frequency and relative-frequency tables, explicitly count default “Select” responses, and visualize with vertical/horizontal bars, stacked bars, and simple pies. You then examine relationships using Pearson (continuous–continuous), Spearman (ordinal), and point-biserial (continuous–binary) correlations, and illustrate Simpson’s paradox with an example to motivate stratification in the next step. Finally, you check subgroup sizes and run the appropriate hypothesis test to see whether apparent differences are statistically meaningful.

**Step 3 — [Stratified Analysis]([https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/socioeconomic-data-analysis-guide-3.html](https://github.com/AlexArPu/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/blob/3baee80387142d4a2ae0625eff8796b49f1afcb6/docs/socioeconomic-data-analysis-guide-3.html))** 

Now you segment the cleaned survey into meaningful population groups (by nationality, income, and marital status) to move beyond overall averages and reveal disparities. You then profile vulnerability (relative poverty and lack of basic services) by district, compare rent burden for all households and for low-income households, and visualize income composition and inequality (Gini) across places. Next, you examine education, age, and marital status patterns across groups, and contrast reported security incidents with perceived safety—both by district and demographics—to spot divergences. Finally, you approximate work location (inside/outside the study area) from commute mode and time, and compare employment accessibility across socio-economic groups and economic activities, presenting results with clear tables and intuitive charts.

**Step 4 — [Dashboard]([https://alexarpu.github.io/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/docs/Dashboard.html](https://github.com/AlexArPu/Urban-Regeneration-Project-Socio-economic-Data-Analysis-Guide/blob/3baee80387142d4a2ae0625eff8796b49f1afcb6/docs/Dashboard.html))**

Lastly, you package the analysis into a Shiny dashboard so non-technical users can explore it themselves. You load the cleaned dataset, add a simple rule-of-thumb to tag whether respondents work inside or outside the study area from commute mode and time, and set up the app skeleton: header, a sidebar filter (by Nationality or District), and three tabs—Summary, Charts, and Data Table. Each tab is wired to dynamic filtering so KPIs, visuals, and tables update instantly. The Summary tab shows headline indicators (neighbourhood liking, safety, income, age, education, rent burden, electricity access, marital status in-country, and share working inside the area); the Charts tab offers interactive plots for age, income, marital status, transport mode, education, utility access, and economic sectors; and the Data Table tab provides a downloadable, grouped summary for quick comparisons. Finally, you deploy to shinyapps.io with rsconnect so the dashboard is shareable online.

The fully operational dashbord can be explored by clicking [here](https://alarpu.shinyapps.io/se-dashboard/).
