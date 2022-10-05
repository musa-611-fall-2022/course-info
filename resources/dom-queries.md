# Document Object Model (DOM) Queries

The **Document Object Model (DOM)** is a name for the way that browsers represent the structure of your web page once it loads your HTML file (document) into memory. It is literally the way that the browser models objects that represent elements in your document.

We can take advantage of the fact that the browser has a representation of your elements to store those elements in variables just like we would any other value.

## Getting Elements Using Basic Attributes

You have several options for getting elements from a document. The first set of options are tailor-made for a few specific types of element attributes.

Let's say you have the following HTML code:

```html
<div id="my-school-map" class="my-map-class"></div>     <!-- #1 -->
<div id="my-park-map" class="my-map-class"></div>       <!-- #2 -->
<div id="my-income-chart" class="my-chart-class"></div> <!-- #3 -->
```

The following are a few options for accessing these elements:

```js
document.getElementById('my-school-map'); // Returns element #1
document.getElementsByClassName('my-map-class'); // Returns elements #1 & #2
document.getElementsByTagName('div'); // Returns elements #1, #2, & #3
```

Note that the `getElementsByClassName` and `getElementsByTagName` functions are
_always_ plural, as opposed to `getElementById`; an element's `id` attribute is
intended to be unique, where as an element's `class` is intended to not be, and of course there can be multiple elements on a page for any tag.

## Getting Elements Using CSS Selector Syntax

Selectors were originally developed as part of the **Cascading Style Sheets (CSS)**
language to identify which elements to style on a page. Over time, developers
found that they were also useful as a syntax for specifying elements for other
purposes besides styling as well.

> **[CSS Selector Resources](css-selectors.md)**
>
> **If you're not well-versed in CSS selectors, I highly recommend using the CSS Selectors resource in this repository as a reference: [css-selectors.md](css-selectors.md).**

### Using the `querySelector`[`All`] Functions

As you can see, CSS selectors are a fairly flexible syntax for _querying_ the
document for a set of elements. The `querySelector` and `querySelectorAll`
functions use CSS selector syntax to identify and return elements using this
selector syntax.

* Benefits of `querySelector`[`All`]:
  * One general-purpose function instead of three separate ones
  * Once you're comfortable with CSS selectors, you can get very specific about
    which elements you want to select using a flexible query language.

* Drawbacks of `querySelector`[`All`]:
  * Relatively slow (compared to the `getElement[s]ByXxx` functions). However,
    the speed difference usually doesn't matter; "relatively slow" is still
    really fast by human standards.

Let's revisit the HTML from above:

```html
<div id="my-school-map" class="my-map-class"></div>     <!-- #1 -->
<div id="my-park-map" class="my-map-class"></div>       <!-- #2 -->
<div id="my-income-chart" class="my-chart-class"></div> <!-- #3 -->
```

* Using `querySelector`

  ```js
  document.querySelector('#my-school-map'); // Returns element #1
  document.querySelector('.my-map-class'); // Returns element #1
  document.querySelector('div'); // Returns element #1
  ```

  Note that even when the selector provided would match many elements, the
  `querySelector` function will only return the _first_ matched element (or
  `null` if none are found). It is not a typo that all three of those statements
  return element #1.

* Using `querySelectorAll`

  ```js
  document.querySelectorAll('#my-school-map'); // Returns element #1
  document.querySelectorAll('.my-map-class'); // Returns elements #1 & #2
  document.querySelectorAll('div'); // Returns elements #1, #2, & #3
  ```

  Note that even when the selector provided would match only one element, the
  `querySelectorAll` function will essentially return an array of that one
  element object. This differs from `querySelector` which will only ever return
  an element object (or `null`). In other words:

  ```js
  document.querySelectorAll('div')[0] === document.querySelector('div');
  ```