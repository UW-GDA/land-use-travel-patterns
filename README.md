# Land Use, Transit Flows, and Demographics in King County

## Team Members
* Kaitlyn Ng
* Kittibhum Tasanasuwan
* Nutvara J

## Short Summary
This study will provide insight into the relationship between land use, demographics, and transit flows in King County. Land uses pattern will be visulized for analysis, while travel demand patterns will be extracted from a household travel survey. Demographic analysis will also be conducted.


## Introductory/background information
Transportation policy-makers often face the challenge of choosing between various transportation scenarios. To do this, they need to understand the flow of origin and destination (OD) of people. King County has diverse land use, including urban areas like Seattle, small towns like Issaquah, and rural areas like Snoqualmie. With different land uses, the population demographics also vary. Therefore, understanding how demographics and land use affect travel patterns is crucial for urban planning and transportation infrastructure development.


## Problem statement and reserach questions
This study aims to **analyze the correlations between travel patterns, demographics, and land use**. The study seeks to answer the following questions:

* What is the correlation between OD flows and demographics given similar land uses?
* How do land use and demographics affect the number of trips?
* Does the city provide a reasonable amount of transit to each census tract based on demographics and land use types?


## Datasets
* [Puget Sound Regional Council Household Travel Survey](https://www.psrc.org/our-work/household-travel-survey-program): Puget Sound Regional Council (PSRC), the metropolitan planning organization for King, Kitsap, Pierce, and Snohomish counties, conducts a household travel survey HTS) every 2-3 years to understand the travel patterns of its residents. This survey captures specific trips a person makes and records specific characteristics, such as travel time, origin location, destination location, and purpose of trip along with trip-maker characteristics. For this project, trip origins and destinations will be extracted to understand travel flows across the four-county region.
* [General Land Use Final Dataset](https://geo.wa.gov/datasets/a0ddbd4e0e2141b3841a6a42ff5aff46_0/about): This data set was developed as an information layer for the Washington State Department of Commerce. It is designed to be used as part of the Puget Sound Mapping Project to provide a generalized and standardized depiction of land uses and growth throughout the Puget Sound region. For this project, land use data will be visualized and pattern will be analysised. 
* [American Community Survey](https://www.census.gov/programs-surveys/acs): The American Community Survey (ACS), conducted by the U.S. Census Bureau, is a vital tool for gathering detailed characteristics data across communities in the United States. Released annually, the survey provides an information through various data tables covering social, economic, housing, and demographic aspects. In this project, this survey will be used to perform demographic analysis on selected characteristics within the King County areas. 

## Tools/packages
* Data wrangling: [numpy](https://numpy.org/doc/stable/user/index.html#user), [pandas](https://pandas.pydata.org/docs/user_guide/index.html#user-guide), [geopandas](https://geopandas.org/en/stable/docs.html)
* OD flows: [scikit-mobility](https://github.com/scikit-mobility/scikit-mobility) (see `FlowDataFrame`), 
* Plotting: [matplotlib](https://matplotlib.org/stable/users/index.html), [folium](https://python-visualization.github.io/folium/latest/)
* Anaylsis: [statsmodels](https://www.statsmodels.org/stable/index.html), [sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html)


## Methodology/approach
* <u>OD Flow Analysis</u>: The PSRC HTS was processed to obtain census tract-level flows across the four-county region. Based on where each recorded trip beings and ends, the origins and destination census tracts were obtained for all participants in the survey. An [origin-destination (OD) matrix](https://transportgeography.org/contents/methods/spatial-interactions-gravity-model/od-matrix-construction/) was created from these flows, where the matrix is of shape $N \times N$ and $N$ is the number of census tracts in the Puget Sound region. The matrix rows represent origin census tracts, and the matrix columns represent destination census tracts. OD flows are extracted for only transit trips.
* <u>Land Use Analysis</u>: The land uses are clipped using census tract geometries (since land use outlines do not alilgn with census tract boundaries). For each census tract, areas are calculated for each type of land use. The land use with the largest area proportion in the census tract becomes assigned as the "land use" for that census tract.
* <u>Demographic Analysis</u>: The analysis utilized common demographic variables. Utilizing the function outlined in the class exercise, demographic data of interest will be obtained using Federal Information Processing System (FIPS) codes. Correlations and visualizations of these demographics will be performed to obtain insights. 

Our methodology integrates the above OD flow patterns, land uses, and demographics. A correlation analysis is run to determine the relationship of variables with each other. The correlations are used to inform linear regression models to understand the relationships more deeply. The correlations and linear regressions inform variable selection for a geospatial mapping analysis.

## Key Insights



## Future Work
* Currently, we are assigning a single land use to each census tract. This is not always representative of a census tract's total land uses (there may be many different land uses in a single census tract). Improved methods for land use classification for a census tract would improve analysis. For example, data could be collected on the proportion of land uses within a single census tract, instead of assign a single land use value. Additionally, image classification performed on satellite imagery could also be a different method to classify land uses.
* Improved interactivity in the folium map could be incorporated to draw greater insights. Implementing tool tips, additional layers in the map, and adjusting layer controls could improve the exploratory power of the map.
* Additional built environmnet information could also be included, such as point of interest (POI) data. Understanding how different POIs (grocery stores, restaurants, hostpitals, etc.) generate transit trips would also reveal greater insights into why transit trips are conducted.


## References
