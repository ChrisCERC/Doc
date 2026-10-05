# Web Map Service (WMS) 
## What is WMS? 
This provides an interface for requesting geo-registered Daily air quality map images for London, Essex and Surrey . 
A WMS request defines the geographic layer(s) and area of interest to be processed. The response to the request is one or more geo-registered map images (returned as JPEG, PNG, etc) that can be displayed in a browser application. 

Typical uses include:

-   Display maps 
-   Add layers to GIS software

## WMS URL

https://api.airtext.info/geoserver/london/wms

## Available Layers

| Layer | Description | 
| ---- | ---- | 
| NO2 | Nitrogen Dioxide (NO<sub>2</sub>) | 
| O3 | Ozone (O<sub>3</sub>) | 
| PM10 | Particulate Matter (PM<sub>10</sub>) | 
| PM25 | Particulate Matter (PM<sub>2.5</sub>) | 
| Total | Maximum DAQI levels over the four pollutants above | 

## Time dimension

The service is a WMS-T (Web Map Service with a Time dimension).  The time parameter is an ISO 8601 timestamp (YYYY-MM-DDT00:00:00Z).  The service provides maps for the current day and the next 2 days.  All of the other parameters in a WMS request are standard parameters.

## Coordinate systems

The data is stored in WGS84 (EPSG:3486) coordinate system, but can be requested in British National Grid (EPSG:27700) and others. 

## Consuming airTEXT WMS Layers

Our Web Map Service (WMS) layers can be integrated directly into web applications or desktop GIS applications.  

### Web Mapping Libraries (Leaflet / OpenLayers)

When displaying WMS layers using JavaScript mapping frameworks, the library handles map tiling, bounding boxes (bbox), spatial reference alignment (srs/crs), and image dimensions (width/height) dynamically as the user pans and zooms.

#### Leaflet Example:

const airtextWMS = L.tileLayer.wms('https://api.airtext.info/geoserver/london/wms', {
  layers: 'NO2',
  format: 'image/png',
  transparent: true,
  version: '1.3.0',
  time: '2026-10-07T00:00:00Z' 
}).addTo(map);

#### OpenLayers Example:

const wmsSource = new ol.source.TileWMS({
  url: 'https://api.airtext.info/geoserver/london/wms',
  params: {
    'LAYERS': 'NO2',
    'TILED': true,
    'TIME': '2026-10-07T00:00:00Z'
  },
  serverType: 'geoserver'
});

### Desktop GIS Software (QGIS)

To load airTEXT map layers into QGIS or other desktop GIS suites (such as ArcGIS):
1. In QGIS, navigate to Browser Panel $\rightarrow$ Right-click WMS/WMTS $\rightarrow$ New Connection...
2. Enter a Name (e.g., airTEXT WMS) and paste the connection URL:
   https://api.airtext.info/geoserver/london/wms
3. Click OK, expand the connection, and drag your desired pollutant layer (NO2, PM10, PM25, O3, Total) onto your map canvas.

Note on Client Parameter Automation: When using QGIS, OpenLayers, or Leaflet, you do not need to manually define parameters like bbox, width, height, or request=GetMap. The client software calculates these on the fly based on your active viewport and screen resolution.


