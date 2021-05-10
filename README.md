# uep239FinalProj
Public Repository for uep239 Geospatial Programming with Python final project

# Summary of Project
## General Structure of this Project:

1. Define a topic for a suitability or vulnerability analysis
    + Ex: What are the most suitable ZIP Code Tabulation Areas for certain groups to live in (college students, new families, etc...)
2. Choose at least four indicators to include in your analysis and base an overall index or score on
    + Pop density
    + Age/sex distribution
    + Edu attainment
    + Occupational distr
    + Avg household income
    + Housing Price/Rent cost
    + Accessibility to certain amenities
3. For each indicator, the analysis must:
    + Visualize spatial data that the indicator is based on
    + Summarize indicator values for each ZCTA in the study area
    + Produce a choropleth map visualizing indicators and produce ZCTA ranking based on indicator values from highest to lowest value
    + Convert indicator values into suitability or vulnerability index or score
    + visualize single indicator based score on choropleth map
4. Summarize single indicator based scores or indices into an overall weighted and unweighted score or index. Justify chosen weights or lack of weighting.
5. Visualize overall suitability or vulnerability index or score on a choropleth map and produce ZCTA ranking based on score or index from highest to lowest ranking


## More Specific Details

This github repository contains data and a python notebook for conducting a suitability analysis for the best places to live for 'bookworms'. The suitability analysis takes vector data to calculate the distance to subways, buses, and libraries, the amount of tree canopy cover, and the percent of population above 18 and in college in Boston zipcode areas. Each metric was rescored from 1-5, with high scores being good and low scores meaning bad for bookworms to live in. Low distance to transportation and libraries was considered good, as was high canopy cover, high percentage of population above 18, and total college population of zipcode areas. Distance and canopy data were converted from rasters to polygons using zonal statistics, after which all vector data was averaged in an unweighted score to give an average suitability score for bookworms in zipcode areas. In weighted analysis, distance to libraries was weighted by 30%, canopy by 10%, distance to public transport (trains and buses) 20%, and population measures were given 10% weights each (weighting justification is given in uep239_FinalProj_SchipperKees.ipynb). All data can be found in the 'Data' folder, with final suitability polygon data found in the 'Output' folder

# Instructions on how to run the project notebook

The project notebook is simple to run, and doesn't need to be modified beyond cloning the github repository onto your machine. The only step required for the notebook to run in full is for the user to clone the repository, install the used environment from the environment.yml file, and set their working directory to the top level of the repository (uep239FinalProj).

# Description of Data, sources, and preprocessing steps

This section will go over the various types of data used, their sources, and preprocessing steps. Each data source will be described in a list under the folder that it is contained in

1. ACS_Data
    + AgeACS.csv
        + Age and gender data from the American Community Survey (ACS) 2019 estimates
        + Preprocessing: was loaded into working notebook with four columns selected (`GEO_ID`, `NAME`, `S0101_C01_026E`, `S0101_C02_026E`). Last two columns are for population over 18, and percentage of population over 18
    + EduAttainmentACS.csv
        + Educational attainment data from ACS 2019 estimates
        + Preprocessing: identical to above, but the columns kept were `S1401_C03_010E`, `S1401_C04_010E`, which represent Population enrolled in public college or grad school, and percent in public college or grad school

# Packages Used + Details

# Acknowledgements and resources