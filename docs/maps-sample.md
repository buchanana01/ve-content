<param ve-config
       title="Map samples"
       banner=""
       layout="vtl"
       author="JSTOR Labs team">

<param ve-component 
       name="mapViewer"
       src="/components/LeafletTimeDimension.vue"
       selectors="tag:map"
       icon="fa-map-marker-alt"
       label="Maps">

## Introduction

This sample essay provides examples showing how maps can be incorporated into an essay.  Various features are used in the examples.

## The simplest possible map

The most basic map tag is `<param ve-map>`.  Inserting this tag into an essay will result in a map at the default location and zoom level using the standard base map.  The map center defaults to `25` (latitude) and `0` (longitude).  The zoom level defaults to `2.5`.  The standard base map is `OpenStreetMap`. This paragraph also has a <span data-click-map-flyto="41.893,12.483,10" data-mouseover-map-flyto="41.893,12.483,11">flyto Rome</span> interaction. Or, <span data-mouseover-map-flyto="45.440, 12.332, 13">goto Venice</span>
<param ve-map>

## A map with custom center and zoom

Maps can be customized in many ways but the most common customizations are to set a center point and zoom level.  The center point can be set using the latitude and logitude values or by specifiying the Wikidata QID for the location in which case the visual essay tool will query Wikidata for the corresponding lat/lon coordinates.  In this example, centering the map on Rome, the lat/lon coordinates are explicitly set - `<param ve-map center="41.893,12.483" zoom="10">`
<param ve-map center="41.893,12.483" zoom="10">

## A map with custom center using Wikidata entity for coordinates

This map should look identical to the previous one.  The difference is that we're using the Wikidata identifier (`Q2201`) for Rome as the center attribute in the map tag - `<param ve-map center="Q220" zoom="10">`
<param ve-map center="Q220" zoom="10">

## A map with a marker

In this example we're again using Rome as the center point.  We've also added an entity tag for Rome (`<param ve-entity eid="Q220">`) and a mention in this paragraph text which will result in a location marker automatically added to the map.
<param ve-entity eid="Q220">
<param ve-map center="Q220" zoom="10">

## A map with a marker and labels opened on map display 

The default behavior is to display location labels only when the mouse hovers over the marker.  If the `show-labels` attribute is addded to the `ve-map` tag labels will be automatically displayed when the map is opened.
<param ve-entity eid="Q220">
<param ve-map center="Q220" zoom="10" show-labels>

## Displaying GeoJSON shapes instead of markers 

Many location entities in Wikidata can automatically be associated with a GeoJSON
region in addition to the latitude and longitude coordinates.  Adding the `prefer-geojson` attribute to the `ve-map` tag will result in the GeoJSON shape being
used for Rome on the map instead of a marker.
<param ve-entity eid="Q220">
<param ve-map center="Q220" zoom="10" prefer-geojson>

## Using external GeoJSON map layer 

One or more external GeoJSON files can be used as map layers.  Each file
is specified in a separate `ve-map-layer` tag with a `url` attribute containing the location of the file.
<param ve-map>
<param ve-map-layer url="/geojson/cities.json">

## Using external GeoJSON map layer with time dimension 

One or more external GeoJSON files can be used as map layers.  Each file
is specified in a separate `ve-map-layer` tag with a `url` attribute containing the location of the file.
<param ve-map 
       time-dimension
       time-interval="-008000/"
       duration="P10000Y"
       basemap="Esri_WorldGrayCanvas"
       max-zoom="4"
       date-format="YYYY"
       auto-play="false"
       auto-fit="false"
       fps="4">
<param ve-map-layer url="/geojson/cities.json">

## Using a georeferenced image overlay

This map of the county of Kent in the UK uses the standard OSM basemap overlaid with a georeferenced topographic survey map from 1860.

<param ve-map center="51.254, 0.876" zoom="10">
<param ve-map-layer active mapwarper mapwarper-id="44832" title="Kent Topo Survey 1860">