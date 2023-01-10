---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.4
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# Water Demand Forecasting

-   9-12: **Brad Ledesma**: expand
-   09-12
-   https://bcourses.berkeley.edu/courses/1516536/files/folder/Module%202%20-%20Water%20supply%20and%20natural%20resources?preview=84056926
-   Water Demand Forecasting
-   p.5: Methods of forecasting: per capita: chart: by city in Bay Area; city by gallons per capita use

```{code-cell} python
print("do math", 33 + 66)
```

-   p.6: land usde forecasting:
-   p.7: econometrics: chart function of variables, by year
-   p.9: Base year and normalization: chart: Average daily water demand by year: 1970 to 2025: against population growth; gallons per capita per day; shows bands of drought years;
-   p10: base year and normalization: chart: Economic Index by year; 1975 to 2018; JN? : pull in Economic Cycles Research Institute data; show different indices?
-   p.11: Driver Units: econometric analysis; JN to pull in Oakland, Berkeley, BA Regional plans, forecasts;
-   p.12: US Census: JN pull in persons per square mile, other population; watch out for boundary definitions: polygons in Geopandas; use Association of Bay Area Governments regional data; JN pull in example data
-   p.13: chart: water use by customer category: from EBMUD: JN to pull in metered consumption data? show customer classes: JN to show major users, ; SFR use for irrigation vs for HH; MultiFamily by other attributes, other data sources
-   p.14: Account level: table of business customer class code; water use by account; Time series 1975 to 2017: Parcel level : time series 2005 to 2017; JN to pull parcels?
-   p.15: Sources of data: consumption:chart: SFR: model calibration, validation and volumetric verification: ??? ; how to do this from EBMUD data: used 2005-6 to build model; used drought, recession years to build model; used 2016 to 2018 to validate;
-   p.16: Large customers: note that UC is not listed:
-   p.20: Hydraulic modeling: show how block hydraulic , meter data matches area forecasting; use PZ to model? use socioecoomic: JN?
-   p.21: non revenue: leak, meter loss; unbilled: how to estimate: see https://wuedata.water.ca.gov/awwa_plans; how to asses leaks; JN?
-   p22: how to use recycled water, conservation in demand forecast: JN?
-   ov/AWWA_plans
-   How many JN?
-   JN.1: small hydraulic block: get 41 meter readings over a year; link to what water passed through which pipes to get there; detail the 6-inch pipe, the 24-inch pipe; what pressure zone; what reservoir feeds;
-   build up into a pressure zone model; aggregate into 21 demand model regions; Problem: census tract boundaries do not coincide with model region boundaries; need to interpolate data on population; income;
-   JN.2: Demand Model Region; a SQL formula for each one to pull data? Use each customer ID, pull into hydraulic model, pull into region; model all these as separate DATAFRAME;
    -   build from smallest behavioral unit; do homework with total demand pulled from subunits; use 21;
-   JN: 21 Region id; in each, allocate 400,000 /21; 20,000; assign to sector; 50% to SFR; MFR: 19%; start with 400000; assign breakdown by category; One column for category or sector. why called “land use”? because land use determes water use?
    -   in each region, assign a population; get demographic profile of each; 1
    -   import customer data; for each, have parcel, census block, census tract, system unique id; meter id; sector or category; monthy usage, monthly bill; regulation regime; internal-attached-detached; year built; redevelopment; large customer;
    -   separate data; temp, rainfall, wind, fire, pandemic, transport miles/day; births; deaths; working; days not at home; land area or parcel use; square footage;
-   Chart: Methods of forecasting: per capita based
    -   x: gallons per capita per day
    -   2020 - 2021 BAWSCA Annual Survey: gallons per capita; 27 cities or WD
    -   Daly City: 53.1; E Palo Alto; 59.1; Hayward: 90.7; Mountain View: 108.1; San Jose: 110.8; EBMUD: 112; Stanford: 175; Hillsborough: 225; Purissima Hills WD: 278.2
    -   Build this from remote data from BAWSCA: open?
