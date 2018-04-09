## All the roundabouts found in Switzerland on Open Street Map
https://github.com/mathieurudaz/notebooks/blob/master/2018/rondspoints/ch_roundabouts-EPSG32632.geojson  
**EPSG: 32632**  
25m buffer around each roundabout

### Query used on overpass-turbo
http://overpass-turbo.eu/

```
[out:json][timeout:25];
{{geocodeArea:Switzerland}}->.searchArea;
(
  node["junction"="roundabout"](area.searchArea);
  relation["junction"="roundabout"](area.searchArea);
  way["junction"="roundabout"](area.searchArea);

  node["highway"="mini_roundabout"](area.searchArea);
  relation["highway"="mini_roundabout"](area.searchArea);
  way["highway"="mini_roundabout"](area.searchArea);
  
);
out body;
>;
out skel qt;
```

https://wiki.openstreetmap.org/wiki/Tag:junction%3Droundabout

> A **roundabout** is a one-way street with right-of-way and a non-traversable centre island. There can be traffic light, as long as the circular road has right-of-way when the lights are off.

> A **mini-roundabout** is a one-way street with right-of-way and a traversable centre island. In particular, large vehicles are allowed to drive across the centre island if otherwise not possible due to their dimensions, i.e. it might be impossible for a large vehicle to drive through a roundabout but possible to drive through a mini-roundabout with the same dimensions.

### Some roundabouts seem to be missing
At least one roundabout seems to be missing in Renens:
https://www.openstreetmap.org/way/305613715#map=18/46.53610/6.57619  
oversight or not considered as roundabout?