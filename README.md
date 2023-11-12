# python-api-challenge

This project combines python requests, APIs and JSON traversals to examine the relationship between latitude and weather. The two sub-projects in this repository, [WeatherPy](WeatherPy) and [VacationPy](VacationPy) take 555 cities as a sample population, then provide the following analyses:

## [Part 1: WeatherPy](WeatherPy)

In this section, we use the jupyter notebook: [WeatherPy.ipynb](WeatherPy/WeatherPy.ipynb) to extact a random sample population of 555 cities in varying latitudes and longitudes. This data is stored in the [cities.csv](WeatherPy/output_data/cities.csv) file in the [output_data](WeatherPy/output_data) folder and used for the following analyses:

<ol>
    <li><a href="WeatherPy/output_data/ScatterPlots/LatvsTemp.png">Latitude vs. Maximum Temperature</a></li>
    <li>[Latitude vs. Humidity](WeatherPy/output_data/ScatterPlots/LatvsHumidity.png)</li>
    <li>[Latitude vs. Cloudiness](WeatherPy/output_data/ScatterPlots/LatvsCloudiness.png)</li>
    <li>[Latitude vs. Windspeed](WeatherPy/output_data/ScatterPlots/LatvsWindspeed.png)</li>
</ol>

We then examine the significance of these relationships in both the northern and southern hemispheres by filtering the dataframe by latitude and storing the separate datafiles under [southern_hemi_data.csv](WeatherPy/output_data/southern_hemi_data.csv) and [northern_hemi_data](WeatherPy/output_data/northern_hemi_data.csv)

Each hemisphere and relationship is then plotted with a linear regression to establish correlation significance:

These regressions can be found in the following files:

<ol>
    <li>[Northern Hemisphere Latitude vs. Temperature](WeatherPy/output_data/Regressions/NHemiCityvsTemp.png)</li>
    <li>[Southern Hemisphere Latitude vs. Temperature](WeatherPy/output_data/Regressions/SHemiCityvsTemp.png)</li>
    <li>[Northern Hemisphere Latitude vs. Humidity](WeatherPy/output_data/Regressions/NHemiCityvsHumid.png)</li>
    <li>[Southern Hemisphere Latitude vs. Humidity](WeatherPy/output_data/Regressions/SHemiCityvsHumid.png)</li>
    <li>[Northern Hemisphere Latitude vs. Cloudiness](WeatherPy/output_data/Regressions/NHemiCityvsCloudy.png)</li>
    <li>[Southern Hemisphere Latitude vs. Cloudiness](WeatherPy/output_data/Regressions/SHemiCityvsCloudy.png)</li>
    <li>[Northern Hemisphere Latitude vs. Windspeed](WeatherPy/output_data/Regressions/SHemiCityvsWindy.png)</li>
    <li>[Southern Hemisphere Latitude vs. Windspeed](WeatherPy/output_data/Regressions/SHemiCityvsWindy.png)</li>
</ol>

Based on these regressions, the following conclusions were found: (more extensive explanations can be found under each regression plot in the [WeatherPy Notebook](WeatherPy/WeatherPy.ipynb)):

<ul>
    <li> There is a correlation between latitude and temperature, and this relationship is more directly correlated in the nothern hemisphere than the southern hemisphere</li>
    <li> There is no statistically significant correlation between latitude and humidity in either hemisphere</li>
    <li>There is no statistically significant correlation between latitude and cloudiness in either hemisphere</li>
    <li>There is no statistically significant correlation between latitude and wind speed in either hemisphere</li>
<ul>
    
## [Part 2:[VacationPy]](VacationPy)

In this section, we use the jupyter notebook: [VacationPy.ipynb](VacationPy/VacationPy.ipynb) to examine the sample cities from the previous analysis as hypothetical vacation location options based on weather criteria.

First, the previous cities dataset is loaded and mapped using hvplot.points. The plot points are filtered by size based on the humidity of each city. The map is then downloaded as an html file and can be found in [map_plot](VacationPy/output_data/map_plot.html)

This dataset is then filtered based on the following criteria:

<ul>
    <li>Temperatures between 21C and 27C</li>
    <li>Wind Speeds of less than 4.5</li>
    <li>0% Cloudiness</li>
<ul>

The resulting dataframe is stored in [filteredcities.csv](VacationPy/output_data/filteredcities.csv). For each of these cities, we then use geoapify api to find the first hotel within 10000 meters of Lat/Long Coordinates. The names of these hotels are appended to a new dataframe which can be found in the [hotel_df](VacationPy/output_data/hotel_df.csv) file. 

These hotels are then mapped using hvplot.points and downloaded as an html file which can be found in [Hotel_plot](VacationPy/output_data/Hotel_plot.html)




