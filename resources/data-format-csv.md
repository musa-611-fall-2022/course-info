# CSV Data

JSON is not the only data format that you can work with in JavaScript, but other data formats will almost certainly require that you use a library to work with the data.

For CSV data, I would recommend the [Papa Parse](https://www.papaparse.com/) library. You can include Papa Parse in your app by adding the following script tag to your HTML:

```html
<script src="https://unpkg.com/papaparse@5.3.2/papaparse.min.js"></script>
```

Note that unpkg is just one of the CDNs where you can get Papa Parse. It's available from a number of them (like [cdnjs](https://cdnjs.com/), [JSDelivr](https://www.jsdelivr.com/), etc.).

## Loading data

Check the [Papa Parse documentation](https://www.papaparse.com/docs) for comprehensive set of things you can do with the library, but generally speaking, if I'm loading a CSV file that has a header row, I'll use a code snippet like:

```js
const csvURL = '...';

fetch(csvURL)
.then(resp => resp.text())
.then(text => {
  const data = Papa.parse(text, { header: true });
  console.log(data);
});
```