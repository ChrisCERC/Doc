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
| `service` | &#10003; | Must be WMS |
| `version`  <br /> `string` | &#10003; | WMS version <br /> `Available values: 1.3.0, 1.1.0` |
| `request` | &#10003; | Request for map image |
| `layers` | &#10003; | Pollutant layers |
| `time` |  | ISO 8601 timestamp (YYYY-MM-DDT00:00:00Z) |
| `format` | &#10003; | Image format |
| `srs` | &#10003; | Coordinate system in WGS84, British National Grid or Google |
| `bbox` | &#10003; | Bounding box in map coordinates |
| `width` | &#10003; | Width of the output image (pixels) |
| `height` | &#10003; | Height of the output image (pixels) |

#### Responses

| Status | Description |
|--------|-------------|
| `200` | Map image rendered successfully |

---


---

