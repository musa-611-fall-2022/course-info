# Objects

An object is a little bundle of data and functionality. Basically everything in JavaScript, with the exception of `null` and `undefined` is effectively an object.

For example, in the following code, `numPlanets` is a number, but also an object:

```js
const numPlanets = 9;
```

Since it's an object, it has some data (`9`) as well as some behavior attached to it. So we could say things like:

```js
numPlanets.toString();
```

Each type of object has different behaviors (in the form of functions) attached. Here are [all the functions attached to numbers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#instance_methods) in JavaScript.