<h1 align="center">BIKE MAPPING</h1>

[![image](https://img.shields.io/twitter/follow/tyson_okoth?style=social)](https://twitter.com/tyson_okoth)
[![LinkedIn Badge](https://img.shields.io/badge/My-LinkedIn-blue)](https://www.linkedin.com/in/okoth-tyson-0968a9178/)
[![GitHub Badge](https://img.shields.io/github/followers/tokoth?style=social)](https://github.com/tokoth)

### About
A  project looking into exploring, processing, cleaning, and visualizing huge open datasets, by exploring NYC Bike Share Data

![Image](https://drive.google.com/uc?export=view&id=12RrVqvfGr7JIgHuept4swzHCWKOchnHF)
 
Huge credits to [Citi Bike System Data](https://ride.citibikenyc.com/system-data) New York City, for publishing there bike rides data, this is used as my datasource for the project.

### Objective

The main objective was to visualize geospatial data in Python.

The bike rides monthly data is a huge dataset. Depending on the season, the trip data files contain one record for each ride, with roughly two million records every month. It's a standard bike share system with fixed stations where a user takes up a bike from one dock and returns it to another using a key fob or a code. For each ride, the station and time the ride began and ended are recorded.

For this data visualization project a few assumptions were made so as to map only a sample of the data.

    1. Only data from the month of December was used for years 2018, 2019 & 2020.
    
    2. The data was cleaned and grouped by Station name and Station id.
    
    3. The resulting cleaned data indicated all the bike station where atleast one bike trip originated from the station
    and the number of trips recorder from the station.


### Data Processing

For this project the Python language and its packages were used in
data reading, observing, cleaning, processing and visualization of the data.

Packages used was; Pandas, Seaborn, Geopandas, Matplotlib, Contextily, and Folium.

The logical steps taken for this task is:
1. Download the [Citi Bike System Data](https://ride.citibikenyc.com/system-data), December data for years 2018, 2019 and 2020. 
2. Using Pandas to read the downloaded data, observe, analyse, group(by Station name and Station id), aggregate and write to an output csv file containing the cleaned data.
3. Using Seaborn to show and visaulize graphs and charts of the observed data.
4. Using GeoPandas to read in the cleaned data to a dataframe, convert it to a geodataframe. Create a backup copy of our data, assign a coordinate reference system(crs) to our geodataframe for our mapping.
5. Using Matplotlip to plot our geodataframes into static maps, using Contextily to add a basemap to our static maps and write to an output file of image format.
6. Using Folium to create an interactive map instance, add all the geodataframes for the years as a feature group to our map instance. Save and output an interactive map to a webpage.


### Results

Read in the downloaded data and display using Pandas.

  ```Python
 #Read and display the data
     data = pd.read_csv("201812-citibike-tripdata.csv")
```

We display the first 5 rows using head() method.
   
```Python
    data.head()
```

![Image](https://drive.google.com/uc?export=view&id=1doIVdoiJGHNn2Mas2wnC4-4wze8S8Nc1)
<h6 align="center">Output head, First 5 rows</h6>

We can get some information about the columns with the info() method.

```Python
    data.info()
```
The output shows the number of rows (just over a million) and the number of columns.

We can now prepare the data further using Pandas and explore some descriptive information from the data. 
Using Seaborn and matplotlib to plot and display graphs of busiest days, and top 10 busiest stations.

![Image](https://drive.google.com/uc?export=view&id=1UoY0_zKNhcNx0AqyGRMbXc0ch5A3kSf1)

![Image](https://drive.google.com/uc?export=view&id=18LqKspwDEi6eNE-PMNzQ4wj5fmgX025p)

After cleaning, grouping the data by (Station ID and Station Name) and aggregating we go ahead,and write to an output csv file.

We use GeoPandas to read in the cleaned data, convert it to a geodataframe. Assign a Coordinate reference system (CRS) to our geodataframe for our mapping

We display the first 5 rows using head() method, and check the CRS of our geodataframe using .crs method, which shows the EPSG code of the data.

```Python
    geodata.head()
```

![Image](https://drive.google.com/uc?export=view&id=1nhVr3_0OjZvORRTNsQnMDhIPZZRxXti5)

```Python
    print(geodata.crs)
```

![Image](https://drive.google.com/uc?export=view&id=1zwrgfgcDSvmcbYABTeQIqZVyHmiOKccz)
