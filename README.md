# PHP
* Basic Coding Standards [PSR-1](https://www.php-fig.org/psr/psr-1/)
  * Class names MUST be declared in `StudlyCaps`.
  * Class constants MUST be declared in all UPPER case with underscore( `_` ) separators.
  * Method names MUST be declared in `camelCase`.
  * Functions and its variables should use `$under_score` naming convention.
  * Namespaces and classes MUST follow an **autoloading** [PSR-4](https://www.php-fig.org/psr/psr-4/)
  * Files should not cause [side-effects](https://www.php-fig.org/psr/psr-1/#23-side-effects)
* Maintaining proper documentation of your code: Write meaningful comments wherever possible. This will help your peers tremendously in understanding and carrying forward the work.
* Avoid short tags `<%` or `<?`; use `<?php`. Former can result in ambiguity with XML parsers and can cause conflict with future versions of PHP
* Use **meaningful variable and function names** in your code
* Code Formatting: Try to keep an indent of`4 spaces`. **Never use Tab** as different computers can have different Tab settings.
* Single Quoted vs. Doubles Quoted Strings:
You have to understand the difference between the single quoted strings and the double quoted ones. **If you just have a simple string to display, then always go for single quotes.**
But if you are going to have variables and special characters like `\n` or `\t` in your string, then you must use double quotes which will get your string parsed by the PHP interpreter and will take more execution time than single quoted strings.
So, try to understand the difference in their working nature and use them appropriately, whenever necessary.
* Never Use Functions inside Loops:
  * Bad Practice:
    ```
    for ($i  = 0, $i <= count($array);  $i++)
    {
    //statements
    }
    ```
  * Good Practice:
    ```
    $count = count($array);
    for ($i = 0; $i < $count;  $i++)
    {
    //statements
    }
    ```
  If you take the burden of storing the value returned by the function in a separate variable before the loop, then you would be saving enough execution time as in the first case the function will be called and executed every time the loop runs which can increase the time complexity of the program for large loops.
* Using Single Quotes around Array Indexes:
There is a difference between `$array['quotes']` and `$array[quotes]` and you have to understand this difference properly.
A feature of PHP is that, it considers unquoted strings used as array indexes as constants, and if the constant have not been defined before, then it will be “self-defined” and a warning will be raised. This will not stop your code from working, but the bug will remain in the code.
* Understanding Strings in a Better Way:
Take the code snippet as an example and try to guess which statement will run the fastest and which one the slowest.
  ```
  $a = ‘PHP’;

  print “This is my first $a program.”;

  echo “This is my first $a program.”;

  echo “This is my first “.$a.” program.”;

  echo “This is my first ”,$a,” program.”;
  ```
  Guess what, the last and the most uncommon statement of all wins the speed test. The first one obviously loses as the “print” statement is slower than “echo” statement.  The third statement wins over the second one as it uses concatenation operation rather than using the variables inline. The lesser-known last statement wins as there are no string operations being performed and is nothing other than a list of comma-separated strings.
* DRY Approach: Acronyn for "Don't Repeat yourself". Repeating yourself in the code is usually considered bad practices. There several practices followed to dry your code like using variables when certain value is repeated, code reuse, breaking your function into smaller and reusable component etc. [Wikipedia](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself#:~:text=The%20DRY%20principle%20is%20stated,their%20book%20The%20Pragmatic%20Programmer)
* Try to Prevent Deep Nesting
Try to prevent deep nesting levels in your code, as much as possible. It can make things really difficult for you when you need to debug your code and can take the heck out of people who will try to review your code. Try to use conditions as logically as possible to avoid unnecessary deep nesting. It is not only a very poor programming practice, but also can make your code look ugly enough to your fellow developers.
* Aunthetication: Always authenticate the oncoming Server request.

# Javascript/jQuery
* Naming conventions
  * prefix `$` symbol before **jQuery** varibles e.g. `$li = jQuery('#some_list')` to distinguish it from vanilla JS variables e.g. `var li = document.getElementById('some-list')`
  * use easy, short and readable variable and function names
  * Function, Variable names should use `camelCase`
  * Class names should use `StudlyCase`
  * Constants must be defined using `UPPER_CASE`
* Best practices followed in Javascript is well expounded [here](https://www.w3.org/wiki/JavaScript_best_practices)
* Lazy load scripts when needed.. Browsers run JavaScript before creating the DOM tree and painting the pixels on the screen, because scripts can add new elements to the page or change the layout or style of some DOM nodes. So, by giving the browser less scripts to execute during page load, we can reduce the time it takes for the final DOM tree creation and painting, after which the user will be able to see the page. Use our custom function: `Drupal.settings.static_files.load`
* DRY; Use jQuery chaining and avoid as much as possible DOM traversal by storing already traversed data.
* Avoid unnecessary AJAX request by doing client-side validation as much as possible beforehand
* Use proper HTTP response codes. [Reference](https://www.restapitutorial.com/httpstatuscodes.html)

# HTML5
* Use `data-*` attributes for storing data that requires any processing via JS
* Use `id`/`class` if it requires processing via JS for quicker DOM access
* Naming conventions:
  * data-*: use hyphen (`-`) spearated strings e.g. `data-body-temp="48"`
  * class: use hyphen (`-`) spearated strings e.g. `class="table-row"`
  * id: use  underscore (`_`) spearated strings e.g. `id="quality_metrics_table"`

# CSS3
* Use `id`/`class` if it requires processing via CSS for quicker DOM access
* Use pre-defined CSS classed in your theme or custom-written as much as possible to keep your CSS files less busy and easy maintainance
* DRY; break your CSS into smaller styling classes and re-use it wherever possible; for e.g., `.right`, `.left`, `red-text` etc are just examples of DRY where CSSs, which are heavily used, are alredy defined by a class; Just use the class or multiple classes and you are good to go!
* `rem`s and `em`s vs. `px`:
There's always been a strong debate as to whether it's better to use pixels (`px`) or ems and rems when defining font sizes. Pixels are a more static way to define font sizes, and `em`s are more scalable with different browser sizes and mobile devices. With the advent of many different types of web browsing (laptop, mobile, etc.), `em`s and `rem`s are increasingly becoming the default for font size measurements as they allow the greatest form of flexibility.
* Try to Use Flexbox and Grid Layout Instead of Floats:
In the past, it was very common and necessary to use floats to create any kind of layout. Unfortunately, floats come with a lot of problems. You can instead start using the much more powerful layout modules called flexbox and grid layout. Flexbox will help you create one-dimensional layouts, and grid will help you with two-dimensional layouts.
* Use `!important` sparingly
The keyword !important is used to bypass any styling rules specified elsewhere for an element. This allows you to use less specific selectors to change the appearance of an element. As a beginner, this might seem like an easy way to style elements without worrying about what selectors you should be using. However, you should avoid that because using !important with a lot of elements will ultimately result in !important losing its meaning, as every CSS rule will now bypass the selector specificity.
 One possible use for !important is to specify the style of third-party elements added to a webpage where you cannot alter the original stylesheet, its loading order, etc.
