# Functions

Functions wrap up some specific set of statements so that you can run them on demand. A function may return a value, but it does not have to.

Sometimes you define functions so that you **copy and paste less code**. Sometimes you define functions so that **your code is more readable**.

There are several ways to define functions:

1.  Traditional syntax, which always starts with the keyword `function` followed by the name of your function, and a set of arguments in parenthesis (the set can be empty). The function body is wrapped in curly braces.

    ```js
    function (a, b) {
      return a + b;
    }
    ```

2.  Arrow syntax, which can be a more compact way to define a function. Arrow functions can be long with multiple statements, or short with a single `return` statement.

    ```js
    (a, b) => {
      return a + b;
    }
    ```

    With arrow syntax, if your function only consists of a single `return` statement, you don't need to include any curly braces or the `return` keyword, so the following is equivalent to above:

    ```js
    (a, b) => a + b;
    ```

3.  Both of the above are unnamed, or "anonymous" functions. We often want to give functions names so that we can actually use them after we define them. For example:

    ```js
    function add1(a, b) { return a + b; }

    const add2 = (a, b) => { return a + b; }

    const add3 = (a, b) => a + b;
    ```

    All of the above functions (`add1`, `add2`, and `add3`) do the same thing. If we say:

    ```js
    let x = add1(4, 5);
    ```

    Then `x` will equal `9`.
