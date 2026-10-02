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
Link: [Swagger document](https://api.airtext.info/API/)

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
