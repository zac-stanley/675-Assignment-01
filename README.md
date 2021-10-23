### 675-Assignment-01 - Albuquerque Bikeway Connectvity to Parks and Open Space
#### Proposed workflow:
1. Symbolize trails by sruface type - use this to create figure ground
2. Set 'Name' field to title case in QGIS because these will be used for tooltips in web map and should look the same.
3. Filter dataset so only Albuquerque cartographic boundary is displayed
3. Verify that CRS on all datasets is 4326/WGS84
4. Convert all data to geoJSON

#### Datasets and Sources:
1. [Bike Paths ](http://coagisweb.cabq.gov/datadownload/biketrails.zip) - City of Albuquerque GIS
2. [Open Space ](http://coagisweb.cabq.gov/datadownload/openspace.zip) - City of Albuquerque GIS
3. [Parks ](http://coagisweb.cabq.gov/datadownload/parks.zip) - City of Albuquerque GIS
4. [Cartographic Boundary Files ](https://www2.census.gov/geo/tiger/GENZ2018/shp/cb_2018_us_ua10_500k.zip) - US Census Bureau

#### Create Web Map Boilperplate
1. Created **index.html** file using `echo > index.html`
2. Copied HTML/CSS boilerplate to index.html
3. Staged and commited changes to master branch using the following commands:
    1. `git add index.html`
    2. `git commit -m "add boilerplate to index.html"`
4. Verified results with `git status` command

#### Migrate data to the correct directory
1. Copy files from temp directory to C:\NewMapsPlus\Map675\675-Assignment-01\data using `copy` command
2. Change directory to data `cd C:\NewMapsPlus\Map675\675-Assignment-01\data`
3. Verify the contents `C:\NewMapsPlus\Map675\675-Assignment-01\data> dir`

#### Unzip shapefiles
1. Use windows extractor for this task
2. Delete *.zip files with `del *.zip` command

#### Explore the data with ogr2ogr
1. Navigate to subfolder in data directory
2. Use `ogrinfo -so biketrails.shp biketrails` to acquire the summary information on the shapefile.
3. The CRS for this dataset is not what we want for our web mapping purposes (NAD83(HARN) / New Mexico Central (ftUS)), thus we ned to project/transform it.
4. Use `ogr2ogr biketrails_4326.shp -t_srs "EPSG:4326" biketrails.shp` to convert the shapefile to WGS84 for web mapping
5. Verify projection change was successful `ogrinfo -so biketrails_4326.shp biketrails_4326`
5. Repeat these steps for remaining datasets

#### Convert shapefiles to GeoJSON with ogr2ogr
1. Navigate to the sub-directory holding biketrails.shp - *biketrails*
2. Run the `ogr2ogr -f "GeoJSON" ../bike-trails.json biketrails_4326.shp` command to convert the re-projected shapefile to a geoJSON and move it up one directory to *data/*
3. Repeat these steps for the remaining three shapefiles.

#### Create Leaflet Basemap
1. Add CSS, HTML and JavaScript to index.html to create a basic leaflet basemap

#### Create a Branch for Fleshing Out Web Map
1. Create new branch using `git checkout -b 'map-symbology'`
2. Load initial datasets into Leaflet using JQuery and the .when() method
3. Once loaded merge this branch back to master
