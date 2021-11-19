# Lab 09/10

## Overview
For this lab, you will develop a simple fitness tracking app.  The user will be able to record points, and see a map of those recorded points updated in real time.

_**Note:** This lab is designed to take 2 weeks, and will be worth the value of two lab assignments.  It is recommended that you develop the map interface in the first week, using placeholder data (e.g. an array of locations).  You can implement the geolocation and geocoding functionality in the second week._

## Instructions
The floating action button will cause the current location to be recorded, and its address/location name looked up using geocoding.  A `FlutterMap` will display all recorded points, both as a polyline connecting them (in order), and using a map marker.

### The Map
First, you will need a class to store the data for the stored points (`Location`):
- `name` (`String`)
- `address` (`String`)
- `latlng` (using the `LatLng` class, storing the geolocation coordinates)

Create a placeholder array of such `Location` objects, and use that for the data for your map's polyline and markers.


The `FlutterMap` will have 2 main components:
- options which will set the max and min zoom levels
- layers which will have the following layers:
    - `TileLayerOptions` - this will be configured to use a MapBox API (use your own token)
    - `MarkerLayerOptions` - this will generate a list of `Marker` instances, one for each location
    - `PolylineLayerOptions` - this will generate a single `Polyline` instance, consisting of the stored location points

### Creating the Data
The floating action button for the app will do the following:
- Use the geolocator plug-in to get the current position
- Use the geocoding plug-in to obtain the placemark for the current position, which will contain:
    - `name`:  `placemark.name`
    - `address`:  `street, locality, postalcode, country`
- For this lab, you can simply show the extracted address from the coordinates on the console.

The data should now be dynamic.  You can enter different GPS coordinates using the settings of the emulator, if you want to test it out.  You can also download and use a GPX/KML file, which contains a list of geolocation coordinates.  This is what was done for the screenshot.  Alternatively, you can use a physical device.

One such file, representing a hike through the wilderness, can be found in this repository:
- `data/cedar_valley.gpx`

![a screenshot of the app](https://github.com/csci-4100u/lab09-10/blob/bda4d0755f6386fbe2ce3ba5d7a8e2c6054a246e/images/map.PNG)

_Figure 1 - A screenshot of the app, showing the map, the floating action button, and the app bar icons_

## Getting Help
If you run into difficulty, you may wish to check out some of the following resources:

- https://api.flutter.dev/  - The standard documentation for Flutter, all classes and methods.
- https://dart.dev/tutorials - A series of tutorials for the Dart programming language, focusing entirely on the features of Dart.
- https://flutter.dev/docs/reference/tutorials - A series of tutorials for the Flutter platform, focusing mainly on the widgets and API.
- https://flutter.dev/docs/codelabs - A series of deep-dive, more comprehensive, tutorials to learn more about the Flutter platform.
- https://flutter.dev/docs/cookbook - A set of recipes for commonly used features of Flutter.
- https://github.com/flutter/samples/blob/master/INDEX.md - A repository containing some completed Flutter applications.
- http://stackoverflow.com/ - A forum for asking questions about programming.  I bet you know this one already!

Of course, you can always ask the TA for help!  However, learning how to find the answers out for yourself is not only more satisfying, but results in greater learning as well.

## How to Submit
Create your flutter project inside this folder, commit, and then push your code to this repository to submit your lab assignment.
