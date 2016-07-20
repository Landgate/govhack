GovHack
============

Hi GovHacker,

Herein you shall find a collection of resources, tips, and examples to help you to get started using data from [data.wa.gov.au](http://data.wa.gov.au/).

# WA Government Open Data

## What data is available?

Over 700 datasets from more than 40 WA government agencies are available at [data.wa.gov.au](http://catalogue.beta.data.wa.gov.au/dataset) for use at GovHack, including:

* Property boundaries and sales records
* A high resolution aerial photo mosaic of Western Australia
* A collection of historical aerial photos dating back to 1948, and historic maps back to 1838
* Administrative boundaries
* Locations of schools, universities, hospitals, and emergency services
* Transport infrastructure
* Mining tenements and minerals deposits
* A cut of information from the 2011 Census
* Information on the sewer system, water pipes, and water meters.
* Environmental datasets and boundaries
* Mining and resources data
* Native Title determinations and Indigenous Land Use Agreements
* Aboriginal communities and heritage places
* Geological and teophysical data
* Power and water utilities data

## Help and Mentors
Confused? Can't find data? Contact [our friendly team of mentors](http://portal.govhack.org/regions/western_australia.html#mentors) from across WA government who'll be available on-site in Perth, and around the country on Slack.

### I can't find the dataset I want
If you're having trouble finding a dataset don't sweat it! Data.wa.gov.au is still in its infancy and doesn't yet list every dataset in Western Australia. Talk to our team of mentors and they may be able to help you find it - they've years of experience in dealing with and tracking down datasets across all levels of government.


## Jargon busting
Throughout data.wa.gov.au and this document you'll find reference to various technical and acronyms, so we've put together a quick jaron busting guide:

![An example list of the different resources that may be attached to a dataset.](example-dataset-resources.png)

*[Web Mapping Service (WMS)](https://en.wikipedia.org/wiki/Web_Map_Service):* A service for generating sets of image tiles used in web mapping. It converts raw spatial datasets into georeferenced images and is a widely used international open standard; as well it supports querying the data ("Tell me about the features at a point"). WMS services available via data.wa.gov.au are served through SLIP.

*[Web Feature Service (WFS)](https://en.wikipedia.org/wiki/Web_Feature_Service):* A service for retrieving raw geospatial datasets and running queries against a dataset (e.g. "Tell me all of the points in this area where the `type` is 'red'."). Unlike a WMS the output of a WFS service must first be passed to software that can visualise spatial data (See @TODO). WFS services available via data.wa.gov.au are served through SLIP.

*ESRI REST API:* A service similar very similar in functionality to WMS and WFS that is available from using the [ESRI](http://www.esri.com/) technology stack. This resource provides a machine-readable ESRI REST API for visualising and accessing this dataset. This API can be used in a variety of ESRI products – including ArcGIS, ArcGIS Pro, and the ArcGIS API for JavaScript. ESRI REST API services available via data.wa.gov.au are served through SLIP.

*[Shapefile](https://en.wikipedia.org/wiki/Shapefile):* An older but still very popular format for spatial datasets. Easy to read, manipulate, and convert to other data formats using spatial software packages (@TODO).

*[Service Map Package](https://blogs.esri.com/esri/arcgis/2010/09/29/map-packages/):* A proprietary format created by the spatial sofware company, [ESRI](http://www.esri.com/), for storing spatial data and their associated styles. Only acessible to users with ArcGIS Desktop or ArcGIS Pro.

*Data dictionaries:* Documents prepared by data custodians with further in-depth information about their datasets, including descriptions and examples of each of the fields in the dataset.

*[SLIP](http://slip.landgate.wa.gov.au):* The Shared Location Information Platform (SLIP) is a repository of spatial, or location-based, datasets from Western Australian government agencies coordinated by Landgate on behalf of the WA Government. Many of the datasets you find on data.wa.gov.au will be hosted and served out of SLIP

## Public, Subscription, and Restricted datasets
The goal of data.wa.gov.au is to make all WA government data discoverable from one place - which means we have data listed that isn't 100% open. Broadly speaking there are three different classifications of data -

*Public:* Datasets that are 100% openly and freely available to use and download under a Creative Commons license.

*Subscription:* Datasets that are open to use, but are typically part of a chargeable service.

*Restricted:* Datasets that are restricted for use to authorised government agencies, typically due to their sensitive nature, and for reasons of security and privacy.

If you find a dataset that you'd like to use for GovHack that isn't public don't worry - in some cases we'll be able to give you access for a limited time to use the data in your GovHack project. Get in touch with our team of mentors regarding access.



# Using SLIP - A technical guide for developers and hackers

This rest of this document will serve as a brief overview and introduction of the SLIP platform for developers and hackers.

SLIP is a cloud-based platform utilising ESRI's [ArcGIS Server](http://www.esri.com/software/arcgis/arcgisserver) and [PostgreSQL](https://www.postgresql.org/) to provide a range of geospatial data APIs and [map services](http://slip.landgate.wa.gov.au/Pages/Public-Maps.aspx).

More general information about SLIP is available at [slip.landgate.wa.gov.au](http://slip.landgate.wa.gov.au/).

We love user-centred design, so we've written this guide for three different user personas.

1. *The Strategist:* I want to look at datasets on a map, to explore what's available, and think about how I can use data at a high-level.
2. *The Analyst:* I need to download whole datasets and use them in their raw form to analyse and interrogate them. I'm comfortable using analysis and visualisation software.
3. *The Developer:* I need to design and create maps or geospatial applications for the web and mobile platforms. I'm a developer and I'm comfortable in the world of APIs and software developmemt. I'd prefer to use other people's data APIs to query and visualise data.

## Technical assistance with SLIP
Confused? Don't understand how to do something? Contact [our friendly team of mentors](http://portal.govhack.org/sponsors/landgate.html) who'll be available on-site in Perth, and around the country on Slack.

## An introduction to geospatial data and services
If you're new to working with spatial data or mapping we highly recommend you spend some time reading [mapschool.io: a free introduction to geo](http://mapschool.io/).

(Trust us - it'll save you much head scratching and bafflement later on.)

You may also want to check out the [Working with Geographic Data](http://govhack-toolkit.readthedocs.org/technical/geographic-data/) and [In which we play at being cartographers](http://govhack-toolkit.readthedocs.org/technical/making-maps/) sections in the GovHack Handbook for a deep dive on all of the awesome tools available for working with spatial data.


## The Strategist
> NM

## The Analyst
If your focus is actually getting at the raw data itself, running queries against it, and analysing it then the [Google Maps Engine API](https://developers.google.com/maps-engine/) is your friend.

The GME API is a RESTful API that speaks and consumes JSON. Our [Getting Started](https://github.com/Landgate/slip-developer-documentation/wiki/Getting-Started) documentation and [GME API Tutorial](https://github.com/Landgate/slip-developer-documentation/wiki/Tutorial-%231%3A-The-GME-API-%26-WFS) have more information on working with the GME API. We've also got a few [code samples](https://github.com/Landgate/slip-code-samples) demonstrating more advanced uses of the GME API.

Accessing data via the Google Maps Engine API is at the datasource level and requires a datasourceId to be provided (see ```layers.json``` above).


### Visualising GeoJSON
You can also map the GeoJSON data that the GME API returns. [OpenLayers](http://openlayers.org/dev/examples/?q=geojson) and [Leaflet](http://leafletjs.com/examples/geojson.html) support GeoJSON natively and GitHub itself [will render GeoJSON files](https://help.github.com/articles/mapping-geojson-files-on-github).


### Command line
If command-line is more your thing there's work underway to support the GME API within the [GDAL](http://www.gdal.org/). See the [GMEDriver documentation](http://trac.osgeo.org/gdal/wiki/GMEDriver) for more information.

### Error: *"This resource is too large to be accessed via this API call."*
If you receive this error message, let us know, and we can provide the details for an account with special access to larger data sources.


## The Developer
If you just need to be able to generate a visual representation of the data (e.g. display it on a map, generate once-off images) you have three APIs available:

* WMS: A RESTful API (Web Mapping Service)
  > A WMS returns JPEG/PNG images for one or more layers in a map service; as well as supporting querying the data ("tell me about the features at a point").
* WMTS: A RESTful API (Web Map Tiling Service)
  > A WMTS returns 256x256 JPEG/PNG images for a singe layer in a map service; it  also supports querying the data.
* Google Maps JavaScript API
  > The Google Maps JavaScript API implements its own version of a WMS-like interface via [MapsEngineLayer](https://developers.google.com/maps/documentation/javascript/mapsenginelayers). It also supports client-side rendering and styling of data via [DynamicMapsEngineLayer](https://developers.google.com/maps/documentation/javascript/mapsenginelayers#dynamicmapsenginelayer_events).

To consume any of these APIs you'll want a client library to do the heavy lifting for you. Fortunately you're spoilt for choice!

### WMS & WMTS
[OpenLayers 2](http://openlayers.org/), [OpenLayers 3](http://ol3js.org/), [Leaflet](http://leafletjs.com/), amd [MapBox JS](https://www.mapbox.com/mapbox.js) can all be used to easily consume WMS and WMTS services.


> **WMS:** [Locate](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/wms/?REQUEST=GetCapabilities) | [Resources](https://mapsengine.google.com/09372590152434720789-11493353092997567468-4/wms/?REQUEST=GetCapabilities) | [Sandbox](https://mapsengine.google.com/09372590152434720789-00440247219122458144-4/wms/?REQUEST=GetCapabilities)
>
> **WMTS:** [Locate](https://mapsengine.google.com/09372590152434720789-00913315481290556980-4/wmts/?REQUEST=GetCapabilities) | [Resources](https://mapsengine.google.com/09372590152434720789-11493353092997567468-4/wmts/?REQUEST=GetCapabilities) | [Sandbox](https://mapsengine.google.com/09372590152434720789-00440247219122458144-4/wmts/?REQUEST=GetCapabilities)]

> **Note:** When referring to layers in WMS and WMTS remember to prepend ```-4``` to the layerId.


#### Google Maps JavaScript API
The [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/tutorial) has connectors specifically [for Google Maps Engine](https://developers.google.com/maps/documentation/javascript/mapsenginelayers).

There are two means of connecting to Google Maps Engine:

1. Via the layerId (recommended - see ```layers.json```), or
2. By supplying a mapId and a layerKey.


# Tools for working with spatial data
We've referred to a few tools that we like, for a much more comprehensive list check out the [Working with Geographic Data](http://govhack-toolkit.readthedocs.org/technical/geographic-data/) and [In which we play at being cartographers](http://govhack-toolkit.readthedocs.org/technical/making-maps/) sections in the GovHack Hacker Toolkit.

## Software libraries
For non-client facing calls you can either build the URLs  yourself; alternatively you can use existing libraries like [OWSLib (Python)](https://pypi.python.org/pypi/OWSLib) or [GeoTools (Java)](http://geotools.org/).

## Make your own maps
If you have data you want to load into a system to render and map you're spoilt for choice these days:

* [Google Maps Engine](http://mapsengine.google.com) (as noted earlier - our development environment is available).
* [CartoDB](http://cartodb.com/)
* [TileMill](https://www.mapbox.com/tilemill/)
* [MangoMap](http://mangomap.com/)

## APIs
For playing with any of these APIs we recommend use of the [Postman](http://www.getpostman.com/) HTTP Client. It makes exploring and testing APIs a breeze.

## Desktop software and offiline processing
For spatial databases consider nothing but the best: the [PostGIS](http://postgis.net/) extension to PostGreSQL. If there's a spatial query or manipulation you need to do then PostGIS has it; and a hundred other functions besides.

For viewing and manipulating spatial data on the desktop you can't go past [QGIS](http://www.qgis.org/en/site/), the open source Geographic Information System.

For command line tools check out [GDAL](http://www.gdal.org/) (Geospatial Data Abstraction Library), which has readers and writers for over 50 types of spatial data. GDAL bindings also exist in Python, .NET, et cetera.
