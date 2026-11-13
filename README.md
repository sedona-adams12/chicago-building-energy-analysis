# How Efficient Is the Windy City? A Decade of Energy Use in Chicago's Big Buildings

An exploratory data analysis of Chicago's large-building energy consumption from 2014 to 2023, using R to investigate energy efficiency, greenhouse gas emissions, building age, and the effects of COVID-19.

## Project Overview

Buildings are a major source of energy consumption and greenhouse gas emissions in large cities. This project uses the City of Chicago's Energy Benchmarking dataset to explore how energy use has changed across Chicago's large buildings over a ten-year period.

The goal was to determine whether buildings are actually becoming more energy efficient, how building characteristics relate to energy consumption, and whether the COVID-19 pandemic had a lasting impact on different property types.

This project was completed as an individual data science project for DAT 301 at Arizona State University in Fall 2026.

## Research Questions

The analysis focuses on four main questions:

1. **Energy Efficiency Over Time:** Has the energy intensity of Chicago's large buildings decreased since 2014? Does the trend hold when comparing the same buildings across multiple years?
2. **Building Age:** Do older buildings use more energy per square foot than newer buildings?
3. **COVID-19 Impact:** How did the pandemic affect energy consumption across different property types, and did those changes continue after 2021?
4. **Greenhouse Gas Emissions:** Which property types contribute the most to building emissions, and how does the mix of natural gas and electricity affect those patterns?

The project also includes a geographic analysis of energy intensity across Chicago's community areas.

## Dataset

The project uses the **Chicago Energy Benchmarking** dataset from the City of Chicago Data Portal.

- **Source:** [City of Chicago Data Portal](https://data.cityofchicago.org/)
- **File:** `Chicago_Energy_Benchmarking_20261029.csv`
- **Time period:** 2014–2023
- **Unit of analysis:** One building or property in a given reporting year

Important variables include:

| Variable | Description |
|---|---|
| Data Year | Year the energy use was measured |
| Primary Property Type | Building category, such as office, multifamily, school, or hospital |
| Gross Floor Area | Building size in square feet |
| Site EUI | Energy use per square foot |
| Weather Normalized Site EUI | Energy use adjusted for weather conditions |
| Total GHG Emissions | Total greenhouse gas emissions |
| ENERGY STAR Score | Building performance score |
| Chicago Energy Rating | City energy rating |
| Community Area | Chicago neighborhood or community area |

## Tools and Technologies

- **R** – Data cleaning, analysis, and statistical exploration
- **RStudio** – Development environment
- **tidyverse** – Data manipulation and organization
- **dplyr** – Data transformation and summarization
- **ggplot2** – Data visualization
- **plotly** – Interactive visualizations and geographic mapping
- **knitr** – Tables and report generation
- **scales** – Formatting chart labels and values
- **R Markdown** – Reproducible analysis and HTML reporting

## Data Cleaning and Preparation

The original dataset contained missing values, inconsistent labels, and numeric values stored as text. Before conducting the analysis, I:

- Converted numeric columns using `parse_number()` to handle commas and formatting.
- Standardized reporting status labels that changed between years.
- Cleaned community area names to avoid duplicate categories caused by capitalization differences.
- Converted invalid or suspicious building construction years to missing values.
- Treated Chicago Energy Rating values of zero as missing.
- Excluded nonpositive and extreme Site EUI values above 500 from the efficiency analysis.
- Created additional variables for building age groups, building size categories, fuel mix, and COVID-related time periods.

These steps helped make the data more consistent and suitable for comparisons across years and property types.

## Analysis and Visualizations

The project includes several areas of exploratory data analysis:

- **Yearly energy trends:** Examines changes in median Site EUI and greenhouse gas intensity over time.
- **Building-level comparisons:** Follows buildings reporting in both 2016 and 2023 to examine whether efficiency improvements are visible within the same buildings.
- **Building age analysis:** Compares energy intensity across construction periods and property types.
- **COVID-19 analysis:** Compares energy use before, during, and after the pandemic.
- **Emissions analysis:** Investigates how emissions are distributed across property types and how fuel sources contribute.
- **Geographic analysis:** Uses an interactive Plotly map to explore building energy intensity across Chicago.
- **Performance validation:** Compares Site EUI with Chicago Energy Ratings and ENERGY STAR scores.

## Key Findings

Some of the main patterns identified in the analysis include:

- Chicago's large buildings generally became less energy intensive over the study period.
- Many buildings that reported in both 2016 and 2023 showed improvements in energy intensity.
- The decline in energy use was not consistent across every year, with a particularly noticeable change around 2020.
- Building age alone was not a strong predictor of energy intensity. Buildings constructed between 1946 and 1975 generally showed higher energy use per square foot.
- COVID-19 affected property types differently. Office buildings experienced a substantial decline in energy use that had not fully reversed by 2023.
- Emissions were concentrated in certain property types, particularly offices and hospitals.
- Chicago's community areas showed differences in median building energy intensity.

These findings also highlight the importance of considering reporting patterns, building occupancy, and changes in the electricity grid when interpreting energy trends.

## Project Files

| File | Description |
|---|---|
| `DAT301_Project1_FINAL.Rmd` | Main R Markdown analysis and source code |
| `DAT301_Project1_FINAL.html` | Rendered HTML analysis report |
| `DAT301_Project1_Slides.Rmd` | R Markdown source for the presentation |
| `DAT301_Project1_Slides.html` | Rendered HTML presentation |
| `Chicago_Energy_Benchmarking_20261029.csv` | Original dataset |

## How to Run the Project

1. Clone or download this repository.
2. Open `DAT301_Project1_FINAL.Rmd` in RStudio.
3. Make sure the CSV dataset is in the same working directory.
4. Install the required R packages if they are not already installed:

```r
install.packages(c(
  "tidyverse",
  "scales",
  "plotly",
  "knitr",
  "rmarkdown"
))
```

5. Knit the R Markdown file to generate the HTML report.

## Limitations and Future Work

The analysis has several limitations. Reporting requirements and participation changed over time, meaning the buildings represented in the dataset may not be consistent across every year. The pandemic also makes it difficult to distinguish genuine efficiency improvements from changes in building occupancy and usage.

Additional work could include building predictive models to identify the strongest drivers of energy intensity, incorporating electricity grid emissions data, and combining energy data with neighborhood demographic information to investigate potential environmental equity patterns.

---

**Author:** Sedona Adams  
**Course:** DAT 301 – Data Science  
**Institution:** Arizona State University  
**Year:** 2026
