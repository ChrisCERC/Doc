# GeoServer WMS Layer API

**Base URL:** `https://api.airtext.info`  

---

### ![GET](https://img.shields.io/badge/GET-2ea44f?style=flat-square) /geoserver/london/wms

Provides map images showing airTEXT forecast maps styled by DAQI band.

Provides URLs that can be used to view map layers.<br /><br />
**Note for GIS Software & Libraries:**<br />
When adding this WMS service to desktop GIS applications (such as QGIS or ArcGIS) or web mapping libraries (like OpenLayers or Leaflet), bounding box (`bbox`), image dimensions (`width`, `height`), and spatial reference (`srs`/`crs`) parameters are typically calculated and managed automatically by the client software as you pan and zoom.<br /><br />

#### Parameters

| Name | Required | Description |
|------|----------|-------------|
| service  <br /> `string`  | &#10003; | Must be WMS |
| version  <br /> `string` | &#10003; | WMS version <br /> `Available values: 1.3.0, 1.1.0` |
| request  <br /> `string` | &#10003; | Request for map image |
| layers  <br /> `string` | &#10003; | Pollutant layers <br /> `Available values: NO2, O3, PM10, PM25, Total` |
| time  <br /> `ISO 8601 timestamp` |  | ISO 8601 timestamp (YYYY-MM-DDT00:00:00Z) <br /> `Example: 2026-12-25T00:00:00.000Z` |
| format  <br /> `string` | &#10003; | Image format <br /> `Available values: image/png, image/jpeg` |
| srs  <br /> `string` | &#10003; | Coordinate system in WGS84, British National Grid or Google <br /> `Available values: EPSG:4326, EPSG:27700, EPSG:900913` | 
| bbox  <br /> `string` | &#10003; | Bounding box in map coordinates <br /> `Example: 51.069,-0.853,51.721,0.337` |
| width  <br /> `integer` | &#10003; | Width of the output image (pixels) |
| height  <br /> `integer` | &#10003; | Height of the output image (pixels) |

#### Example cURL Command

```bash
curl -G "https://api.airtext.info/geoserver/london/wms" \
    --data-urlencode "service=WMS" \
    --data-urlencode "version=1.3.0" \
    --data-urlencode "request=GetMap" \
    --data-urlencode "layers=NO2" \
    --data-urlencode "time=2026-12-25T00:00:00.000Z" \
    --data-urlencode "format=image/png" \
    --data-urlencode "srs=EPSG:4326" \
    --data-urlencode "bbox=51.069,-0.853,51.721,0.337" \
    --data-urlencode "width=600" \
    --data-urlencode "height=400" \
    -o no2.png
```

#### Responses

| Status | Description |
|--------|-------------|
| `200` | Map image rendered successfully |
| `400` | Bad Request |

---


---

