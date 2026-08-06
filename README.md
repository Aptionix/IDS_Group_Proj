# IDS Group Project

Group project repository for **Introduction to Data Science** (Team **K9**).

We perform an exploratory data analysis of how the six inhabited continents (all except Antarctica) are faring against two specific targets set out by the UN under Sustainable Development Goal 8:

1. Sustain per capita economic growth in accordance with national circumstances and, in particular, at least 7% gross domestic product growth per annum in the least developed countries.
2. By 2020, substantially reduce the proportion of youth not in employment, education or training.

The full report is in **`IDS Group Project Report.pdf`**.

## Team

| GitHub username  | Name              |
| ---------------- | ----------------- |
| charlied2107     | Charlie Dicker    |
| Aptionix         | Haoxuan Du        |
| AchintaKundra    | Achinta Kundra    |
| vasilikimichalia | Vasiliki Michalia |
| jsmntrbch        | Jasmine Trabucchi |

## Repository structure

The analysis is split into three R Markdown files, each compiled to a matching PDF:

| File                           | Purpose                                                      |
| ------------------------------ | ------------------------------------------------------------ |
| `IDS-setting-up.Rmd`           | Data import and cleaning. Merges the raw datasets, flags LDC countries, computes GDP / growth rates, and exports the cleaned data to `Exported_data/`. |
| `IDS-Task-1.Rmd`               | Target 1 analysis: continental GDP levels and growth (indexed to 100 in 2015), weighted vs. average growth, top-2 GDP driver countries per continent, and LDC growth against the 7% benchmark. |
| `IDS-Task-2.Rmd`               | Target 2 analysis: NEET trends by continent with regression slopes and significance tests, and Spearman/Pearson correlations of NEET against tertiary school enrollment, youth unemployment, and GDP per capita. |
| `IDS Group Project Report.pdf` | The final written report.                                    |
| `data_sets/`                   | Raw input CSVs (see data sources below).                     |
| `Exported_data/`               | Cleaned CSVs produced by `IDS-setting-up.Rmd` (`gdp_per_capita_cleaned.csv`, `youth_neet_cleaned.csv`). |

## Data sources

Provided datasets:

- Continents classification
- GDP per capita constant 2017 USD$
- Share of youth not in education, employment or training (NEET)

Additional datasets added by the team:

- Population, total — [World Bank](https://data.worldbank.org/indicator/SP.POP.TOTL)
- Unemployment, youth total (% of labour force ages 15–24, ILO estimate) — [World Bank](https://data.worldbank.org/indicator/SL.UEM.1524.ZS)
- School enrollment, tertiary (% gross) — [World Bank](https://data.worldbank.org/indicator/SE.TER.ENRR)

### Note on the Target 2 education data

Originally, education *attainment* data was used to analyse the correlation between education and NEET (changed in [PR #30](https://github.com/Aptionix/IDS_Group_Proj/pull/30)). We switched to the **tertiary school enrollment rate**, since it is calculated as the population in tertiary education divided by the population of official tertiary-education age (roughly 18–22), which covers a much larger share of the youth population (15–24) and therefore better reflects the education side of NEET.