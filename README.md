# Learn-PHP

-------------------------------------------------------------------------------------------------------------------------------------------------
A. Introduction to PHP
------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------
1.How is PHP used in HTML?
---------------------------

PHP is often used to build dynamic web pages. A dynamic web page is one where each visitor to the website gets a customized page that can look different than how the site looks to another visitor. This is in contrast to static web pages which provide the same content to each visitor.


![alt text](https://content.codecademy.com/courses/introduction-to-php/php_static_dynamic.svg)

In order to create this dynamic behavior, PHP was designed to work closely with HTML. PHP can be used directly in-line with an HTML document. When the web site is delivered from the back-end to the front-end, the PHP content is executed and added to the HTML to form one HTML document. The start of in-line PHP is denoted with <?php and the end is denoted with ?>. 

As an example, consider the following code:

    <p>This HTML will get delivered as is</p>
    <?php echo "<p>But this code is interpreted by PHP and turned into HTML</p>";?>
    
In PHP, the echo keyword is used to output text. The text in this case is everything between the double quotes ("). An instruction written in PHP is called a statement. A semicolon (;) is required at the end of each statement in PHP.

So when the code above is executed, it outputs the text into the HTML file and the front-end will receive the following HTML document:

    <p>This HTML will get delivered as is</p>
    <p>But this code is interpreted by PHP and turned into HTML</p>
    
---------------
Example:
--------------

    Index.js
    
    <h1>My First PHP Site</h1>
    <p>This HTML will get delivered as is</p>
    <?php echo "<p>But this code is interpreted by PHP and turned into HTML</p>";?>
    <?php echo "<ul><li>You can use any HTML tags,</li><li>like this list.</li></ul>";?>
    <footer>
      <p>And this code is back in plain HTML</p>
    </footer>
    
    Output:
    
    /*My First PHP Site

    This HTML will get delivered as is

    But this code is interpreted by PHP and turned into HTML

        You can use any HTML tags,
        like this list.

    And this code is back in plain HTML/*
    
----------------------------
2.How is PHP Executed?
----------------------------

In the previous exercise, we explored how PHP can be sent from the back-end to the front-end where it is received as HTML to be displayed by a browser.

When writing a PHP script file, we still need to denote that we are beginning our PHP code using <?php, but the closing tag is no longer required. It is typically left out by convention.

For example, if the following code were placed in index.php:

    <?php
    echo "Hello, World!";

When the code above is run, "Hello, World!" will be output to the terminal.

Generally, PHP ignores whitespace (tabs, spaces, new lines), so this code yields the same result as the previous example:

    <?php
    echo     "Hello, World!";

You may be surprised that this code also works:

    <?php
    Echo "Hello, World!";

Unlike many other languages, PHP is not always case-sensitive, so Echo is a valid statement in PHP. However, it’s best practice to use standard casing – in this case, echo.

------------------------
3.PHP Comments
-----------------------

Sometimes, we want to include text in our files that we don’t want the computer to execute or display to the end user. We can do this with comments. Comments can be used to annotate our code to make it clearer to ourselves or others. They are also useful to prevent lines of code from being executed without deleting them.

In PHP, there are two main ways to add comments to our code. The first is single line comments. These are typically used for short explanations or points of clarification. Either # or // can be used to create a single line comment. Anything on the same line after these symbols is not executed by PHP.

For example:

    // I will always remember this
    echo "Hello world"; // My first PHP statement

    or

    # I will always remember this
    echo "Hello, World!"; # My first PHP statement

The second type of comment is a multi-line comment. This is used for longer descriptions, a more detailed guide on how to properly use the section of code, or to prevent several lines of code from being executed. These comments are started with /* and ended with */.

For example:

    /* "I've never thought of PHP as more 
    than a simple tool to solve problems."
    - Rasmus Lerdorf */
    echo "Hello, World!";
    
--------------------------------------------------------------------------------------------------------------------------------------------------------------
Quick Review A
--------------------------------------------------------------------------------------------------------------------------------------------------------------

-> Despite its age, PHP is still a commonly used technology in web development. 

-> PHP is designed to interact with HTML to generate dynamic websites.

-> Embedding PHP in HTML is done by placing PHP code between <?php and ?> tags.

-> Every statement in PHP must be terminated with a semicolon (;).

-> PHP files have a .php extension and the file always starts with the opening PHP tag <?php. The closing tag is implied and left out by convention.

-> Whitespace is generally ignored when executing PHP code.

-> Keywords are not case sensitive in PHP. As a convention, use the standard casing.

-> Single line comments are made in PHP using # or //. Multi-line comments are placed between /* and */.

---------------------------------
B.PHP Strings and Variables
---------------------------------

----------------------
1.Strings
---------------------

![alt text](https://content.codecademy.com/courses/php-strings-variables/PHP_m2l1e1.svg)

In everyday conversation, we use the word data to refer to any sort of information. This information is often a list of numbers, like a company’s monthly expenses or statistics about an athlete’s performance. However, in programming, data means something very specific. It’s still information, but that information takes the form of a few specific types.

The PHP language has different ways of handling different types of data. Which actions the computer can perform and how the computer stores the data in memory will vary based on the type. In this lesson, we’ll be learning about the string data type.

    echo "My first string"; // Prints: My first string
    
----------------------
2.Escape Sequences
----------------------

We use quotation marks to indicate the start and end of a string. The quotation marks tell the computer that we want everything inside them to be treated as a single piece of data. But how do we include quotation marks inside a string?

Consider the following string: "She said "hi" to the dog."

In the code above, the quotes around “hi” are intended to be part of the string, but the computer will actually see two strings "She said " and " to the dog." with hi in between. Since hi won’t be recognized as valid PHP it will result in an error:

    echo "She said "hi" to the dog."; //syntax error, unexpected 'hi' (T_STRING)
    
In order to indicate which quotation marks the computer should view as instructions vs which it should view as simply characters, PHP allows for escape sequences. An escape sequence usually consists of a backslash (\) immediately followed by another character. 

     echo "She said \"hi\" to the dog."; // Prints: She said "hi" to the dog.
       
Quotation marks aren’t the only symbol requiring an escape sequence. When we print multiple strings, PHP will print them to the same line by default: 

    echo "1. Go to gym";
    echo "2. Cook dinner"; 
    
You don’t need to worry about other escape sequences yet, but if you’d like to see the full list you can find one in the http://php.net/manual/en/language.types.string.php#language.types.string.syntax.double
    
----------------------------
3.String Concatenation
----------------------------

It can be useful to combine two strings together. This process is called string concatenation, and we can use the concatenation operator (.) to do this. 

An operator is a character that performs a task in our code. The computer will take the string to the left of the concatenation operator, combine it with the string to the right, and return the resulting single string. Let’s see an example of string concatenation:

    echo "one" . "two"; // Prints: onetwo

Notice how the string “onetwo” was printed. The computer won’t make any assumptions for us—it will combine the strings exactly as they are without adding any spaces or line-breaks. If we want spaces, we’ll have to add any spaces we want ourselves. Here we added a space to the string "one ":

    echo "one " . "two"; // Prints: one two

We can also combine, or chain, our operations to get a final result:
    
    echo "one" . " " . "two" . " " . "three"; // Prints: one two three

The concatenation operator takes two strings (the operands) and produces a string as a result (the return value). As we delve deeper into PHP, we’ll learn about other kinds of operators. Most will take one or two operands, but there’s even one that takes three.

-------------------
4.Variables
-------------------

Let’s say I have a really long string in my program, and I’m going to need to use it multiple times. Do I have to type the string out every time I need to use it? The answer is “no”. Variables are a fundamental programming concept designed to address this concern. With variables, we store values so that we can easily reuse them throughout a program. 

![alt text](https://content.codecademy.com/courses/php-strings-variables/PHP_m2l1e4m.svg)

Before we can use variables in our code, we need to declare and assign them.

Declaring a variable is the process of reserving a word, the variable name, which we’ll be able to refer to in our code. It’s good practice to name the variable in a way that describes the data it holds.

Assignment is the process of associating that variable name with a specific value so that everytime we use the variable’s name the computer will grab that value. 

![alt text](https://content.codecademy.com/courses/php-strings-variables/PHP_m2l1e4n.gif)

-----------------------
5.Creating Variables
-----------------------

Let’s look at an example of creating a variable:

    $my_name = "Aisle Nevertell";
    
In the code above, we’re actually doing two things with a single statement: we’re declaring a new variable by giving it the name my_name. We’re also assigning it the value "Aisle Nevertell". The variable $my_name now holds the value "Aisle Nevertell".

To declare a variable we use the dollar sign character ($) followed by our chosen variable name. The dollar sign is known as a sigil; it’s a character that allows the computer to see quickly that something is a variable.

To assign it a value we use another operator: the assignment operator (=) followed by the value we’re assigning to the variable.

Though it can occasionally be useful to separate these actions, we’ll most often be declaring and assigning variables at the same time. 

![alt text](https://content.codecademy.com/courses/php-strings-variables/PHP_m2l1e5.svg)

In PHP, variables names can contain numbers, letters, and underscores (_), but they have to start with either a letter or an underscore. Variable names are case sensitive, meaning that PHP will treat the variables $my_example and $My_example as two different variables.

    ⚠️Snake case:
    
    One common convention when naming PHP variables is to use an underscore between words on variable names with more than one word in their name. This is known as snake case:
    
    $mood = ":)";
    $favorite_food = "Red curry with eggplant";
    
-----------------------
6.Using Variables
------------------------

Once we’ve declared a variable and assigned a value to it, we can use it as many times as we want. We refer to a variable by using the dollar sign followed by the variable’s name.

    $favorite_food = "Red curry with eggplant, green beans, and peanuts";
    echo $favorite_food; 
    // Prints: Red curry with eggplant, green beans, and peanuts
    
Except during assignment, whenever the computer sees a variable in your code, it replaces the variable with the value assigned to that variable.

    $dog_name = "Tadpole";
    echo $dog_name; 
    // Prints: Tadpole
    
Since the computer treats a variable just as if it were the value it holds, this means we can do operations on variables just as we would with any value of that type.

    $dog_name = "Tadpole";
    echo "My dog is named " . $dog_name; 
    // Prints: My dog is named Tadpole
    
-------------------
7.Variable Parsing
--------------------

In the last exercise, we saw how concatenating a number of strings and string variables got annoying. There’s an easier way!

PHP strings allow us to place variables directly into double quoted strings. These variables will be parsed which means the computer will read the variables as the value they hold rather than see them as just a sequence of characters.

    $dog_name = "Tadpole";
    $favorite_food = "salmon";
    $color = "brown";
 
    echo "I have a $color dog named $dog_name and her favorite food is $favorite_food.";
    // Prints: I have a brown dog named Tadpole and her favorite food is salmon.

PHP string parsing is incredibly useful. Whenever PHP sees a dollar sign ($) inside a string it will assume all the characters next to it (until it reaches a character that couldn’t be included in a variable name) are a part of the variable name.

Sometimes this can get complicated. Consider the following example:

    $toy = "frisbee";
    echo "Alex likes playing with $toys";

The code above will cause an error. Why? The computer was looking for a variable $toys and couldn’t find one.

Fear not! PHP allows us to specifically indicate the variable name by wrapping it in curly braces to avoid any confusion. We’ll include the dollar sign followed by the variable name wrapped in curly braces:

    $dog_name = "Tadpole";
    $favorite_food = "treat";
    $color = "brown";
 
    echo "I have a ${color}ish dog named $dog_name and her favorite food is ${favorite_food}s.";
    // Prints: I have a brownish dog named Tadpole and her favorite food is treats.

-------------------------
8.Variable Reassignment
-------------------------

The word variable comes from the latin variāre which means “to make changeable.” This is an apt name because the value assigned to a variable can change.

The process of assigning a new value to a variable is called reassignment. We reassign a variable using the assignment operator on a variable that’s already been declared:

![Variable reassignment](https://content.codecademy.com/courses/php-strings-variables/PHPVariable_m2l1e8.gif)

    $favorite_food = "Red curry with eggplant";
    echo $favorite_food; // Prints: Red curry with eggplant

    // Reassign the value of $favorite_food to a new string
    $favorite_food = "Pizza"; 
    echo $favorite_food; // Prints: Pizza

It’s often useful to create new variables assigned to the same value as an existing variable:

    $first_player_rank = "Beginner";
    $second_player_rank = $first_player_rank; 

In the code above, we declared the variable $first_player_rank and assigned to it the string "Beginner". Next, we declared $second_player_rank and assigned it to $first_player_rank.

This created a new variable ($second_player_rank) assigned the value "Beginner". Notice how variables can be treated different depending on where they appear in code. During variable assignment or reassignment, the variable on the left of the assignment operator is treated as a variable (named storage for holding a value) while a variable on the right of the operator is treated as the value it stores. 

-----------------------------------
9.Concatenating Assignment Operator
-----------------------------------

We can assign and reassign variables to the values that result from operations:

    $full_name = "Aisle" . " Nevertell";
    echo $full_name; // Prints: Aisle Nevertell

During assignment, the computer will first evaluate everything to the right of the assignment operator and return a single value.

In the code above, the computer will concatenate the strings "Aisle" and " Nevertell" into the value "Aisle Nevertell". It will then assign this string as the value to the $full_name variable.

This is true even for more complex operations:

    $full_name = "Aisle" . " " . "Nevertell" . " " . "Nomaderwat";
    echo $full_name; // Prints: Aisle Nevertell Nomaderwat

One theme you may notice as you learn a programming language’s syntax is that common actions that programmers need to do a lot often have a shortcut. Consider the following:

    $full_name = "Aisle";
    $full_name = $full_name . " Nevertell";
    echo $full_name; // Prints: Aisle Nevertell

In the code above, we have the variable $full_name assigned the value "Aisle". We want to reassign $full_name to its current value appended with the string " Nevertell".

Believe it or not, this is such a common task that PHP offers a shorthand notation, the concatenating assignment operator (.=). Let’s compare the same action but using this alternate operator:

    $full_name = "Aisle";
    $full_name .= " Nevertell";
    echo $full_name; // Prints: Aisle Nevertell

It may seem funny to provide a shortcut to save just a few characters of typing, but when operations are performed often enough, those keystrokes can really add up. This syntax is also faster and easier to read which makes code easier to maintain.

One important thing to note is that even though PHP is often flexible about whitespace, it is inflexible with the concatenating assignment operator—the . and = characters must not have any spaces or other whitespace characters between them. 

-------------------------
10.Assign by Reference
-------------------------

When we create a variable assigned to another variable, the computer finds a new space in memory which it associates with the left operand, and it stores a copy of the right operand’s value there. 

![Assign by reference](https://content.codecademy.com/courses/php-strings-variables/PHPVariable_4_v3.gif)

This new variable holds a copy of the value held by the original variable, but it’s an independent entity; changes made to either variable won’t affect the other:

    $first_player_rank = "Beginner"; 
    $second_player_rank = $first_player_rank; 
    echo $second_player_rank; // Prints: Beginner

    $first_player_rank = "Intermediate"; // Reassign the value of $first_player_rank
    echo $second_player_rank; // Still Prints: Beginner

![Alt text](https://content.codecademy.com/courses/php-strings-variables/PHPVariable_5_v3.gif)

We use a different operator for this—the reference assignment operator (=&).

When we assign by reference we’re saying that the variable on the left of the operator should point, or refer, to the exact same data as the variable on the right. With assignment by reference, changes made to one variable will affect the other:

    $first_player_rank = "Beginner";
    $second_player_rank =& $first_player_rank; 
    echo $second_player_rank; // Prints: Beginner

    $first_player_rank = "Intermediate"; // Reassign the value of $first_player_rank
    echo $second_player_rank; // Prints: Intermediate
    
    
--------------------------
Quick Review B
--------------------------

Awesome work! We’ve covered a lot of material in this lesson, so let’s review:

-> Strings are collections of text that the computer treats as a single piece of data.

-> A string can be any length and contain any letters, numbers, symbols, or spaces surrounded by quotation marks.

-> In order to include certain characters inside strings we have to use escape sequences.

-> An operator is a character that performs a task in our code.

-> We can use the concatenation operator (.) to combine two strings into one.

-> Variables are a fundamental programming concept which allow us to easily reuse data in our code.

-> We declare a variable using the dollar sign ($) followed by the variable name and then use the assignment operator (=) to give it a value.

-> PHP has variable parsing which allows us to include variables directly in our strings.

-> Once a variable has been assigned, we can change its value. This is called reassignment.

-> We can create an alias for a variable, instead of just a copy, using the reference assignment operator (=&).

-> Operations to the right of the assignment operator will be evaluated before assignment takes place.

-> The concatenating assignment operator (.=) is a shorthand notation for reassigning a string variable to its current value appended with another string value.

------------------------------------------------------
C.Numbers in PHP
----------------------------------------------------

----------------------------
1.Numbers
---------------------------

Numbers and arithmetic operations are a fundamental part of programming. In this lesson, we’ll learn how to use and manipulate numbers in PHP.

PHP has two number data types. The integer data type includes positive and negative whole numbers (such as 3, 4599, -98, and 0). The floating point data type is used to represent decimal numbers (such as 4.98273, 2.1, -9.7, -182736.8).

    echo 5; // Prints: 5
    echo -22.8; // Prints: -22.8

We can also declare variables and assign numbers as their values:

    $my_int = 78;
    $my_float = -897.21;

    echo $my_int; // Prints: 78
    echo $my_float; // Prints: -897.21

In the code above, we created the $my_int variable and assigned the integer value of 78 to it. Next, we created the $my_float variable and assigned the floating point value of -897.21 to it.

----------------------------
2.Addition and Subtraction
--------------------------------
PHP provides several operators we can use on numbers. Let’s start with two that are likely familiar: the addition (+) and subtraction (-) operators:

    echo 5 + 1; // Prints: 6
    echo 6.6 + 1.2; // Prints: 7.8
    echo 198263 - 263;  // Prints: 198000
    echo -22.8 - 19.1; // Prints: -41.9

Most of the time, we don’t have to worry about which type of number we’re using. We can add a float to an integer, subtract an integer from a float, and so on.

One quirk is that operators will return integers whenever the result of the operation evaluates to a whole number. So 8.9 + 1.1 will return 10, an integer, and not 10.0 even though both of the operands in the calculation were floating point numbers. 

---------------------------
3.Using Number Variables
---------------------------

We can use number operators on variables that hold number values:

    $tadpole_age = 7;
    $lily_age = 6; 
    $age_difference = $tadpole_age - $lily_age;
    echo $age_difference; // Prints 1

Let’s look at another example of performing operations with number variables:

    $favorite_num = 22;
    echo $favorite_num + 1; // Prints 23
    echo $favorite_num; //Prints 22

In the code above, we created the variable $favorite_num then we used echo to print that value plus 1. Note that we didn’t reassign the value of the $favorite_num variable, so it still had the value 22 when we printed it on the last line.

We reassign number variables using the assignment operator:

    $age = 82;
    echo $age; // Prints: 82

    $age = $age + 2;
    echo $age; // Prints: 84


------------------------------
4.Multiplication and Division
-------------------------------

PHP also gives us operators for performing multiplication (*) and division (/).

    echo 2 * 3; // Prints: 6
    echo -21 / 7; // Prints: -3

Like with addition and subtraction, when we perform multiplication or division, the computer will return an integer whenever the operation evaluates to a whole number.

The reverse is also true:

    $num_cookies = 24;
    $num_friends = 7;
    $cookies_per_friend = $num_cookies / $num_friends;
    echo $cookies_per_friend; // Prints: 3.4285714285714

In the code above, we performed an operation on two integers that didn’t divide into each other evenly, so the computer returned a floating point number. 

-----------------------
5.Exponentiation
---------------------

PHP give us an operator for raising a number to the power of another number: the exponentiation operator (**).

For example, we can square a number by raising it to the power of 2:

    echo 4 ** 2; // Prints: 16

We can also use this operator on floats and negative numbers:

    echo 2.89 ** 3.2;  // Prints: 29.845104015297
    echo 10 ** -1; // Prints: 0.1

For PHP to interpret this operator correctly it can’t have any spaces between the two * characters:

    echo 2 * * 3; // Will result in an error
    
----------------------------
6.Modulo
----------------------------

PHP also provides an operator that might be less familiar: modulo (%). The modulo operator returns the remainder after the left operand is divided by the right operand.

    echo 7 % 3; // Prints: 1

In the code above, 7 % 3 returns 1. Why? We’re trying to fit 3 into 7 as many times as we can. 3 fits into 7 at most twice. What’s left over—the remainder—is 1, since 7 minus 6 is 1.

![alt text](https://content.codecademy.com/courses/php-strings-variables/PHP_m2l2.gif)

The modulo operator will convert its operands to integers before performing the operation. This means 7.9 % 3.8 will perform the same calculation as 7 % 3—both operations will return 1.

Let’s look at another example of the modulo operator in action:

    $num_cookies = 27;
    $cookies_per_serving = 4;
    $leftover_cookies = $num_cookies % $cookies_per_serving;
    echo $leftover_cookies; // Prints: 3
    
------------------------------
7.Order of Operations
--------------------------------

We can chain multiple operations together to get a single result:

    echo 2 + 3 + 4 + 5 - 1.1; // Prints: 12.9
    echo 2 * 9 / 6; // Prints: 3

You might have learned about operations having an order of precedence in a math class. This means that operations in a chain aren’t simply performed from left to right; rather each operator is given a special rank.

Operations will be evaluated in the following order:

    -> Any operation wrapped in parentheses (())
    -> Exponents (**)
    -> Multiplication (*) and division (/)
    -> Addition (+) and subtraction (-).

The acronym PEMDAS can be helpful for remembering the order of precedence for these arithmetic operations.

    echo 1 + 3 * 9; // Prints: 28

In the example above, 3 * 9 (27) is calculated first and then is added to 1 to yield a final result of 28. We can change what this expression returns by using parentheses:

    echo (1 + 3) * 9; // Prints: 36

Here, 1 + 3 (4) is calculated first and then that value is multiplied by 9 to which returns 36. 

------------------------------
8.Mathematical Assignment Operators
-------------------------------------

This is such a common task that PHP provides a shorter syntax using arithmetic assignment operators:

    Operation: 	Long Syntax: 	Short Syntax:
    Add 	    $x = $x + $y 	$x += $y
    Subtract 	$x = $x - $y 	$x -= $y
    Multiply 	$x = $x * $y 	$x *= $y
    Divide 	    $x = $x / $y 	$x /= $y
    Mod 	    $x = $x % $y 	$x %= $y

    $savings = 800;
    $bike_cost = 75;
    $savings -= $bike_cost;
    echo $savings; // Prints: 725

With mathematical assignment operators, PHP doesn’t allow spaces between the two characters. 

Ready for one more shortcut? Increment operators allow us to subtract or add one to a number with just two characters.

    $age = 89; 
    $age++;
    echo $age; // Prints: 90

    $days_til_vacation = 7; 
    $days_til_vacation--;
    echo $days_til_vacation; // Prints: 6

In the code above, we used the post-increment (++) operator to add one to $age and we used the post-decrement operator (--) to subtract one from $days_til_vacation. 


