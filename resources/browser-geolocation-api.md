## Geolocation API

The [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API) allows the user to provide their location to web applications if they so desre. There are two primary functions available in the geolocation API: `getCurrentPosition` and `watchPosition`.

The `getCurrentPosition` function retrieves the devices current location one time. The function takes up to three arguments: the first is a callback function that gets called if the device's location is successfully found; the second is a callback that gets called if there's some error while determining the device's location; and the third is a options object.

The `watchPosition` function retrieves the device's location each time it gets updated by the device. The function takes the same arguments as `getCurrentPosition` but the callback functions may get called a number of times.

For both `getCurrentPosition` and `watchPosition`, the success callback gets called with a single [`GeolocationPosition`](https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPosition) argument.

You use the functions like:

```js
navigator.geolocation.getCurrentPosition((pos) {
  ...
}, (err) {
  ...
});
```

One important difference in usage is that you usually want to store the return value from calling `watchPosition`. This value will be an ID that you can use to cancel the ongoing geolocation:

```js
// Start watching the user's position.
const geolocID = navigator.geolocation.watchPosition(...);

...

// Cancel watching the user's position.
navigator.geolocation.clearWatch(geolocID);
```