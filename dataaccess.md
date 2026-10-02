# Data Access Guide 

## Introduction 

Welcome to the Data Access Guide. This guide explains the different ways you can access data from the system. It is intended for users with little or no technical background and provides an overview of each service, together with links to more detailed documentation. 

--- 
# Available Services 

The following data access methods are available: 
| Service | Purpose | Suitable for | 
|----------|----------|--------------|
 | REST API | Access data programmatically | Developers, integrations | 
 | WMS | View map layers | GIS users, mapping applications | 
 | WCS | Download raster data | GIS users, analysts | 
 --- 
 # REST API 
 ## What is the REST API? 
A REST API is a standard method for accessing data.  The Forecast API provides the same air quality data that is shown on the airTEXT website, in a format that enables users to integrate the data into their systems.

Typical uses include: 
- Integrating with other systems 
- Downloading data 
- Automating processes 

### API Endpoint 
``` https://london-airtext-forecasts-api-gateway-7x54d7qf.nw.gateway.dev ``` 
### Example Request
 ```https://london-airtext-forecasts-api-gateway-7x54d7qf.nw.gateway.dev/getforecast/pollutant?from=2026-07-17&numdays=1&zone=Southwark ``` 
### Example Response 
```json 
{
	"forecastdate":"17-07-2026 14:48",
	"timestamp":1784299724550.003,
	"zones":[
		{"forecasts":
			[
				{
					"NO2":2,
					"O3":3,
					"PM10":2,
					"PM2.5":2,
					"forecast_date":"2026-07-17",
					"pollution_version":202607171410,
					"total":3,
					"total_status":"LOW"
				}
			],
			"zone_id":29,
			"zone_name":"Southwark",
			"zone_type":1
		}
	]
} 
``` 

### Swagger Documentation 
The complete API documentation is available in Swagger. 
Link: https://api.airtext.info/API/

--- 
# Using Swagger 
Swagger provides an interactive interface for exploring and testing the API. 

## Trying an Endpoint 
1. Click **Authorize**. 
2. Enter your API key.
3. Select the getForecast endpoint. 
4. Click **Try it out**. 
5. Enter any required parameters, as described in the swagger document.
6. Click **Execute**. 
7. Review the response. 

--- 
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
| --- | --- | 
| NO2 | Nitrogen Dioxide (NO<sub>2</sub>) | 
| O3 | Ozone (O<sub>3</sub>) | 
| PM10 | Particulate Matter (PM<sub>10</sub>) | 
| PM25 | Particulate Matter (PM<sub>2.5</sub>) | 
| Total | Maximum DAQI levels over the four pollutants above | 


## Connecting to WMS 

TODO

--- 
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
| --- | --- | 
| NO2 | Nitrogen Dioxide (NO<sub>2</sub>) | 
| O3 | Ozone (O<sub>3</sub>) | 
| PM10 | Particulate Matter (PM<sub>10</sub>) | 
| PM25 | Particulate Matter (PM<sub>2.5</sub>) | 
| Total | Maximum DAQI levels over the four pollutants above | 

## Connecting to WCS 

TODO

--- 
# Data Update Schedule

The data is updated regularly.  Twice a day, a full data update is performed using the latest forecast data for three days.  The morning update provides data for the current day and the next two days.  The evening update provides data for the next three days.  The current day's data is also updated every 2 hours, taking into account the latest monitoring data.

--- 
# Further Help 
Links to: 
- Swagger 
- - Support email 
- - FAQs

# Other documents

-   Example files: e.g. A QGIS project file preconfigured with the WMS layers ?

---
# Data Access Quick Start Guide 
## Introduction 
This guide provides the information needed to quickly connect to the available data services. It is intended for developers, GIS users and system integrators who are familiar with web services. 
For less techincal explanations, see the **Data Access Guide**.

 --- 
  # Available Services 
 | Service | Purpose | Suitable for | 
|----------|----------|--------------|
 | REST API | Access data programmatically | Developers, integrations | 
 | WMS | View map layers | GIS users, mapping applications | 
 | WCS | Download raster data | GIS users, analysts | 
 --- 
# REST API 
## Base URL 
``` https://london-airtext-forecasts-api-gateway-7x54d7qf.nw.gateway.dev  ``` 
## Authentication 
API Key
Example:
 ``` todo ``` 
 
--- 
## Endpoints
Explain the /all, /pollutant, etc path parameters

## Query Parameters
List and provide examples for each parameter
## Error codes
List the various error codes and what they mean

--- 
# WMS 
## Service URL 
``` https://api.airtext.info/geoserver/london/wms ``` 

--- 
## Supported Versions 
* 1.3.0 
* 1.1.1 
--- 
## Available Layers

| Layer | Description | 
| --- | --- | 
| NO2 | Nitrogen Dioxide (NO<sub>2</sub>) | 
| O3 | Ozone (O<sub>3</sub>) | 
| PM10 | Particulate Matter (PM<sub>10</sub>) | 
| PM25 | Particulate Matter (PM<sub>2.5</sub>) | 
| Total | Maximum DAQI levels over the four pollutants above 
--- 
## Example GetCapabilities 
``` todo ``` 

--- 
## Example GetMap 
``` todo ``` 

--- 
# WCS 
## Service URL 
``` https://api.airtext.info/geoserver/london/wcs ``` 
--- 
## Supported Versions 
* 2.0.1 
--- 
## Available Coverages 
| Coverage| Description | 
| --- | --- | 
| NO2 | Nitrogen Dioxide (NO<sub>2</sub>) | 
| O3 | Ozone (O<sub>3</sub>) | 
| PM10 | Particulate Matter (PM<sub>10</sub>) | 
| PM25 | Particulate Matter (PM<sub>2.5</sub>) | 
| Total | Maximum DAQI levels over the four pollutants above | 

--- 
## Example GetCapabilities 
``` todo ``` 

--- 
## Example DescribeCoverage 
``` todo ``` 

--- 
## Example GetCoverage 
``` todo ``` 

--- 
# Coordinate Reference Systems Supported 
CRS: 
| EPSG | Description |
 |------|-------------| 
 | 27700 | British National Grid | 
 | 4326 | WGS84 | 
 --- 
