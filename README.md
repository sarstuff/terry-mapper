# terry-mapper
An application made with electron to display, edit, and print offline maps with overlays.

## Features

- offiline maps using [Mapbox GL JS](https://github.com/mapbox/mapbox-gl-js) and [Electron](https://github.com/electron)
- converts OSM files to geojson (using [osmtogeojson](https://github.com/tyrasd/osmtogeojson))
- uses geojson files as only source of a custom mapbox style
- it is now automatically converting .osm files that are pasted into ```src/maps/``` folder.
- ```src/maps_overlay``` is instead used to store pois and areas for the territories.


## TODOs

- have several files imported and displyed (WIP)
- interface to draw polygons and pois and save them (WIP)
- interface to modify and locally save styles
- printing maps (WIP)

## Installation
Download the files in a local folter, then run npm install. i.e.:
```
cd terry-mapper
npm install
```

## Maps folder
```
src/maps/
```

It is used to store maps in OSM format, if placed here the files will be automatically converted into __geojson__ format, then rendered into the application.

## Maps overlay folder
```
src/maps_overlay/
```

This folder stores the maps overlays, areas and points.

Each feature will be rendered using the following properties:

- name -> will be displayed as a label
- poi -> classifies the type of area-point, it does nothing for now.


Here an example:
```
"features": [
    {
      "type": "Feature",
      "properties": {
        "name": "Fla. Araki",
        "poi" : "home"
      },
      "geometry": {
        "coordinates": [
          -78.40355448825697,
          -0.3539252347306814
        ],
        "type": "Point"
      },
      "id": "6ea5c4429125564c63d68d0aea1617ab"
    },
```
