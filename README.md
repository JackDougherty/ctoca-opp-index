# ctoca-opp-index
Leaflet map of CT Open Communities Alliance, Opportunity Index 2014

## Demo
https://jackdougherty.github.io/ctoca-opp-index/index.html

## Data Sources and Methods

2014 Opportunity Index Levels, compiled by Scott Gaul for CTOCA.org, last updated February 9, 2015

https://sgaul.github.io/opportunity/

https://github.com/sgaul/opportunity/blob/gh-pages/opportunity-index.csv

Jack Dougherty made these changes when preparing Scott's CSV table (renamed opp-index-2014.csv) for conversion into GeoJSON map data, using Census 2010 tract boundaries:

1. Renamed each data header to include its abbreviated source & method info (example: "poverty" became "povertyZ-ACS0812" meaning the poverty Z-score for Am Community Survey 2008-2012 tract data)

2. Added town name (New Haven) that was missing for census tract 1428

3. Removed 4 rows of census tracts with no data
- 9901
- 9900
- 9901
- 9900

4. Removed 2 duplicate census tract rows (deleting the row with incomplete data) for two military bases (Groton sub base and Windsor Locks air base), then re-numbered these to match existing census tract geographies for these military areas
- Groton	9800	became Groton 9800.01
- Windsor Locks	9800	became  Windsor Locks 9800.02

5. Added a new column (level2014) based on numerical index (opp2014), using these equal-interval range cuts from Scott and Erin Boggs at CTOCA.org:

- Very low (166) = -3 to -0.4
- Low (165)      = -0.4 to 0.185
- Moderate (166) = 0.185 to 0.2297
- High (166)     = 0.2298 to 0.433
- Very High (166)= 0.433 to 1.6
- Total (829)

6. Downloaded CT Census 2010 tract map (from UConn MAGIC as shapefile and converted to GeoJSON format) and used http://mapshaper.org to join with the CSV table above, to create new geospatial file:
- opp-index-2014.GeoJSON

7. Important headers
- tract2010
- town
- index2014
- level2014

## Credits
- for map template, see credits and licenses in http://github.com/jackdougherty/leaflet-maps-with-google-sheets/
