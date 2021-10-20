### 675-Assignment-01 - Albuquerque Bikeway Connectvity to Parks and Open Space
#### Proposed workflow:
1. Symbolize trails to show existing and proposed bike trails - use theis to create figure ground
2. Merge parks and open space shapefiles into a single file or symbolize - we may have to make fields match for this to work
3. Filter dataset so only Albuquerque cartographic boundary is displayed
3. Verify that CRS on all datasets 
4. Commit all data to JSON

#### Datasets and Sources:
1. [Bike Paths ](http://coagisweb.cabq.gov/datadownload/biketrails.zip) - City of Albuquerque GIS
2. [Open Space ](http://coagisweb.cabq.gov/datadownload/openspace.zip) - City of Albuquerque GIS
3. [Parks ](http://coagisweb.cabq.gov/datadownload/parks.zip) - City of Albuquerque GIS
4. [Cartographic Boundary Files ](https://www2.census.gov/geo/tiger/GENZ2018/shp/cb_2018_us_ua10_500k.zip) - US Census Bureau

### Process workflow
1. Created **index.html** file using `echo > index.html`
2. Copied HTML/CSS boilerplate to index.html
3. Staged and commited changes to master branch using the following commands:
    1. `git add index.html`
    2. `git commit -m "add boilerplate to index.html"`
4. Verified results with `git status` command