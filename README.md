# PHP
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
