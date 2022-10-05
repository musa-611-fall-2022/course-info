# CSS Structure & Layout

First, some general concepts:
* As far as CSS is concerned, every HTML element that shows up on the page is a box (a rectangle).
* When thinking of a page layout, it's helpful to break the page into components. Every element has it's own internal layout, so instead of worrying how to get every individual element on the page to where you want it to go, instead think of how to arrange a group of elements together into a rectangle. Then you can treat that entire rectangle as a unit to be arranged on the page.

There are _a ton_ of important CSS attributes, but for the purposes of layout, there's one that rules them all: the `display` attribute. Specifically, the values of the `display` attribute that I recommend you understand are (in this order):
* [`inline`](https://css-tricks.com/almanac/properties/d/display/#aa-display-inline)
* [`block`](https://css-tricks.com/almanac/properties/d/display/#aa-display-block)
* [`inline-block`](https://css-tricks.com/almanac/properties/d/display/#aa-display-inline-block)
* [`flex`](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-examples)

Other attributes that are important to layouts within an element or on the page overall:
* [`margin`/`padding`/`border`](https://css-tricks.com/the-css-box-model/)/[`box-sizing`](https://css-tricks.com/box-sizing/)
* [`position`](https://css-tricks.com/almanac/properties/p/position/)

## Recommended exercises
* Flexbox Froggy: https://flexboxfroggy.com/
* CSS Grid Garden: https://cssgridgarden.com/

## Helpful references
* The CSS `display` attribute: https://css-tricks.com/almanac/properties/d/display/
* CSS Attribute Ordering: https://9elements.com/css-rule-order/
* Flexbox Reference: https://css-tricks.com/snippets/css/a-guide-to-flexbox/

## Other resources
* CSS Element Templates: https://csslayout.io/
* CSS Layout Tips: https://web.dev/one-line-layouts/
