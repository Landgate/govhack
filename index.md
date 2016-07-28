---
layout: default
---

# Hi
These are a set of code samples we've prepared for developers and hackers participating in 
[GovHack](http://govhack.org) to quickly get up to speed with using WA Government's
[**Shared Location Information Platform (SLIP)**](http://slip.landgate.wa.gov.au).  

If you've stumbled on this page you might want to check out data.wa.gov.au's more general 
guidance for everyone, not just developers at [data.wa.gov.au/govhack](http://data.wa.gov.au/govhack).

## Need help?
Get in touch with a member of [our friendly team of mentors](http://portal.govhack.org/sponsors/landgate.html).
We love nerding out about everything geospatial :)

# Code Samples
We realise that getting started with SLIP and the ArcGIS Server platform may not be the easiest task - particularly if you aren't a spatial nerd - so we've put together some code samples and demo apps to help developers get off to a flying start.

The initial set of code samples primarily concern themselves with visualising data (WMS and ESRI MapServer) or extracting the underlying raw feature data (WFS and ESRI FeatureServer). We plan to expand the range of samples over time to include more than just web maps (e.g. Python scripts, mobile apps), and more complex sample applications demonstrating some of the more advanced features of ArcGIS Server.

The data used here are all publicly available from [data.wa.gov.au](http://data.wa.gov.au).

If you spot any bugs in these samples, or have an idea of a code sample you'd like to see, do please file an issue in GitHub. If you have any trouble with these code samples, or there's something you'd like to do but aren't show of how, please contact us.

## ESRI's Documentation

Our SLIP platform is based on ESRI's [ArcGIS Server](http://server.arcgis.com/) technology, and these days ESRI is all about [*"Developers, Developers, Developers"*](https://www.youtube.com/watch?v=KMU0tzLwhbE), so do check out their [ArcGIS for Developers](https://developers.arcgis.com/) site.

![ArcGIS for Developers header banner screenshot](images/esri/arcgis-developers.png)

Or just jump right in to [their GitHub repos](http://esri.github.io/).

![ESRI GitHub repos header banner screenshot](images/esri/esri-github.png)


# ArcGIS JavaScript API 4.0 Code Samples
[ArcGIS JavaScript API 4.0 Documentation](https://developers.arcgis.com/javascript/)

## MapImageLayer
Let's start simple by grabbing some shipwrecks data and displaying them as pre-rendered image tiles on a 3D globe using a [MapImageLayer](https://developers.arcgis.com/javascript/latest/api-reference/esri-layers-MapImageLayer.html) layer.

<a href="esri/mapimagelayer.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/esri/mapimagelayer.html" class="obnoxious-button"><strong>Get the code</strong></a>

## FeatureLayer
This time let's use the raw data to render our shipwrecks client-side using a [FeatureLayer](https://developers.arcgis.com/javascript/latest/api-reference/esri-layers-FeatureLayer.html) layer. (We haven't demonstrated it here - but client-side rendering means you're in control of the styling and presentation of the data. Custom symbology ahoy!)

<a href="esri/featurelayer.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/esri/featurelayer.html" class="obnoxious-button"><strong>Get the code</strong></a>

## FeatureLayer Querying
OK, let's step it up a notch and build on the previous example by dynamically querying our shipwrecks to populate a list of wrecks, and throw in a popup info window for good measure.

<span style="color: red;">&#x2764;</span> [`queryFeatures()`](https://developers.arcgis.com/javascript/latest/api-reference/esri-layers-FeatureLayer.html#queryFeatures)

<a href="esri/queryfeaturelayer.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/esri/queryfeaturelayer.html" class="obnoxious-button"><strong>Get the code</strong></a>

## Custom Client-side Rendering
Now we're just going to show off a little - let's grab the ABS's 2011 Census data on [dwellings per suburb](http://catalogue.beta.data.wa.gov.au/dataset/abs-b31-dwelling-structure-ssc), roughly bin suburbs in Western Australia by the number of dwellings they have, and apply a custom client-side renderer over the top with some funky colours. 

<a href="esri/featurelayer-custom-renderer.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/esri/featurelayer-custom-renderer.html" class="obnoxious-button"><strong>Get the code</strong></a>


# OpenLayers Code Samples
[OpenLayers](http://openlayers.org/)

## Web Map Service & feature querying
A simple one to start with here - we'll display townsites in Western Australia's as image tiles on a map, and throw in an interactive *"What features are at this location"* query ability.

<a href="openlayers/wms-getfeatureinfo.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/openlayers/wms-getfeatureinfo.html" class="obnoxious-button"><strong>Get the code</strong></a>

## Web Feature Service *[WORK IN PROGRESS]*
This time we'll use a WFS service to pull down some raw data and render it client-side.

<a href="openlayers/wfs.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/openlayers/wfs.html" class="obnoxious-button"><strong>Get the code</strong></a>


# Leaflet Code Samples *[WORK IN PROGRESS]*
[Leaflet](http://leafletjs.com/)

## Web Feature Service *[WORK IN PROGRESS]*
This time we'll use a WFS service to pull down some raw data and render it client-side.

<a href="leaflet/wfs.html" class="obnoxious-button"><strong>View live example</strong></a>
<a href="https://github.com/Landgate/govhack/blob/master/leaflet/wfs.html" class="obnoxious-button"><strong>Get the code</strong></a>