# Why Pipes Break, and How To Predict Breaks
10-17: **David Katzev** and **Clifford Chan**

- 10-17
- [Katzev/Chan video](https://bcourses.berkeley.edu/courses/1516536/files/folder/Module%204%20-%20Infrastructure%20maintenance%2C%20renewal%20and%20replacement?preview=84420282)
- Why Pipes Break and Predictive Modeling
- p.6: Primary Causes of Main Breaks: how to show JN for tension, compression, bending, corrosion, pressure?
## insert JN
:::{code-cell} python
install pandas as pd
:::
- p.8: chart of *cause* and *failure mode* by material: could pull data from failure db; fill chart with proportions;

````{div} full-width
```{note}
Add Jupyter notebook cells that could generate these figures
```
````

- p.9: Main Break history: JN : main breaks/ 100 miles / year: 3850 miles 16" and under; 1990 to 2021 by 4 materials; color coded; value of JN to show most recent breaks;

Testing

```{code-cell}
import pandas as pd
maindata = pd.Series([30,40,50,10, 50], name = "main")
dates = pd.date_range('1/1/2023', periods=5, freq="Y")
df = pd.DataFrame( {"Year": dates, 'Mainbreaks/100mi/year' : maindata})
print(df)
```

- p.10: Cast Iron pipe break rate: miles installed by year: 1877 to 1967; main breaks per mile by year overlaid; unclear if miles installed per year relates to breaks per mile; why huge drop in 1961 to zero in 1967 in breaks per mile?; huge peak in 1941; need relationship; breaks per mile by year installed?
- p.11: main breaks by month; great plot using distribution; JN show application of sorting by month

:::{note}
Here is a note!
:::

And here is a code block:

```
e = mc^2
```
- p.12: main breaks and precipitation: chart; main breaks each year; 1997 to 2016; overlay yearly precipitation; no clear relationship; maybe 2005; not 2008; maybe lagged; 2013; inches for east bay. should do for WH, EH; should do by pressure zone;
- p.13: Cast Iron Main Break Rate: chart; failure modes; break rate , breaks per 100 miles 1997 to 2017; bar chart; group by 6 failure modes; grouped again by pipe size; 4 inch, 6 inch, 8 inch; need further breakdown of pipe location in pressure zone by pipe size; possible new data showing what each pipe connects to; possible to list each pipe segment offsets, welds, joint types; longitudianal split or full circumference break; ML territory
- p.14: problem with pressure: chart: Thornton and Lambert, 2007: average reduction in new main breaks vs Average reduction in max pressure; scatter; reduction gets larger on vertical axis; redo chart; data from years, or locations, or water districts? or pressure zones? flip chart to show increase vertically....see original data
- p.15: Main break rate and pressure: break rate, breaks per mile by max pressure; opposite to p.14: need years, or age of pipe, or year installed;
- p.16: Measuring Pressure Transients: Las Vegas data; sample rate;  need original data; shows accuracy of measuring transient pressure peaks; Only see peaks at 128 samples/second; need discussion of instrumentation;
- p. 17 : Main Breaks and Pressure Zones: chart; Main Break rate by pressure zone identifier: colored by regulated pressure zone or non-regulated PZ; need discussion of instrumentation, method of regulation, regulation of peaks...
- p. 18: Pressure Regulators: charts show variance of psi measurements; seems to be for one PZ showing PSI by time; does this show sampling rate? same as Las Vegas
- p.19: Main Breaks by Day of Week: Chart: JN could show datetime multiple Pandas charts at different time resolutions. Shows 3000 breaks on Tuesday; don't know over what time period. Could show rates; breaks per 100 miles? 14,000 breaks; lower on weekend;
- p.20: Water Operations and Main Breaks: chart: Main breaks in one pressure zone by dates: Jan14 to Sep 16; monthly data; overlay of Woods PP Start/Stop; ??; from 0 to 105; breaks range from 1 to 7 per month in PZ; JN could show all PZ data;
- p.21: Butterfly Valve Flow Characteristics: chart; flow rate vs valve stem angle; sinuisoidal; 1 / 1 - e ^ degree?
- p.22: Water Operations and Main Breaks: map showing hot spots by reservoirs:
- p.23; Data Collection: Pressure and Acoustics: map showing locations; could show real-time readings; maybe 250 hydrants?
- p.25: Machine learning; describes wrangling data; adding geodata; ML;
- p.26: describe data import:
					1. Utility pipe asset data
					2. Utility Break History
					3. Data Wrangling
					4. Cleaned Pipe Asset Data
					5. Cleaned Break History Data
					6. ESRI Shape file. 23,876 pipe segments: 15% missing data;
					7. Break data: two Excel spreadsheets; + GIS file: ????
					8. Geocode Excel data?? Assign to pipes?
- p.27: Machine Learning:
					- shows attribute list of pipe;
					- attributes of breaks;
					- generate Pipe Asset with Likelihood of Failure scores: JN can do this with existing data;
					- Geo Variables from USGS soil properties: Resolution? 40+;
						- slope; elevation; proximity to transport; proximity to water;
						- population; buildings: can build more with SIM data
					- Utility variables; derived variables?; geo variables: Derived geo:
					- 1000 variables: ???
- p.28: Risk visualization:
					- map: show colored segments;  5 colored risks: F1 to F5;
- p.29: Compare to actual data; table showing forecasted breaks, break rate by 5 ranks; close with F5; F1 is 2702.9 miles; 1183 to 838; close
- p.30: Fracta demo: EBMUD-RUL-2022-08-16: link to web site;
					- https://www.fracta.io/home
					- Extend this
- p.31: Center for Smart Infrastructure:
