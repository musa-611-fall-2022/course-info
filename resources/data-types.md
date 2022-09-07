# Data Types

Data types specify the type of data that you work with in a program. It's important to pay attention to what type of data is stored in the variables you're working with, as working with the wrong data types may result in unintended consequences.

For example, let's say it's 2004 and we are working with the planets in the solar system.

```js
let numPlanets = '9';

/*
  In 2005, astronomer Mike Brown and his team announced the discovery of 2003
  UB_313 (later named Eris after the Greek goddess of discord and strife), a
  trans-Neptunian object then thought to be just barely larger than Pluto.
  Soon afterwards, a NASA Jet Propulsion Laboratory press release described
  the object as the "tenth planet".

  So, now it's 2006 and we have to update our data:
*/

numPlanets = numPlanets + 1;

/*
  So, how many planets does our program think there are?
*/

console.log(numPlanets);
```

What happens when you run the code above? How can you fix it?

Refer to the refereneces below for more information, but a quick note about a couple weird things in JavaScript to watch out for:
* When checking for equality between two values you can technically use two equals signs (`==`) or three equals signs (`===`). However, I recommend you always use three equals signs unless you're trying to do something really special. To get a sense for why, in your JavaScript console, try to see what the following two statements return:
  ```js
  '9' == 9;
  ```
  ```js
  '9' === 9;
  ```
* Non-values (which is a term that I just made up) are weird in JavaScript. In JavaScript there are two values that people will often check for: `null` and `undefined`. The first (`null`) is a variable that is defined but is missing a value, while the second (`undefined`) is a variable that refers to something that doesn't exist, and the variable isn't defined to be anything. Over time you'll have a better sense of when to use one or the other, but just note that they are not strictly equal to each other (in a three-equal-sign sense).

## References

- JavaScript Data Types and Data Structures | MDN
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures