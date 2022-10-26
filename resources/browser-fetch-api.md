## Fetch API

The fetch API provides a way to fetch data from HTTP requests using JavaScript in the browser. It mainly consists of the `fetch` function.

The `fetch` function takes a URL and some options as arguments. The options allow you to control other aspects of the request.

The `fetch` function returns a promise that calls the resolve function with a [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response) object. There are functions such as `json()`, `text()`, and `formData()` on that `Response` object parse the response content in different ways and return another promise with the parsed content.

For example, for reading JSON from a URL this usually looks like:

```js
fetch('https://...')
.then(resp => resp.json()) // <-- Parse the response as JSON
.then(data => {
  // The data is a JSON object.
  ...
});
```

For reading text contnent from a URL this usually looks like:

```js
fetch('https://...')
.then(resp => resp.text()) // <-- Parse the response as text
.then(data => {
  // The data is a string.
  ...
});
```