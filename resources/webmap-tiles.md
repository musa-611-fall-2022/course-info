# Map Tiles

See the Leaflet recommended reading below for context around what map tiles literally are (at least in a raster web context).

To use some of Mapbox's pre-made styles, you'll have to have a Mapbox access token (which you can get by simply signing up for a free account). Then you'll want to create a Leaflet tile layer using something like this:

```js
const mapboxAccount = 'mapbox';
const mapboxStyle = 'light-v10';
const mapboxToken = '...'
L.tileLayer(`https://api.mapbox.com/styles/v1/${mapboxAccount}/${mapboxStyle}/tiles/256/{z}/{x}/{y}@2x?access_token=${mapboxToken}`, {
    maxZoom: 19,
    attribution: '© <a href="https://www.mapbox.com/about/maps/">Mapbox</a> © <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> <strong><a href="https://www.mapbox.com/map-feedback/" target="_blank">Improve this map</a></strong>',
}).addTo(schoolMap);
```

Any time you use tiles directly from or based on some ready-made source, be sure to use an appropriate attribution. The attribution used above was taken from [Mapbox's documentation](https://docs.mapbox.com/help/getting-started/attribution/#other-mapping-frameworks).

## Recommended reading
* Leaflet's documentation on zoom levels: https://leafletjs.com/examples/zoom-levels/

## Other resources
* Mapbox Style Gallery: https://www.mapbox.com/gallery/
* Mapbox's core styles: https://docs.mapbox.com/api/maps/styles/#mapbox-styles
* The Leaflet Providers extension: https://github.com/leaflet-extras/leaflet-providers (preview tiles in [the gallery](http://leaflet-extras.github.io/leaflet-providers/preview/index.html))
