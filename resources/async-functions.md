# Asynchronous Functions

With normal (**synchronous**) functions it's easy enough to calculate a value and return that value for you to do something with elsewhere. For example, say you want to make a function that creates an element in the HTML DOM and then allows you to store that element in a variable. Since creating DOM elements doesn't require any asynchronous operations, that could look like:

```js
function myCreateElement(tag, id, classes) {
  // Create the element with the tag.
  const el = document.createElelement(tag);

  // Set the `id` attribute on the element.
  el.setAttribute('id', id);

  // Add all the classes to the element.
  for (const cls in classes) {
    el.classList.add(cls);
  }

  // Return the element to do other things with.
  return el;
}

// Now we can use the result of the function -- i.e. the
// return value -- in our code.
const mapDiv = myCreateElement('div', 'map', []);
const map = L.map(mapDiv, { maxZoom: 22 });
...
```

There are times, however, when you'll want to create a function that executes some **asynchronous** operation internally, and then allows you to do something with the result of that operation. Since an asynchronous operation will be passed to a background worker and the callback will be placed on the task queue for execution at some later time -- i.e., after your function exits -- you can't rely on a return value.

There are three common tools that you could use to make the result of an asynchronous operation available for later processing: **callback functions**, **promises**, or **custom events**. For example, let's say we want to find the user's position using the [`getCurrentPosition` function](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition) from the browser's Geolocation API. Let's see how we would do this with each tool.

## Callback Functions

Callback functions are the oldest way that JS developers have been dealing with asynchronous operations. Every browser back to the earliest ones that support JavaScript support callback functions. That's because, aside from the name, there's nothing special about callbacks: **callback functions are just functions**.

```js
// Here the findUsersPosition function accepts a `callback` as an
// argument. This callback should be a function that accepts a
// `GeolocationPosition` object as an argument (because that what
// the Geolocation API gives you):
//
// https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPosition
//
// When the browser finds the user's position, this function will
// call the onSuccess callback and pass the geolocation position along 
// to it.
function findUsersPosition(onSuccess, onFailure) {
  navigator.geolocation.getCurrentPosition(
    (pos) => { onSuccess(pos) },
    (err) => { onFailure(err) },
  );
}

let position = null;
findUsersPosition(pos => {
    position = pos;
  },
  err => {
    console.log(`Failed with error: ${err.message}`)
  });
```

## Promises

[Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) are a newer feature of JavaScript, but all modern browsers have robust support for them (NOTE: Internet Explorer is _not_ a modern browser). In fact, some newer browser APIs (like [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)) are implemented with promises.

```js
// Here, the findUsersPosition function creates a `Promise` object
// and returns it. When the browser finds the user's position, the 
// function will "resolve" the promise (i.e., call its `resolve`
// callback function). This callback should be a function that accepts
// a `GeolocationPosition` object as an argument (because that what
// the Geolocation API gives you):
//
// https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPosition
//
// When the browser finds the user's position, this function will
// call the callback and pass the geolocation position along to it.
function findUsersPosition() {
  const promise = new Promise((resolve, reject) => {
    navigator.geolocation.getCurrentPosition(
      (pos) => { resolve(pos) },
      (err) => { reject(err) },
    );
  });
  return promise
}

// There are two ways we can use a function that returns a promise. In
// the first way, we use the `then`/`catch` syntax. A `then` method on
// a promise gets called when the `resolve` function is called within
// the promise. The `catch` method on a promise gets called when the
// `reject` function is called within the promise.
let position = null;
findUsersPosition()
.then(pos => {    // <-- this is the resolve function
  position = pos;
})
.catch(err => {   // <-- this is the reject function
  console.log(`Failed with error: ${err.message}`)
});

// Alternatively, we can use the `async`/`await` syntax, which can be
// easier to read, but functionally does _exactly_ the same thing. If
// you use the `await` syntax inside of a function, your function must
// be declared as `async`.
let position = null;
try {
  const pos = await findUserPosition();  // The `await` returns whatever arguments the `resolve` callback was called with.
  position = pos;
} catch (err) {
  console.log(`Failed with error: ${err.message}`)
}
```

## Custom Events

Finally, custom events allow you even more flexibility for responding to asynchronous operations. They require a bit more set up, but allow you to separate the code where you call your function from the code where you do something with the function's result.

```js
// Here, findUsersPosition will will call getCurrentPosition, and
// when it returns, create a new custom event with a made up name
// called `geolocation-success`. The detail on this event will be
// the position returned from geolocating. This event will get
// dispatched on the global window object.
function findUsersPosition() {
  navigator.geolocation.getCurrentPosition(
    (pos) => {
      const evt = new CustomEvent('geolocation-success', { detail: pos });
      window.dispatchEvent(evt);
    },
    (err) => { console.log(`Failed with error: ${err.message}`) },
  );
}

// Here we listen to for any time the geolocation-success event is
// triggered on the window, whether it's triggered from our function
// or from somewhere else.
let position = null;
window.addEventListener('geolocation-success', evt => {
  position = evt.detail;
  console.log(evt.detail);
});

findUsersPosition();
```

## Summary

In summary, using custom events is often the most flexible option, but is also most difficult to manage. Alternatively, **callbacks** are easiest to use. However, for everywhere that callbacks are sufficient, **promises** are probably the right level of solution for most cases. One reason is because of a relatively new syntax that makes asyncrhonous operations using promises a little easier to work with: `async`/`await`. Using these keywords, we could rewrite the last few lines promises example. Instead of saying:

```js
let position = null;
findUsersPosition()
.then(pos => {
  position = pos;
});
```

We could say:

```js
let position = await findUsersPosition();
```