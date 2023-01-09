---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---


# Infrastructure Investments Overview
10-03: **Jimi Yoloye**
- 10-03
- Infrastructure investments overview
## EBMUD Distribution System: 4,600 miles

![Distribution System](../Images/Distribution_System.png)

- [Link to Lecture PDF](https://bcourses.berkeley.edu/courses/1516536/files/folder/Module%204%20-%20Infrastructure%20maintenance%2C%20renewal%20and%20replacement?preview=84282682)
- Page 15: Miles of pipe replaced; Total Main breaks reported; 1997- 2024

```{code-cell} ipython3
#import pandas as pd
# Comment: draw from EBMUD live data: use SQL query against main pipeline database
milesTotalPipe = 4200
milesScheduledRebuildYear = 30
yearsBeforeSystemRebuild = milesTotalPipe / milesScheduledRebuildYear 
print("Years before EBMUD system will be rebuilt ", yearsBeforeSystemRebuild)
```
- need access to machine learning model for graphical version

- Page 16: Main Breaks per month: 2020 line; historical bands
- Page 22: Cash flow by FY; FY 2022 - 2026
- Page 23: Cash flow by project: FY 2022 - 2026
- Page 24: Cash flow: for projects
- Page 25: Budget by Asset class: FY 2022 - 2026: pie chart
- Page 26: Cash flow by asset class: bar chart
- Page 27: Timeline 2020- 2030:
```{code-cell} ipython3
3 * 9
```
