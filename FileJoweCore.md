# Jowe-Core #

This is the main file of the project. It contains the "engine" to construct your map.
It only produces an array of integer with random values. That's the single purpose of that object.
That way, its result could be used in any other GUI.

## Usage ##

### Method 1: Calling methods individually ###

```
// Create a new HeightMap object with default values
// pitch = 8, ratio = 3.1, width = 127, height = 127
var oMap = new HeightMap();

// Set the requested size for the final array (zero-based).
// Below you'll get an array of [0..9][0..11].
oMap.setSide(10, 12);

// Process the random height map.
oMap.makeMap();

// Optional, but smoothing the map is often required to avoid weird points and
// produce better looking map. For now, smooth only works on non-cropped maps.
// Once the map is cropped, smooth will failed (will be fixed in a next release).
oMap.smooth();

// Finally, crop the working map to get the one with the requested size (10,12) as set previously.
oMap.crop();
```

### Method 2: Calling the "all-in-one" method ###

```
// Create a new HeightMap object with default values.
var oMap = new HeightMap();
// Shortcut to generate a map (direct calls to "setSide", "makeMap", "smooth" and "crop").
oMap.doMap(10,12);
```

Both usages will give you an item array which will looks like the one below :

```
oMap.item =
  [[6,6,5,5,4,4,3,3,3,4,4,4] 
  ,[6,5,5,5,4,4,3,3,3,4,4,4] 
  ,[5,5,5,5,4,4,3,3,3,4,4,4] 
  ,[5,5,5,4,4,3,3,3,3,4,4,4] 
  ,[4,4,4,4,3,3,3,3,3,4,4,4] 
  ,[4,4,3,3,3,3,3,3,3,4,4,4] 
  ,[3,3,3,2,2,2,3,3,3,3,4,4] 
  ,[3,3,2,2,2,2,2,2,3,3,4,4] 
  ,[2,2,2,2,2,2,2,2,2,3,3,4] 
  ,[2,2,2,2,2,2,2,2,2,3,3,3]]
```

## Notice ##

For an online help on how to use the jowe-core.js file, follow that [link](http://jowe.ouebfrance.com/examples-jowe-core.html)

## Documentation ##

[Online](http://jowe.ouebfrance.com/jsdoc/symbols/HeightMap.html) documentation for the HeightMap object provided by the jowe-core.js file.