-   Land use forecast
-   Econometrics
    -   Create a functional realtionship; regression based estimators? Water Use = f( price, Income, Weather, Meter Data, Housing Unit data, Economy, Climate, Water rates, Density)
    -   Model use per unit; per dwelling unit; per acres of park or irrigation; per square ft of building; or others
    -   Chart : GPD/Unit vs time;
    -   Normalization means removing effects of economy or climate
-   Chart: 1970 - 2025: gallons per capita per day; gpcd: THIS IS CHART
    -   Total water demand:
    -   population:
        -   1970: 1,055000; 2020: 1,420,000;
        -   gpcd : water: 1970: 208; 1976: 128; 1987: 190; 1994: 156; 2020: 112
            -Drought years: 1976-78;1987-94; 2007-10;2014-16;2021-22
-   Chart: Economic index: Economic Cycles Research Institute: ???
    -   1975 to 2018: Economic index, between -0.1 and +0.12
-   Sources of Data:
    -   Oakland Downtown specific plan;
    -   Regional plans: meet w planners
    -   US Census: watch out for boundaries: persons per square mile by census tract
        -   GET info on changing tract boundaries: see if geopandas has data
    -   ABAG data: find staff names, on-line data sources
-   Chart: Customer classes, categories; different patterns of use; SFR: 50%, Institutional:4%; Irrigation: 8%; Petroleum: 7%; Industrial: 5%; Commercial:7%; MFR: 19%
    -   Find ways to link data to other sources: get list of other sources; oil data? institutional? UC: irrigation? MFR: rentals;
    -   Sources of Data: Account level: time series 1975 to 2017; why stopped? ; note variation in account numbers;
        -   water use per account missing dwelling units and square footage
        -   erroneous dwelling units due to illegals;
-   Sources: Parcel Level: Time series: 2005 to 2017: why stop?
    -   Dwelling units; parcel areas; dweilling square foot? or parcel square foot?
        -   Detailed demand allocation? along transport corridors; why?
-   Model calibration: Validation; volumetric validation; do have volume data, can use for validation
    - chart: 2005-2006: normal : validation
    - 2007-2009: drought and recession
    - 2010- 2013: recovery
    - 2014-2015: drought
    - 2016-2018: volumetric validation
    - graph: calibration 2007-2018: show observed, predicted
    - graph: validation: show Jan2005 to Oct 2006: validation unclear what this means; maybe normal year;
-   Sources: large customers:
    - Oakland Airport; C&H; Phillips 66; Chevron; Diablo Country Club; Coca Cola; Gatoraid; Cal;
    - high: 4.0 MGD; 1.3 MGD; 0.2 MGD;
-   Need graphic like forecasting challenges: Demand Categories and Areas
    - Customer
    - Parcels
    - Census Blocks
    - Census Tract
    - System wide useage data;
-   21 Demand Model Regions: 345 Census tracts; hundreds of models, 1000’s of results!
    -   Model Sectors:
        -   Single Family: 1: Housing Units
        -   Multiple Family: 3: Housing Units: why 3? big, medium, small? when built?
        -   Commercial: 2: Building area by 1000 square feet; retail, auto?
        -   Industrial: 1: building area; why not industrial code?
        -   Institutional;1; building area; why not edu, airport
        -   landscape irrigation; 1; parcel Area : acres; golf ? park?
-   Show map with meters indicated: Hydraulic Modeling
    - shows a main going around a 24-inch and joining a 6 inch
    - allocate into hydraulic model????
    - relate meter data and demand area forecast: how? is goal to predict how many more big pipes will be needed for expanding residential growth? or big new factory?
-   Non-revenue; leaks, theft, breaks; model
    - https://wuedata.water.ca.gov/awwa_plans
    -   Incorporate Water Conservation Strategic Plan 2021
    -   Updated Recycled Water Master Plan feb 2019
