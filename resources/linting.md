# Linting

A "linter" is a program that checks whether some code conforms to some set of style rules. Usually the style rules have to do with specific choices around syntax, formatting (e.g., indentation, spacing around symbols), and language constructs (e.g. what types of loops are used or how variables are defined).

While linters will usually catch when code won't work at all (i.e. when there is invalid syntax) they will often flag problems in code that technically works. **_At this point, it's reasonable for you to ask "but if code works, then how can it be wrong?"_**

The job of a linter is not to check whether your code will run (and certainly not to check whether your code will do what you intend for it to do). Instead, **the job of a linter is to encourage you to use a coding style that will:**
* **minimize the chances of introducing unintended errors**
* **maximize the chances of writing efficient code**
* **be consistent and readable, because readability is important** (maybe not for computers, but certainly for humans!)

Remember that **a set of linter rules is an opinion about how code should be written**; it is not hard and fast rules about a programming language itself. There are a number of popular rule sets for linting JavaScript. In this class we're using a custom set on top of ES Lint's recommended set.

## Recommended reading
* Compare the Top 3 Style Guides and Set Them Up With ESLint - https://betterprogramming.pub/comparing-the-top-three-style-guides-and-setting-them-up-with-eslint-98ea0d2fc5b7