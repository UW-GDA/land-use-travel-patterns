# Analyzing Travel Demand Patterns and Land Use in Washington State

## Team Member
* Kaitlyn Ng
* Kittibhum Tasanasuwan
* Nutvara J

## Short Summary
This study will provide insight into travel demand patterns and land use in the Puget Sound region. Land uses will be determined through satellite imagery and computer vision, while travel demand patterns will be extracted from a household travel survey. Demographic analysis will also be conducted.

## Introductory/background information
Linking travel trajectories and land uses may provide insight into mobility patterns which improve a person's overall accessibility. ~~For example, individuals living in the suburbs may have fewer healthcare-related POIs near their home and thus have lower healthcare accessibility. However, as they commute downtown for work, we may observe spatiotemporal changes to healthcare POI density and subsequent increases in accessibility.~~

## Problem statement and reserach questions
We aim to analyze correlations between travel pattern origin-destination (OD) flows and land use. Land uses will be identified via satellite imagery. The following questions will be answered:
1) How do land uses affect trip generation? In other words, what land uses are correlated with a greater number of trips (e.g., do residential areas have more trips than industrial areas)?
2) What is the correlation between OD flows and demographics given similar land uses? For example, do low-income residential census tracts have a greater number of outflows compared to high-income residential census tracts?


## Datasets
* [Puget Sound Regional Council Household Travel Survey](https://www.psrc.org/our-work/household-travel-survey-program): Puget Sound Regional Council (PSRC), the metropolitan planning organization for King, Kitsap, Pierce, and Snohomish counties, conducts a household travel survey HTS) every 2-3 years to understand the travel patterns of its residents. This survey captures specific trips a person makes and records specific characteristics, such as travel time, origin location, destination location, and purpose of trip along with trip-maker characteristics. For this project, trip origins and destinations will be extracted to understand travel flows across the four-county region.
* [some satellite imagery here?]
* American Community Survey


## Tools/packages you’ll use
* Data wrangling: [numpy](https://numpy.org/doc/stable/user/index.html#user), [pandas](https://pandas.pydata.org/docs/user_guide/index.html#user-guide), [geopandas](https://geopandas.org/en/stable/docs.html)
* OD flows: [scikit-mobility](https://github.com/scikit-mobility/scikit-mobility) (see `FlowDataFrame`), [movingpandas](https://github.com/movingpandas/movingpandas) (see section on trajectory aggregation)
* Plotting: [matplotlib](https://matplotlib.org/stable/users/index.html)


## Methodology/approach
* <u>Computer Vision for land use classification</u>:
* <u>OD Flow Analysis</u>: The PSRC HTS will be processed to obtain census tract-level flows across the four-county region. Based on where each recorded trip beings and ends, the origins and destination census tracts can be obtained for all participants in the survey. An [origin-destination (OD) matrix](https://transportgeography.org/contents/methods/spatial-interactions-gravity-model/od-matrix-construction/) will be created from these flows, where the matrix is of shape $N \times N$ and $N$ is the number of census tracts in the Puget Sound region. The matrix rows represent origin census tracts, and the matrix columns represent destination census tracts.
* <u>Demographic Analysis</u>:

## Expected outcomes
* There will likely be areas where OD flows are clustered, such as in cities (Seattle, Tacoma, Everett). These areas will therefore be highly correlated with land uses such as residential (neighborhoods) and commercial (such as business districts). It is also expected that the OD matrix will be fairly sparse; for example, there may be a very high number of flows between Seattle and Bellevue, but very few flows between Seattle and census tracts in rural Eastern Washington. 
* Classification of land use via satellite imagery(Image Classification)
* Map for demographics, OD flow map


## References
TBC
