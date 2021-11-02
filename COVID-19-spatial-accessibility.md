---
layout: page
title: Error and Uncertainty
---
## Introduction
In *Rapidly Measuring Spatial Accessibility of COVID-19 Healthcare Resources: A Case Study of Illinois, USA*, Kang et al. use the Enhanced Two-Step Floating Catchment Area (E2SFCA) method with parallel processing to assess the accessibility of ICU beds and ventilators to vulnerable populations -- defined as individuals of 50 years of age or older -- and COVID-19 patients in Illinois.
The goal of their study was to provide policymakers with regularly updated information concerning the spatial capability of key treatment resources to COVID-19 patients and vulnerable populations.
The authors found that access to ventilators and ICU beds was unevenly distributed throughout Illinois, and they published updated analyses daily in an online, interactive webpage called [WhereCovid](https://wherecovid19.cigi.illinois.edu/spatialAccess.html#7/40.000/-89.000/Dark_Mode-il_acc_i/370).

We seek to reproduce Kang et al.'s study for a few reasons.
First, the global pandemic is a pressing issue, and public policy decisions regarding the pandemic ought to be based upon reputable research.
Reproducing this study either confirms its findings, contributing to its validity as a basis for public policy, or overturns its findings, improving the basis of knowledge from which the government designs public policy.
There are also intellectual and pedagogical motives for conducting a reproduction of this study.
Intellectually, a reproduction confirms the validity of the researchers' spatial techniques; and pedagogically, conducting a reproduction allows students to see how geospatial studies are conducted and encourages students think critically about their reputability.

## Materials and Methods
The Kang et al. study draws on four datasets:
1. A **hospital dataset** provided by the Illinois Department of Health, which contains information about the number of ICU beds and ventilators at each hospital.
2. A **COVID-19 dataset** also provided by the Illinois Department of Health, with information regarding the number of COVID-19 cases in each Zip Code in the state.
3. A **residential dataset** from the 2018 American Community Survey 5 year table detailing the population and demographic composition of each tract in Illinois.
4. A **road network dataset** queried from OpenStreetMap using the Python package, OSMnx.

The provided research notebook includes only the data for the City of Chicago, because it is computationally burdensome for users to conduct this reproduction on the entire state of Illinois.
In order to deal with boundary issues (i.e. sometimes the fastest route to a hospital in Chicago uses streets outside the city), the road network provided for reproduction extends 15 miles past the boundaries of Chicago.
However, the population data provided by the authors contained information exclusively for the tracts within Chicago.
Residents of the Chicago suburbs can, and likely do, take advantage of the services provided by the hospitals physically within the city.
For this reason, we know that a more accurate analysis would incorporate population information of Chicago's suburbs.

In our class's reproduction of this analysis, we seek to remedy this issue by extending the pool of demographic information to include the tracts in all of the counties neighboring Cook county, which is the county where Chicago is located.
We did not address the geographic extent of the COVID-19 case data.

The computational resources available for the original study and our reproduction included a CyberGIS server and the programming language Python.
Specifically, the study was conducted in a Jupyter notebook using the virtual computing environment, CyberGISX, a cyberinfrastructure project which performs computations on a bank of supercomputers at the University of Illinois Urbana-Champaign.
Required Python packages include numpy, pandas, geopandas, networkx, OSMnx, shapely, matplotlib, tqdm, and multiprocessing.

***(((incorporate value of Open Source GIScience/complementing the original authors)))
(((comment code)))
Derrick's notes 6***

## Our Additions to the Code
Our additions to the code can be found in [/procedure/code/04-Class-Reanalysis.ipynp](https://github.com/Liam-W-Smith/RPr-Kang-2020/blob/main/procedure/code/04-Class-Reanalysis.ipynb) under the "Population and COVID-19 Cases Data by County" subheading and our new figures are under [/results/figures/reproduction](https://github.com/Liam-W-Smith/RPr-Kang-2020/tree/main/results/figures/reproduction) and are copied below:

```python
# Load data for tract geometry
tract_geom = gpd.read_file('./data/raw/public/ReanalysisClass/cb_2018_17_tract_500k.shp')
tract_geom.head()

# Load data for Census Demographics
tract_dem = pd.read_csv('./data/raw/public/ReanalysisClass/real_data_census_illinois.csv', sep=",", skiprows = [1, 1])
tract_dem.head()

# Extract the following columns: S0101_C01_001E, S0101_C01_012E, S0101_C01_013E, S0101_C01_014E, S0101_C01_015E, S0101_C01_016E, S0101_C01_017E, S0101_C01_018E, S0101_C01_019E
at_risk_csv = tract_dem[["GEO_ID", "NAME", "B01001_001E", "B01001_016E", "B01001_017E", "B01001_018E", "B01001_019E", "B01001_020E", "B01001_021E", "B01001_022E", "B01001_023E", "B01001_024E", "B01001_025E", "B01001_040E", "B01001_041E", "B01001_042E", "B01001_043E", "B01001_044E"]]
#Note: after a certain number of column names, atom becomes convinced that you're done with your code chunk. For this reason, I left out the last few columns in the code above, but they ought to be included when running the code.

# Find the number of columns in dataframe
len(at_risk_csv.columns)

# Sum all of the counts for individuals who are 50 years or older
at_risk_csv['OverFifty'] = at_risk_csv.iloc[:, 3:23].sum(axis = 1)

# create new pop column with a more useful name
at_risk_csv['TotalPop'] = at_risk_csv['B01001_001E']

# drop columns to clean the data set
at_risk_csv = at_risk_csv.drop(at_risk_csv.columns[2:23], axis =1)

# rename col to join
newnames = {"GEO_ID":"AFFGEOID"}
at_risk_csv = at_risk_csv.rename(columns = newnames)

# check projection
print(tract_geom.crs)

# transform CRS
tract_geom = tract_geom.to_crs(epsg=4326)

# check projection
print(tract_geom.crs)

# select tracts in Cook County and in counties adjacent to Cook County
tract_geom = tract_geom.loc[(tract_geom["COUNTYFP"] == '031')|
                            (tract_geom["COUNTYFP"] == '089')|
                            (tract_geom["COUNTYFP"] == '197')|
                            (tract_geom["COUNTYFP"] == '043')|
                            (tract_geom["COUNTYFP"] == '097')|
                            (tract_geom["COUNTYFP"] == '111')]

# perform an inner join based on AFFGEOID columns
atrisk_data = tract_geom.merge(at_risk_csv, how='inner', on='AFFGEOID')
```

## Results and Discussion


![Searching for Spatial Autocorrelation in my Erroneous Results](assets/Kang_OG_Reproduction/pop_icu_class.png)
![Searching for Spatial Autocorrelation in my Erroneous Results](assets/Kang_Class_Reproduction/pop_icu_class.png)

![Searching for Spatial Autocorrelation in my Erroneous Results](assets/Kang_OG_Reproduction/pop_vents_class.png)
![Searching for Spatial Autocorrelation in my Erroneous Results](assets/Kang_Class_Reproduction/pop_vents_class.png)


You can find my complete reproduction repository [here](https://github.com/Liam-W-Smith/RPr-Kang-2020).



## Conclusions
