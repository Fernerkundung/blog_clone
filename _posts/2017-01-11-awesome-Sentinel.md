---
published: true
layout: post
title: Awesome Sentinel
---
The [Copernicus Sentinel satellites](http://www.esa.int/Our_Activities/Observing_the_Earth/Copernicus/Overview4) are an amazing opportunity for people all over the world to explore unprecedented amounts of remote sensing data under a free and open license. The [collaborative nature](http://www.esa.int/Our_Activities/Observing_the_Earth/Copernicus/Sentinel_Collaborative_Ground_Segment) of the Copernicus programme means that there are multiple ways to get access to Sentinel satellite data and the open license allows anyone to host mirrors of the data. The definitive data access portal for Sentinel data is the [**Copernicus Sentinels Scientific Datahub**](https://scihub.copernicus.eu/) aka. scihub. It contains all Sentinel-1, -2 and -3 data since their respective launches and offers a [graphical search interface](https://scihub.copernicus.eu/dhus) as well as an [API](https://scihub.copernicus.eu/twiki/do/view/SciHubWebPortal/APIHubDescription). It is based on the open-source [data hub software](http://sentineldatahub.github.io/DataHubSystem/), which is also employed by most national mirrors. There are however a wide number of mirrors and tools to get the data and process it. **This post is a curated list of awesome tools, tutorials and APIs related to data from the Copernicus Sentinel Satellites.**

## Data Access

### Data Hubs and National Mirrors
Official datahubs and mirrors by the Copernicus partners and [Collaborative Ground Segment members](https://sentinels.copernicus.eu/web/sentinel/missions/collaborative/national-points-of-contact).

- [**Copernicus Sentinels Scientific Datahub (SciHub)**](https://scihub.copernicus.eu/)
- [**Australia National Mirror**](http://www.copernicus.gov.au/)
- [**Austria National Mirror**](https://data.sentinel.zamg.ac.at/)
- [**Finnish National Mirror**](https://finhub.nsdc.fmi.fi/)
- [**French National Mirror (PEPS)**](https://peps.cnes.fr/rocket/)
- [**German National Mirror (CODE-DE)**](https://code-de.org/)
- [**Greek National Mirror**](https://sentinels.space.noa.gr/)
- [**Italian National Mirror**](http://collaborative.mt.asi.it/)
- [**UK National Mirror (SEDAS)**](http://sedas.satapps.org/)

### Partial Mirrors
Innitiatives to integrate specific Sentinel data into existing search and discovery platforms.

- [**Alaska Satellite Facility (Sentinel-1)**](https://www.asf.alaska.edu/sentinel/)
- [**Centre for Environmental Data Analysis - CEDA (Sentinel-1, -2)**](http://catalogue.ceda.ac.uk/search/?search_term=sentinel&return_obj=ob&search_obj=ob)
- [**USGS EarthExplorer (Sentinel-2)**](https://earthexplorer.usgs.gov/)

### Cloud providers
Providers that host Copernicus Sentinel data and allow you to bring your own code to process it.

- [**Amazon Web Services (Sentinel-2)**](http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/)
  - public S3 bucket, Sentinel-2 only, hosted in region eu-central-1 (Frankfurt)
- [**Google (Sentinel-2)**](https://console.cloud.google.com/storage/browser/gcp-public-data-sentinel-2/?pli=1)
  - public Google Storage bucket, `.SAFE` format, EU region
  
## Tools
Specific to Copernicus Sentinel data discovery, download and processing.

### search & download
- [**`sentinelsat`**](https://github.com/ibamacsr/sentinelsat)
  - search and download from any Datahub. Comes with an intuitive command line and a flexible Python API.
- [**`Sentinel-download`**](https://github.com/olivierhagolle/Sentinel-download)
  - download Sentinel-2 data from Copernicus SciHub. Supports download of sub-tiles in the old product format (PDS <14).
- [**`peps_download`**](https://github.com/olivierhagolle/peps_download)
  -  download data from the French National Mirror (PEPS).
- [**`Sentinel2ProductIngestor`**](https://github.com/sinergise/Sentinel2ProductIngestor)
  - ingest Sentinel-2 data from SciHub into S3. Used by [Sinergise](https://github.com/sinergise) to populate the [AWS Sentinel-2 mirror](http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/)
- [**`sat-download`**](https://github.com/sat-utils/sat-download)
  - download Sentinel-2 data from AWS
- [**`sat-api`**](https://github.com/sat-utils/sat-api)
  - query Sentinel-2 data on AWS using APIGateWay
  - deployed by Development Seed at [https://api.developmentseed.org/satellites](https://api.developmentseed.org/satellites)
  
### viewers & browsers
- [**AWS/Sinergise "Sentinel Image Browser"**](http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/browser.html)
  - search Sentinel-2 data available on Amazon Webservices
- [**RemotePixel "Satellite Search"**](https://remotepixel.ca/projects/satellitesearch.html)
  - [open source](https://github.com/RemotePixel/satellitesearch) viewer for Landsat-8 and Sentinel-2 data hosted by AWS
  - uses [**`sat-api`**](https://github.com/sat-utils/sat-api)
- [**Sinergise "Sentinel Playground"**](http://apps.sentinel-hub.com/sentinel-playground)
  - visualize AWS Sentinel-2 data in different band combinations ando offers a [WMS/WMTS service](http://www.sentinel-hub.com/apps/wms).
- [**EOSDA "Land Viewer"**](https://lv.eosda.com/)
  - viewer for Landsat-8 and Sentinel-2 data hosted by AWS
- [**jeobrowser "Rocket"**](https://mapshup.com/projects/rocket)
  - viewer for Sentinel (1,2,3), Landsat-8, SPOT and Pleiades imagery
  - based on [resto](https://github.com/jjrom/resto) search engine and used as frontend for [PEPS](https://peps.cnes.fr/rocket/)
  
### processing
- [**`SNAP` (Sentinel Application Plattform)**](http://step.esa.int/main/toolboxes/snap/)
  - (pre-)process any Sentinel data
  - also available as [docker](https://github.com/edwardpmorris/docker-snap)
- [**`Sen2Cor`**](http://step.esa.int/main/third-party-plugins-2/sen2cor/)
  - athmospheric correction of Sentinel-2 data
  - also available as [python package](https://github.com/umwilm/SEN2COR)
- [**Google Earth Engine**](https://earthengine.google.com/)
  - process the global Sentinel-1 and Sentinel-2 archives directly on Google's servers

Know another awesome API, mirror or app that is missing from this list? Send it to me via [Email](mailto:kersten@krstn.eu), [Twitter](https://twitter.com/Fernerkundung) or open a pull request on [Github](https://github.com/Fernerkundung/awesome-sentinel/).
