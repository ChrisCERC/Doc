# Welcome to the Data Access Guide

## Introduction 
This guide provides the information needed to quickly connect to the available airTEXT data services. It is intended for developers, GIS users and system integrators who are familiar with web services. 

## About airTEXT

airTEXT is a free service for the public providing air pollution alerts by email, text message, and voicemail and 3-day forecasts of air quality, pollen, UV and temperature across Greater London, Surrey and parts of Essex. airTEXT is an independent service, operated by Cambridge Environmental Research Consultants (CERC) Ltd in partnership with a consortium made up of representatives from all the member local authorities, the GLA, UK Health Security Agency and the Environment Agency. The airTEXT Consortium is chaired by Islington Council.

--- 
## Available Services 

The following data access methods are available: 

| Service | Purpose | Suitable for | Link |
| ------- | ------- | ------------ | ---- |
| REST API | Access data programmatically | Developers, integrations | [REST API](restapi.md) |
| WMS | View map layers | GIS users, mapping applications | [WMS Guide](wms.md) |
| WCS | Download raster data | GIS users, analysts | [WCS Guide](wcs.md) |

--- 
## Data Update Schedule

The data is updated regularly.  Twice a day, a full data update is performed using the latest forecast data for three days.  The morning update provides data for the current day and the next two days.  The evening update provides data for the next three days.  The current day's data is also updated every 2 hours, taking into account the latest monitoring data.
