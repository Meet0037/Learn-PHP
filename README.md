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


------------------------------------------------------------------------------------------------
C.Introduction to PHP Functions
------------------------------------------------------------------------------------------------

We can think of programs as series of instructions to be performed by the computer. So far in each of our PHP programs, each step has been explicitly laid out in the order we want it to happen.

Sometimes we’ll have a group of actions we want to repeat in a program. In these situations, we could copy and paste the lines of code we want to run again, but this isn’t very efficient. Instead, we should use functions.

A function is a set of instructions we package as a unit, often with a name, so that we can reuse it. We define a function by writing out the series of steps that should happen whenever we use the function. To use the function we call or invoke it.

In this lesson, we’re going to start learning the syntax for defining and invoking PHP functions. We’ll start with simpler functions and work our way to more complex ones. If this is your first time working with functions, it can feel like a big jump. Take your time and be patient with yourself.

![caption](https://content.codecademy.com/courses/php-functions/PHP_Salad_Recipe.mov)

------------------------------
2.Defining Functions
------------------------------


Let’s get right to it and create our first function:

    function greetLearner()
    {
      echo "Hello, Learner!\n";
      echo "I hope you're enjoying PHP!\n";
      echo "Love, Codecademy";
    }

Let’s walk through the code above:

We used the function keyword to start our function definition.
We named the function greetLearner. Function names must start with a letter or underscore, followed by any number of letters, numbers, or underscores.
We created a code block with curly brackets ({ }). The code inside this code block will execute when our function is invoked.
Within that block we wrote three instructions: echo "Hello, Learner!\n!";, echo "I hope you're enjoying PHP!\n";, and echo "Love, Codecademy";

With our greetLearner() function defined, we’ll be able to invoke the function multiple times and print those strings without having to copy or retype the three echo statements again and again.

A few notes on naming conventions: we typically snake case (separate words with underscores) our variable names, but, in order to easily tell the difference between variables and functions in our code, we’ll do something different when naming functions. We’re going to use camel case for our function names—we’ll start with a lowercase letter and then capitalize the first letter of every new word: camelCase vs. snake_case. Another good practice is to name functions in a way that describes what they do—typically we’ll start function names with a verb. 

-------------------------------
3.Invoking Functions
------------------------------

In our last exercise, we saw that when we define a function, the instructions within the code block aren’t executed. Defining a function only tells the computer to associate a name with a set of instructions. To actually execute this code we’ll need in invoke, or call, the function. Invoking a function is the process of using a function that’s been defined. Let’s look at an example:

    function greetLearner()
    {
      echo "Hello, Learner!\n";
      echo "I hope you're enjoying PHP!\n";
      echo "Love, Codecademy";
    }

    greetLearner(); 
    /*
    Prints:
    Hello, Learner!
    I hope you're enjoying PHP!
    Love, Codecademy
    */
    
---------------------------------
4.Return Statements
--------------------------------

As we build more complicated functions, we’ll often be using them to process data. In order for the data to be useful, functions have the ability to return a value in addition to performing instructions. Let’s look at an example:

    function countdown() 
    {
      echo "4, 3, 2, 1, ";
      return "blastoff!";
    }

When the countdown() function is invoked it will print 4, 3, 2, 1,, but what about the string "blastoff!"? This value will be returned. We have a lot of options for what to do with a returned value. For example, we could capture it in a variable:

    $return_value = countdown(); // Prints: 4, 3, 2, 1, 
    echo $return_value; // Prints: blastoff!

This example is a little silly, since we could have just printed the string within the function, but, as we continue to create more complicated functions, the ability to return a value will become extremely useful. 

---------------------------------
5.More on Return Statements
-----------------------------------

The return keyword immediately stops a function. This means that any code after a return won’t run.

Let’s compare two different functions: announceRunning() and announceRunning2(). The first of these is defined as follows:

    function announceRunning()
    {
      echo "The first function is running!\n";
      return "This is the return value of the first function.";
    }

    $first_result = announceRunning();
    echo $first_result;

Let’s walk through the code above:

We defined the function announceRunning().
Next, we defined the variable $first_result and assigned as its value the result of invoking the announceRunning() function. This actually did two things. It executed the function causing "The first function is running!/n" to be printed. It also assigned "This is the return value of the first function." to $first_result.
Finally, we printed $first_result.

That seemed to work as expected. In our terminal we saw:

    The first function is running!
    This is the return value of the first function.

Let’s contrast that to the following example:

    function announceRunning2()
    {
      return "This is the return value of the second function.";
      echo "P.S., I love you";
    }
 
    $second_result = announceRunning2();
    echo $second_result;

In this example, the string "P.S., I love you" will never be printed! As soon as the return statement is reached, the function will end. So in the terminal, we’d see this output:

    This is the return value of the second function.
    
--------------------
6.Return Values
----------------------

The value returned from a function is just that—a value. This means it can be used in any manner we would normally use a value of that type. This can take some getting used to. Take a look at the following code:

    function returnFive() 
    {
      return 5;
    }

    echo returnFive(); // Prints: 5

In the code above we defined a silly function, returnFive(); all it does is return the number 5. Then we used echo to print the invoked function. The way that the computer executes functions and handles their returns can take getting used to, but it’s very similar to what we experienced with numbers and variables:

    echo 5 + 3; // Prints: 8

    $num = 5;

    echo $num + 3; // Prints: 8

    echo returnFive() + 3; // Prints: 8

A computer evaluates 5 + 3 to 8. In the same manner, when a computer encounters a function invocation, it will execute the code in the function’s body and then evaluate to the function’s returned value. We need to think of functions as both what they do (the instructions in their code block) and what they return. 

-----------------------------
7.Returning NULL
-----------------------------

What about functions without return statements? Any function without a return returns a special value NULL. NULL is a special data type that stands for the absence of a value.

    function returnNothing() 
    {
      echo "I'm running! I'm running!\n";
    }

    $result = returnNothing(); // Prints: I'm running! I'm running!

    echo $result; // Nothing is printed

Let’s walk through the code above:

We defined a function returnNothing()— the returnNothing() function prints "I'm running! I'm running!\n" but has no return statement.
We defined the variable $result and assigned it the value returned when we invoke returnNothing().
Since we invoked the function, I'm running! I'm running! is printed.
Because the function does not have a return statement, the value assigned to $result is NULL
Finally, we print the $result variable, but, since its value is NULL, nothing is printed.

---------------
8.Parameters
---------------

Functions that do exactly the same thing every time they run can save us from having to repeat code in our programs, but functions can do more.

In the beginning of this lesson, we wrote a greetLearner() function that printed the same friendly greeting every time it was invoked. That’s ok… we guess… But what we’d really like is to print a customized greeting. We can accomplish this by using parameters!

When we define a function, we can also define parameters. A parameter is a variable which serves as a placeholder throughout the function’s code block. When the function is invoked, it’s invoked with a specific value. As the computer executes the function, it replaces each occurrence of the parameter with the value that was passed in. The actual value passed in is known as an argument.

Let’s look at an example:

    function sayCustomHello($name)
    {
        echo "Hello, $name!";
    };
 
    sayCustomHello("Aisle Nevertell"); // Prints: Hello, Aisle Nevertell!

    sayCustomHello("Codecademy learner"); // Prints: Hello, Codecademy Learner!

In the code above, we defined the sayCustomHello() function. It has a $name parameter. We invoked the function twice:

The first time, we passed in "Aisle Nevertell" as the argument. During that invocation, the function assigned "Aisle Nevertell" to $name so Hello, Aisle Nevertell! was printed.
The second time we invoked the function with the argument "Codecademy learner" so $name was assigned that value and Hello, Codecademy Learner! was printed.

---------------------
9.Multiple Parameters
----------------------

We can also define functions with multiple parameters.

    function divide($num_one, $num_two)
    {
      return $num_one / $num_two;
    };

In the function above, we defined the divide() function. It takes in two number arguments and returns the result of dividing the first parameter by the second. Let’s look at how we invoke this function:

    echo divide(12, 3); // Prints: 4

    echo divide(3, 12); // Prints: 0.25

In the code above:

    First, we printed the value returned from invoking our divide() function with 12 and 3 as arguments.
    Next, we printed the value returned from invoking our divide() function with 3 and 12.

Notice that the order we pass in the arguments decides which parameters they correspond to—the first argument we pass into divide() will be assigned to $num_one and the second argument to $num_two.

Invoking a function with fewer arguments than expected will result in an error:

    function expectTwo($first, $second)
    {
      return "whatever";
    }

    echo expectTwo("test"); // Will result in an error

----------------------
10.Default parameters
-----------------------

Earlier we wrote a sayCustomHello() function which took in a $name and printed a custom greeting. If we tried to invoke this function without an argument, it would cause an error; the function is designed to run with one argument, and it won’t accept fewer.

    function sayCustomHello($name)
    {
      echo "Hello, $name!";
    };

    sayCustomHello(); // Causes an error!

We can be more flexible about parameters when defining our functions. We want to print "Hello, [name passed in]!" if an argument is provided, and "Hello, old chum!" only if no argument is passed in.

We can accomplish this by providing a default value for the $name parameter:

    function greetFriend($name = "old chum")
    {
      echo "Hello, $name!";
    };

    greetFriend("Marvin"); // Prints: Hello, Marvin!

    greetFriend(); // Prints: Hello, old chum!

In the code above, we defined the greetFriend() function. It has a parameter $name with a default value of “old chum”. We invoked the function twice:

The first time, we passed in "Marvin" as the argument. During that invocation, the function assigned "Marvin" to $name so Hello, Marvin! was printed.
The second time we invoked the function with no argument. Therefore, the default value of "old chum" was assigned to $name and Hello, old chum! was printed.

--------------------------
11.Pass By Reference
-------------------------
We can invoke functions with variables or with values directly. When we invoke a function with a variable as its argument, it’s as if we’re assigning the value held by that variable to the function’s parameter. We assign a copy of the value held by the argument variable. The variable argument and the parameter are distinct entities; changes made inside the function to the parameter will not affect the variable that was passed in:

    function addX ($param)
    {
      $param = $param . "X";
      echo $param;
    };
    $word = "Hello";
    addX($word); // Prints: HelloX
    echo $word; // Prints: Hello

Let’s walk through the code above:

We defined a function addX() which reassigns $param to its previous value appended with "X".
We defined the variable $word and assigned it the value "Hello".
We invoked addX() with $word as its argument.
During the function invocation, $param was reassigned and the function printed "HelloX".
When we printed $word after the function was invoked, it remained its original value: "Hello".

If we do want to make permanent changes to a variable within a function, we can prepend the parameter name with the reference sign (&). In this way, we assign the parameter to be an alias for the argument variable. Both will refer to the same spot in memory, and changes to the parameter within the function will permanently affect the argument variable.

    function addXPermanently (&$param)
    {
      $param = $param . "X";
      echo $param;
    };
    $word = "Hello";
    addXPermanently($word); // Prints: HelloX
    echo $word; // Prints: HelloX

In the addXPermanently() function we made $param a reference to the argument. When we invoked the function with $word the changes made to $param permanently affected the $word variable. 

-----------------------------
12.Variable scope
-------------------------------
Passing arguments into a function and returning values is a clear way to define the interface between the function and the rest of the code. This is the preferred method of exchanging information within a program since it is straightforward to see the data a function depends on from the function parameter list.

Consider the following function. It returns a number of days left of feed depending on the number of chickens and the rate at which they consume it.

    function calculateDaysLeft($feed_quantity, $number, $rate)
    {
      $result = $feed_quantity / ($number * $rate);
      return $result;
    }
    echo calculateDaysLeft(300, 2, 30);

You can immediately see that this function depends on three pieces of information to provide an answer:

    $feed_quantity
    $number
    $rate

We also echo what is returned by the function, instead of a variable from inside the function. If we attempted to:

    echo $result;

outside of the function, it would throw an error (Undefined variable). This is due to variable scope. Each function has its own local scope. This means that any variables defined within the function’s code block can only be accessed within the code block itself.

However, if many functions depend on the same piece of information, it can be beneficial to have a variable that can be accessed anywhere without being passed in. To do this, we have to use the global keyword to tell PHP to look in the global scope for the variable, instead of the local scope of the function.

    $feed_quantity = 300;
    function calculateDaysLeft($number, $rate)
    {
      global $feed_quantity;
      $result = $feed_quantity / ($number * $rate);
      return $result;
    }
    echo calculateDaysLeft(2, 120);

When using this pattern, it becomes slightly more difficult to determine what information this function depends on. Make sure to consider this trade-off when implementing your own functions.

Note that the global keyword is not used when invoking functions. Once a function has been defined, it can be used within the same code block or even within other function code blocks. This code will print “This works!” to the console.

    function first()
    {
      echo "This works!\n";
    }
    function second()
    {
      first();
    }
    second();
    
--------------------------------------------------------
Quick Review C
--------------------------------------------------------

![Alt text](https://content.codecademy.com/courses/php-functions/php_functions_syntax.png)


------------------------------------------------------------------------------------
D.Intro to Built-in PHP Functions
-------------------------------------------------------------------------------------

------------------------
1.Introduction
-------------------------

If you’ve been paying attention so far, you might have picked up a theme in programming—shortcuts. Defining our own functions gives us an easier way to repeat similar code throughout a program. But some tasks are so common that the language comes with them by default.

PHP comes with a number of built-in functions. These functions—also known as internal functions— can be invoked without writing them ourselves. In this lesson, we’ll explore some useful built-in functions and empower you to discover new built-in functions yourself. This will quickly become an essential part of your developer toolkit! 

Ex:

We’ve been using echo to print information to the console. echo is NOT a function (it’s a “language construct”). But, one little PHP quirk is that we can use it in a way that looks a lot like invoking a function—we can wrap an argument for echo in parentheses.

echo can also be used to print multiple string arguments, but unlike a function, for this feature to work we must NOT wrap them in parentheses. Take a look at the code editor; we’ve provided some examples of using echo with and without parentheses. If you’d like, uncomment the broken code to see the error it causes.

    <?php
    echo("This works!\n");

    echo "This also works!\n";

    //echo("This would NOT work", "\n");   //Cause an error

    echo "Buuuut!", " ", "This", " ", "does!", "\n";


-----------------------------
2.Working with Variables
----------------------------

PHP includes useful built-in functions for getting information about variables. The gettype() function takes a variable as its argument and returns a string value representing the data type of the argument. 

    $name = "Aisle Nevertell";
    $age = 1000000;

    echo gettype($name); // Prints: string

    echo gettype($age); // Prints: integer
    
Notice that we didn’t write a definition for the gettype() function ourselves—it’s built into PHP. Since the function is included within the language itself, we can just call it anywhere within our PHP code.

Let’s take a look at another built-in function! The var_dump() function also takes a variable argument. It prints details about the argument it receives.

In the code above, we first used var_dump() to print information about the variable $name. string(15)—the variable’s type and length—were printed followed by the value held by the variable.

-----------------------------
3.String Functions
----------------------------

We can find PHP built-in functions to accomplish common tasks. Need to reverse a string? There’s a built-in function for that!

The strrev() function takes in a string as its argument and returns a string with all of the characters of the original string in reverse order.

Let’s see it in action:

    echo strrev("Hello, World!"); // Prints: !dlroW ,olleH

Remember that we can use the values returned from functions directly (rather than saving them into variables). In the code above, we used echo to print the value returned from invoking the strrev() function with the string "Hello, World!" as its argument.

PHP also comes with built-in functions to change the capitalization of a string. We can use the strtolower() function to transform an argument string into all lowercase letters:

    echo strtolower("HeLLo"); // Prints: hello

Built-in functions often have multiple parameters. The str_repeat() function takes a string as its first argument and a number as its second. It returns a string containing the argument string repeated the argument number of times.

    echo str_repeat("hi", 10); // Prints: hihihihihihihihihihi 


--------------------------------
4.Working with Substrings
--------------------------------
A substring is a portion of a string. For example, "hello" is a substring of the string "Oh hello, how are you?" and "el" is a substring of the string "hello". Manipulating strings is very common in programming, and working with substrings is often necessary.

The substr_count() function returns the number of instances of a substring within a string. It takes two arguments, the string to search through—sometimes called the haystack— and the string to search for—sometimes called the needle.

    $story = "I was like, \"Dude, like just tell me what you like think because like everyone else is like being totally honest, and like I just want to know what you like think.\" So like I don't know...";

    echo substr_count($story, "like"); // Prints: 8

In the code above, we invoked the substr_count() function, passing in $story as the haystack and "like" as the needle. We used echo to print the returned result—8, which is the number of times the substring "like" appears in the $story string. 

----------------------------
5.Number Functions
----------------------------

Another common task in programming is working with numbers, so it shouldn’t surprise us that PHP comes with some handy built-in functions for working with numbers.

The abs() function returns the absolute value of its number argument:

    echo abs(-10.99); // Prints: 10.99

    echo abs(127); // Prints: 127

Another useful function is the round() function which returns the nearest integer to its number argument:

    echo round(1.2); // Prints 1

    echo round(1.5); //Prints 2

    echo round(1298736.821763876); // Prints: 1298737
    
------------------------------
6.Generating Random Numbers
------------------------------

Generating random numbers may not seem obviously useful, but, as your programs become increasingly complicated, you’ll see this is actually a common task—for example to randomize data for testing.

The rand() function returns a random integer. We have some flexibility with how we invoke it. Invoking rand() with no arguments will return a number between 0 and the largest number our current environment will allow; this is a quirk of PHP. We can find out what this number is by invoking a different built-in function, getrandmax():

    $max = getrandmax(); 

    echo $max;

    echo rand(); // Prints a number between 0 and $max

In the code above, we assigned the largest possible random integer to the $max variable by invoking the getrandmax() function.

Next, we used echo to print a random integer. This integer will be a number between 0 and $max.

Functions often have a strict definition which dictates exactly which arguments it expects to be called with and results in an error otherwise. The rand() function, however is somewhat flexible.

If we’d like more control over the random number we generate, we can invoke the rand() function with two integer arguments representing the smallest allowable random number and the largest allowable random number. Fun fact: the second argument provided can be larger than getrandmax(). These numbers are inclusive meaning the arguments we pass in could be generated by the function.

    echo rand(1, 2); // Prints either 1 or 2

    echo rand(5, 10); // Prints a number between 5 and 10 (inclusive!)

    echo rand(1, 100); // Prints a number between 1 and 100 (inclusive!)
   
----------------------------
7.Documentation
--------------------------
In order to understand built-in functions we’ve never used before, we’ll want to get comfortable understanding how they are represented in the documentation. Documentation typically includes:

    -> The name of the function.
    -> The versions of the PHP language the function is available in.
    -> An overview of how the function works.
    -> Additional details on the parameters and return value.
    -> Examples of the function in use.
    -> User comments further explaining features of the function.

The description section can be confusing, so we’ll break that down.

Here’s the description for the abs() function:

    abs ( mixed $number ) : number

Here we see the function name followed by parentheses. The parentheses contain information about the function’s parameter(s)—first the parameter’s type followed by its name. The parameter for abs() has the type mixed because there are multiple data types the function will accept (an integer or a float). The parameter for abs() is named $number. After the parentheses is a colon (:) followed by number; this is the data type the function will return.

A function that prints something but doesn’t return a value will have :void instead of a return type. Similarly, a function that doesn’t accept parameters will have void within its parentheses.

Let’s look at a more complicated example. Here’s the description for the substr_count() function:

    substr_count ( string $haystack , string $needle [, int $offset = 0 [, int $length ]] ) : int

Earlier in this lesson, we invoked substr_count() with only the two string parameters ($haystack and $needle). But functions can have optional parameters. This means they’ll work with or without them. These parameters are wrapped in square brackets ([ ]) in the function’s description. An optional parameter may have a default value, this is the value that will be used if no argument is passed into the function. The default value is indicated with an equal sign (=).

The substr_count() function accepts two additional integer arguments—$offset and $length. $offset has a default value of 0.

    ------------------------
    Example
    ------------------------
    
    Here’s the description for the str_pad() built-in function:

    str_pad ( string $input , int $pad_length [, string $pad_string = " " [, int $pad_type = STR_PAD_RIGHT ]] ) : string

    In the code editor, we’ve provided four variables: $a, $b, $c, and $d. Your task is to invoke str_pad() with these four variables as its arguments so that it returns the string: *~**~**~*You did it!*~**~**~*. You’ll need to figure out which order to pass them in.

    Use echo to print the result of invoking the function.

    This task is designed to be a little challenging. Check out the (https://www.php.net/manual/en/function.str-pad.php) for more information, and take a look at the hint for more guidance.

    Note: One of the arguments (and its corresponding variable) is a PHP type we haven’t taught yet: pre-defined constants. You can solve this challenge without understanding them deeply. Predefined constants are similar to variables—they’re names which hold values. Unlike variables, predefined constants are defined by the language, not by us, and they’re constant, they can’t change value.
    
    
    Index.html
    
    <?php
    namespace Codecademy;

    $a = 29;
    $b = "You did it!";
    $c = STR_PAD_BOTH;
    $d = "*~*";

    // Write your code below:
    echo str_pad($b, $a, $d, $c);

    -------------------------------------
    Output: *~**~**~*You did it!*~**~**~* 

------------------------------
8.Finding Functions
------------------------------

Refer this example,

       Index.php
       
           <?php
    namespace Codecademy;

    // Write your code below:
    function convertToShout($str)
    {
      return strtoupper($str) . "!";
    }

    function tipGenerously($cost)
    {
      return ceil($cost * 1.2);
    }

    function calculateCircleArea($diameter)
    {
      return pi() * ($diameter/2)**2;
    }

    //Tests: 
    echo convertToShout("woah there, buddy"); 
    // Prints: WOAH THERE, BUDDY!
    echo "\n";
    echo convertToShout("i just don't know");
    // Prints: I JUST DON'T KNOW!
    echo "\n";
    echo tipGenerously(100.00); // Prints: 120
    echo "\n";
    echo tipGenerously(982.27); // Prints: 1179
    echo "\n";
    echo calculateCircleArea(6); 
    // Prints: 28.274333882308
    echo "\n";
    echo calculateCircleArea(29); 
    // Prints 660.51985541725  
    

-----------------------
Quick Review D
------------------------

    ---------------------
    Simple syntaxes 
    --------------- so far you have learned
    
        <?php
    $string_var = "Check it out";
    echo strtoupper($string_var) . "!\n";               

    echo ceil(8.873);
    echo "\n";                          

    echo pi();
    echo "\n";

    echo str_pad("PHP", 30, "*^*-", STR_PAD_BOTH);
    echo "\n";

    echo getrandmax();
    echo "\n";

    echo rand();
    echo "\n";

    echo rand(1, 52);
    echo "\n";

    echo abs(-1287);
    echo "\n";

    echo round(8723.999);
    echo "\n";

    echo substr_count($string_var, " ");
    echo "\n";

    echo strrev("\n.pu ti peeK .taerg gniod er'uoY");

    echo strtolower("SOON, tHiS WILL Look NoRmAL.\n");

    echo str_repeat("There's no place like home.\n", 3);

    echo gettype($string_var);
    echo "\n";
    echo var_dump($string_var);
    
    -----------------------------
    Output
    
    CHECK IT OUT!
    9
    3.1415926535898
    *^*-*^*-*^*-*PHP*^*-*^*-*^*-*^
    2147483647
    2063255896
    12
    1287
    8724
    2
    You're doing great. Keep it up.
    soon, this will look normal.
    There's no place like home.
    There's no place like home.
    There's no place like home.
    string
    string(12) "Check it out"
    
    --------------------------------
