![FWT](FWT.png)
## Problem Description

Inflation is eroding the purchasing power of the everyday American. We hypothesize that median annual salaries are not increasing at the same rate as average living expenses. Analyzing US income and annual household expense data at the metropolitan area and state levels can allow us to identify trends, and understand the true extent of the gap. Additionally, we would like to see if the data supports the hypothesis that the recent mass exodus from larger metropolitan areas, to smaller cities on-the-rise, has caused spikes in rent prices. 

## Impact

Cost burden is defined as paying more than 30% of household income for housing including rent, mortgage, and other housing needs (https://www.census.gov/library/stories/2022/12/housing-costs-burden.html). It’s becoming increasingly more difficult for people to meet basic needs with the rise in living expenses and salaries not increasing proportionately to meet that demand. If the rise in living expenses continue to outpace wage increases, we will see many more citizens who cannot afford basic necessities. It may also exacerbate the exodus from larger to smaller metropolitan areas, leading to increased cost-of-living expenses in those areas, and the displacement of long-time residents. 

## Approach

 - Utilize curated data to understand the change in median income, rent, and consumer expenditures over the years of 2017 to 2021
 - Compare wages vs living expenses in a given area to measure affordability
 - Perform multiple linear regression analysis using statsmodels to determine the relationship between wages and independent variables like population
 
 ## Data Curation
 
 ### Data Sources
 
 The analysis was completed using the datasets listed below:

 - **U.S. Department of Housing and Urban Development Fair Market Rents (HUD FMR)**
 
    HUD’s Fair Market Rents (FMRs) estimates the 40th percentile of gross rents for standard quality rental units, ranging from a studio to a 4+ bedroom dwelling, within a metropolitan area. The calculation includes the cost of shelter plus all major utilities excluding telephone, cable television, and internet services. Data for all US states was collected in the form of csv files from https://www.huduser.gov/portal/datasets/fmr.html for the years 2017 - 2022.

 - **U.S. Census Bureau (USCB)**
 
    The U.S. Census Bureau produces estimates of the total resident population annually at the state, county, and city/town levels. City/town level data for all US states was collected from https://www.census.gov/data.html in the form of csv files for the years 2010 - 2021.

 - **U.S. Bureau of Labor Statistics - Consumer Price Index (BLS CPI)**
 
    The Consumer Price Index (CPI) measures the change in prices paid by urban consumers for goods and services. CPIs for all expense items excluding shelter for eleven regions relevant to the analysis were collected from https://www.bls.gov/cpi using the Public Data Application Programming Interface for the years 2017 - 2022 and a modified version of Randy Runtsch's Python code found here: https://towardsdatascience.com/acquire-and-visualize-us-inflation-data-with-the-bls-api-python-and-tableau-409a2dca1537.

 - **U.S. Bureau of Labor Statistics - Occupational Employment and Wage Statistics (BLS OES)**
 
    The Occupational Employment and Wage Statistics program produces and publishes annual wage estimates for ~830 occupations at a national, state, and metropolitan/nonmetropolitan area level. Data for all US states was collected in the form of Excel files from https://www.bls.gov/oes for the years 2017 - 2021.
   
## Project Tools

- JupyterLab
- Python
  - Dataprep
  - Pandas
  - Numpy
  - Seaborn
  - Plotly
  - Fuzzywuzzy
  - Statsmodels
 
## Analysis

The complete analysis consists of five parts linked below:

1. [Exploring Fair Market Rent Data](https://nbviewer.org/gist/robyndwhite/42c20ac0ec085538d5929ddd13ddb5f5)
2. [Exploring State and Metro Wage Data](https://nbviewer.org/gist/robyndwhite/600038c51830c8328ade16b9e882bf8d)
3. [Exploring Consumer Price Index Data](https://nbviewer.org/gist/robyndwhite/083dd940b5c14060bd5bd257283facda)
4. [Exploring Population Data](https://nbviewer.org/gist/robyndwhite/186d5fa00699e46c92f75a1b67e578b6)
5. [A Comparative Analysis](https://nbviewer.org/gist/robyndwhite/d0f9cfc7a1dcb90843d1c4672f24fa7c)

## Findings

1. Have the percentage increases in median wages kept up with the percentage increases in rent and CPI?

In short, it depends on the area. For some areas that we plotted, like Fort Lauderdale, FL or San Francisco, CA, we can see that the median wage increase is well below the increases of the FMRs and consumer price indexes. Other areas like Decatur, IL and Rochester, NY have seen greater increases in the median wage. A point to consider however, is that the Fair Market Rent data provided by HUD may differ from actual market rent data that can be found directly on property listings in some cities.

2. Is there a correlation between wages and other variables like rent, CPI, and population?

There appears to be a correlation between wages and the other variables with the strongest correlation is between wages and fair market rents.

3. Can we conclude that an increase in an area's population directly relates to an increase in living expenses based on our collected data?

Again, it depends largely on the area. In some areas, like those in the southern region, we see a higher correlation between the median FMR and population. In other areas, population seems to have little to no effect on living expenses.
