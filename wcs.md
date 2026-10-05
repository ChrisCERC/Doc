# Web Coverage Service (WCS) 
## What is WCS? 
WMS provides **pictures of maps**, WCS provides the **underlying data**.
Typical uses include:

-   Analysing the data 
-   Including the data in other processes, e.g. WPS.

### WCS URL 
``` https://api.airtext.info/geoserver/london/wcs ``` 

## Available Coverages

| Coverage| Description | 
| ---- | ---- | 
| NO2 | Nitrogen Dioxide (NO<sub>2</sub>) | 
| O3 | Ozone (O<sub>3</sub>) | 
| PM10 | Particulate Matter (PM<sub>10</sub>) | 
| PM25 | Particulate Matter (PM<sub>2.5</sub>) | 
| Total | Maximum DAQI levels over the four pollutants above | 

## Consuming airTEXT WCS Layers

Our Web Coverage Service (WCS) provides access to raw raster data (GeoTIFF files) rather than pre-rendered map images. This enables direct spatial analysis, value extraction, and processing in GIS software and custom scripts.

### Desktop GIS Software (QGIS / ArcGIS)

#### To load raw airTEXT coverage datasets into QGIS:

1. In QGIS, Layer $\rightarrow$ Add Layer $\rightarrow$ Add WCS Layer...
2. Enter a Name (e.g., airTEXT WCS) and paste the endpoint URL:https://api.airtext.info/geoserver/london/wcs
3. Click OK, expand the connection tree, and select your target coverage (e.g., NO2, PM10) and date.
4. QGIS will handle spatial trimming (subset/bbox) and projection mapping (crs) automatically as you query data.
