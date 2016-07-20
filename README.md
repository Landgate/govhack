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
If your goal is to quickly explore and see what data is available then there are a range of pre-packaged maps available that will make that task a breeze.

- A set of themed maps are available for Western Australia covering the themes of [environment, infrastructure, property and more](http://slip.landgate.wa.gov.au/Pages/Public-Maps.aspx).

- The [NationalMap](http://nationalmap.gov.au/) provided map-based access to spatial datasets across all levels of Australia Federal, state, and local governments.


## The Analyst
If your focus is actually getting at the raw data itself, running queries against it, and analysing it then you have the choice of downloading data and analysing it locally, or using our APIs to do the heavy lifting for you.

### Downloading data
Geospatial datasets are currently available to download from data.wa.gov.au in two formats - Shapefile and Map Package. These downloads are automatically snapshotted and refreshed on a nightly basis.

@TODO Screenshot

See our [Jaron busting guide](#jargon_busting) for a description of the formats.

> *Note:* While most of the datasets downloads are freely available, you will be prompted to sign in when you download a dataset. This helps us to better understand and engage with the end users of our datasets. Simply register an account and login you'll be able to proceed to download your datasets.

@TODO Screenshot

Once you've downloaded your datasets there's a wide range of different tools available to help you query, convert, and analyse the data:

* *Quick visualisation and data format conversion:*
  * [GeoJSON.io](http://geojson.io/#map=2/20.0/0.0): A simple website for that allows for uploading, converting, and visualising moderately sized spatial datasets. You can also draw and create your own spatial datasets - handy for creating dummy datasets!
  * [Ogre](https://ogre.adc4gis.com/): A handy website to convert many common spatial data formats (including shapefiles) to the modern [GeoJSON](http://geojson.org/) format.
  * [NationalMap](http://nationalmap.gov.au/): NationalMap is not only a handy catalogue of government datasets, you can also upload and visualise other datasets on it (supports common formats like GeoJSON, KML, GPX, and more).
* *Platform as a Service Maps:* 
  * [Carto](https://carto.com/) (**formerly CartoDB**): A simple, easy-to-use platform for everyone (not just geospatial nerds). Upload your data, hook into common datasets (e.g. country borders, administrative boundaries), and create beautiful web and mobile maps right from your browser.
  * [ArcGIS Online](https://www.arcgis.com/home/index.html): Make and share beautiful maps, and do everything in between. Maps, apps, analytics, administration, collaboration through an easy-to-use mapping solution.
  * [MapBox](https://www.mapbox.com/): Mapbox is a mapping platform for developers. Easily integrate location into any mobile or online application. Search, geocoding, real-time data, directions and routing, 2.5D and 3D maps.
* *Desktop software:*
  * [QGIS](http://www.qgis.org/en/site/): The open source Geographic Information System. Create, edit, visualise, analyse, and publish geospatial information on Windows, Mac, Linux, and BSD.
  * [ArcGIS Pro](http://www.esri.com/en/software/arcgis-pro): ArcGIS Pro reinvents desktop GIS. Design and edit in 2D and 3D, work with multiple displays and layouts, and publish finished web maps directly to ArcGIS Online or Portal for ArcGIS, connecting you to users throughout the world.
* *Databases:*
  * [PostGIS](http://postgis.net/): Spatial databases aren't just for storing data - they're great for conduct complex analysis tasks if you're happy writing SQL queries. For spatial databases consider nothing but the best: the PostGIS extension to [PostgreSQL](https://www.postgresql.org/). If there's a spatial query or manipulation you need to do then PostGIS has it; and hundreds of other functions besides.

### Using APIs
> Benefits

@TODO Screenshot

See our [Jaron busting guide](#jargon_busting) for a description of these APIs.


> APIs: ESRI REST/WMS/WFS
>> NatMap, AGO
>> Web Libraries, Mobile Libraries
>> QGIS, ArcGIS, et cetera

> Tools
>> Command-line
>> GeoJSON.io, ogr2ogr Ogre
>> GitHub GeoJSON


### Visualising GeoJSON
You can also map the GeoJSON data that the GME API returns. [OpenLayers](http://openlayers.org/dev/examples/?q=geojson) and [Leaflet](http://leafletjs.com/examples/geojson.html) support GeoJSON natively and GitHub itself [will render GeoJSON files](https://help.github.com/articles/mapping-geojson-files-on-github).




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
