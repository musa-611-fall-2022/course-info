# GeoJSON

GeoJSON is a special case of the JSON data format. **JavaScript Object Notation (JSON)** is a data format that grew out of JavaScript, but now exists beyond JavaScript. It uses a constrained form of the object-literal syntax from JavaScript to represent data in a highly flexible way.

* Curly braces surround a JSON object.
* Each object has keys wrapped in double quotes.
* Each key has a corresponding value. Together they are a "key/value pair", or an "attribute".
* Values can have one of the following data types:
  - number
  - string
  - boolean
  - null
  - array
  - object

**GeoJSON** followes all of the rules above (as it is just JSON), but has a few additional rules as well:

* Every GeoJSON object has a `type` attribute
* Depending on the value of the `type` attribute, the GeoJSON object must contain some other attributes:
  * For geometry `type` values (i.e., `"Point"`, `"LineString"`, `"Polygon"`, etc.) the object must also have a `coordinates` attribute that is an array. The specific content of the `coordinates` attribute depends on the `type` value.
  * For a `type` value of `"Feature"`, the object must have:
    * a `properties` attribute -- an object of additional data attached to the feature.
    * a `geometry` property -- a GeoJSON object with a geometry `type`.
  * For a `type` value of `"FeatureCollection"`, the object must have a `features` attribute that is an array of GeoJSON objects with `type` of `"Feature"`.

## Examples

Simple JSON example
```json
{
  "first_name": "Mjumbe",
  "last_name": "Poe"
}
```

GeoJSON example
```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "address": "123 Sesame St",
        "owner": "Oscar the Grouch"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-75.16, 39.94]
      }
    }
  ]
}
```

## Tools
* GeoJSON.io - https://www.geojson.io

## Helpful references
* More than you ever wanted to know about GeoJSON: https://macwright.com/2015/03/23/geojson-second-bite.html

## Recommended reading
* Introduction to Web Mapping chapter on GeoJSON: http://132.72.155.230:3838/js/geojson-1.html
