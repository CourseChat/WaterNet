# Water Demand Forecasting
- 9-12: Brad Ledesma: expand
- 09-12
- https://bcourses.berkeley.edu/courses/1516536/files/folder/Module%202%20-%20Water%20supply%20and%20natural%20resources?preview=84056926
- Water Demand Forecasting
- p.5: Methods of forecasting: per capita: chart: by city in Bay Area; city by gallons per capita use
:::{code-cell} python
## Download EBMUD historical water demand daily amounts by customer class
install pandas as pd
install url
:::
- p.6: land usde forecasting: 
- p.7: econometrics: chart function of variables, by year
- p.9: Base year and normalization: chart: Average daily water demand by year: 1970 to 2025: against population growth; gallons per capita per day; shows bands of drought years; 
- p10: base year and normalization: chart: Economic Index by year; 1975 to 2018; JN? : pull in Economic Cycles Research Institute data; show different indices?
- p.11: Driver Units: econometric analysis; JN  to pull in Oakland, Berkeley, BA Regional plans, forecasts; 
- p.12: US Census: JN pull in persons per square mile, other population; watch out for boundary definitions: polygons in Geopandas; use Association of Bay Area Governments regional data; JN pull in example data
- p.13: chart: water use by customer category: from EBMUD: JN to pull in metered consumption data? show customer classes: JN to show major users, ; SFR use for irrigation vs for HH; MultiFamily by other attributes, other data sources
- p.14: Account level:  table of business customer class code; water use by account; Time series 1975 to 2017: Parcel level : time series 2005 to 2017; JN to pull parcels?
- p.15: Sources of data: consumption:chart: SFR: model calibration, validation and volumetric verification: ??? ; how to do this from EBMUD data: used 2005-6 to build model; used drought, recession years to build model; used 2016 to 2018 to validate;
- p.16: Large customers: note that UC is not listed: 
- p.20: Hydraulic modeling: show how block hydraulic , meter data matches area forecasting; use PZ to model? use socioecoomic: JN? 
- p.21: non revenue: leak, meter loss; unbilled: how to estimate: see https://wuedata.water.ca.gov/awwa_plans;   how to asses leaks; JN? 
- p22: how to use recycled water, conservation in demand forecast: JN?
- ov/AWWA_plans