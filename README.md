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


Point to be noted : void is the return type, which means it does not return a value.

---------------------------------
E.Ordered Arrays
---------------------------------

--------------------------
1.Introduction
--------------------------

So far in our PHP programming, we’ve been thinking about individual pieces of data. We’ve seen how useful variables can be for holding a single value, for example. But as our programs grow more complicated, it’s often useful to organize data into collections of elements, and to work with those collections as individual entities.

For example, when we build a to-do list, each item on the list is one piece of data, but the collection of all of the elements together is also a meaningful object. To help us store and manipulate related elements of data together, programming languages employ data structures.

One type of data structure fundamental to computer science is an array, a list of ordered, stored data. In PHP, we refer to this data structure as an ordered array.

The location of an element in an array is known as its index. The elements in an ordered array are arranged in ascending numerical order starting with zero—the index of the first array element is 0, the index of the second is 1, and so on.

Fun fact: Outside of programming, it’s somewhat unusual to see a count that starts at 0 instead of 1, but there’s a reason you’ll see this in many programming languages. In the original implementation of the array data structure, the computer reserved side-by-side spots in memory for each element in an array, but it was too inefficient to keep track of all these memory locations. Therefore, the computer only stored the memory address of the very first element. The index was used to indicate how far away from the start of the array a given element was located. The first element of an array was zero spaces away from that stored address, hence it was at the 0th index.

![Alt text](https://content.codecademy.com/courses/learn-cpp/vectors/11235.gif)

-------------------------------
2.Creating Arrays with array()
-------------------------------

We can construct ordered arrays with a built-in PHP function: array(). 

We can construct ordered arrays with a built-in PHP function: array().

The array() function returns an array. Each of the arguments with which the function was invoked becomes an element in the array (in the order they were passed in).

Arrays are most useful when we store them in variables. We create an array variable the same way we create variables of other data types—with the assignment operator.

    $my_array = array(0, 1, 2);

In the code above, we constructed an array using the array() function which we captured with the $my_array variable. $my_array is an array with three elements: 0 is located in the 0th index, 1 in the 1st, and 2 in the 2nd.

    PHP arrays can store elements of any data type:

$string_array = array("first element", "second element");

In the code above, $string_array holds two string elements. The string "first element" is located at the 0th location index, and the string "second element" is located at the 1st.

PHP arrays can also store elements of multiple data types:

    $mixed_array = array(1, "chicken", 78.2, "bubbles are crazy!");

Above, $mixed_array holds four elements—some are strings while others are numbers.

We can use the built-in PHP count() function to get the number of elements in an array. This is especially useful as we work with larger and more complicated arrays:

    echo count($my_array); // Prints: 3
    echo count($string_array); // Prints: 2
    echo count($mixed_array); // Prints: 4
    
---------------------------------------
3.Creating Arrays with Short Syntax
---------------------------------------


In addition to using array(), we can also create an array by wrapping comma-separated elements in square brackets ([ ]). This feature is sometimes referred to as short array syntax, and more closely resembles what you might see in other programming languages.

    $number_array = [0, 1, 2];

In the code above, we created the variable $number_array and assigned as its value an array containing the numbers 0, 1, and 2. The number 0 is located at the 0th location index, the number 1 at the 1st, and the number 2 and the 2nd.

Let’s compare using short array syntax with invoking the array() function:

    $string_array = array("first element", "second element");
    $str_arr_short = ["first element", "second element"];

    $mixed_array = array(1, "chicken", 78.2, "bubbles are crazy!");
    $mix_arr_short = [1, "chicken", 78.2, "bubbles are crazy!"];

Here, regardless of which method we used, we got the same results.

When constructing arrays, we can also place each element on its own line to make it easier to read:

    $long_array = [
      1,
      2,
      3,
      4,
      5,
      6
    ];


------------------------------
4.Printing Arrays
-----------------------------

Since arrays are a more complicated data type than strings or integers, printing them is slightly more challenging. Using echo won’t have the desired result:

    $number_array = [0, 1, 2];
    echo $number_array; // Prints: Array

When we tried to use echo to print $number_array, it printed the word “Array” rather than the contents of the array. To print the contents of the array, we can use PHP built-in functions. The built-in print_r() function outputs arrays in a human readable format:

    print_r($number_array);

This will output the array in the following format:

    Array
    (
        [0] => 0
        [1] => 1
        [2] => 2
    )

If we merely want to print the elements in the array listed, we can convert the array into a string using the built-in implode() function. The implode() function takes two arguments: a string to use between each element (the $glue), and the array to be joined together (the $pieces):

    echo implode(", ", $number_array);

This will output in the following format:

    0, 1, 2 
    
--------------------------
5.Accessing an Element
----------------------------

The individual elements in an array can be accessed using the array variable’s name, and the location index surrounded by square brackets ([]), for example:

    $my_array = ["tic", "tac", "toe"];

    echo $my_array[1]; // Prints: tac

This process is sometimes referred to as indexing an array.

Remember the computer evaluates variables it encounters (outside of assignment): it replaces them with the values they hold. Let’s look at an example of indexing an array with a number variable:

    $num_var = 2;

    $important_info = ["talking chicken", 181, "magnets?!", 99];

    echo $important_info[$num_var]; // Prints: magnets?!
    
------------------------------
6.Adding and Changing Elements
-----------------------------

We can make adjustments to existing arrays—we don’t have to create a new array when we want our array to change.

We add elements to the end of an array by taking the variable name and appending square brackets ([]), the assignment operator (=), and the element we want to add:

    $string_array = ["first element", "second element"];

    $string_array[] = "third element";
 
    echo implode(", ", $string_array); 
    // Prints: first element, second element, third element 

We can also reassign the individual elements in an array:

    $string_array = ["first element", "second element", "third element"];

    $string_array[0] = "NEW! different first element";

    echo $string_array[0]; // Prints: NEW! different first element"

In the code above, we replaced the original string held in the array ("first element") with a new string value: "NEW! different first element".

-----------------------------------------
7.More Array Methods: Pushing and Popping
-----------------------------------------

In the previous exercise, we learned how to add single array elements and to change array elements at a given index. PHP also provides us with built-in methods for removing array elements, and for adding many elements at once.

The array_pop() function takes an array as its argument. It removes the last element of an array and returns the removed element.

    $my_array = ["tic", "tac", "toe"];
    array_pop($my_array); 
    // $my_array is now ["tic", "tac"]
    $popped = array_pop($my_array); 
    // $popped is "tac"
    // $my_array is now ["tic"]

Note that array_pop() doesn’t just set the last element to NULL. It actually removes it from the array, meaning that array’s length will decrease by one (which we can verify using count()).

The array_push() function takes an array as its first argument. The arguments that follow are elements to be added to the end of the array. array_push() adds each of the elements to the array and returns the new number of elements in the array.

    $new_array = ["eeny"];
    $num_added = array_push($new_array, "meeny", "miny", "moe"); 
    echo $num_added; // Prints: 4
    echo implode(", ", $new_array); // Prints: eeny, meeny, miny, moe 
    
----------------------------
8.Shifting and Unshifting
----------------------------

We saw that array_pop() and array_push() deal exclusively with the end of the array (the index at the length of the array minus 1). PHP also provides functions for adding and removing elements from the beginning of an array (index 0).

The array_shift() function removes the first element of an array and returns that value. Each of the elements in the array will be shifted down an index. For example, the element that was previously at the 3rd index will now be located at the 2nd.

    $adjectives = ["bad", "good", "great", "fantastic"];
    $removed = array_shift($adjectives); 
    echo $removed; //Prints: bad
    echo implode(", ", $adjectives); // Prints: good, great, fantastic 

Just like array_pop(), array_shift() reduces the length of the array, and the deleted element is gone for good.

The array_unshift() function takes an array as its first argument. The arguments that follow are elements to be added to the beginning of the array. It returns the new number of elements in the array.

    $foods = ["pizza", "crackers", "apples", "carrots"];
    $arr_len = array_unshift($foods, "pasta", "meatballs", "lettuce"); 
    echo $arr_len; //Prints: 7
    echo implode(", ", $foods); 
    // Prints: pasta, meatballs, lettuce, pizza, crackers, apples, carrots

-----------------------------
9.Nested Arrays
-----------------------------

We mentioned that arrays can hold elements of any type—this even includes other arrays! We can use chained operations to access and change elements within a nested array:

    $nested_arr = [[2, 4], [3, 9], [4, 16]];
    $first_el = $nested_arr[0][0];
    echo $first_el; // Prints: 2

Above, $nested_arr is an array with three array elements. The first, located at the 0th index, is the array [2, 4]. The expression $nested_arr[0] returns that array. We then index that array’s first element by appending an additional [0].

This can take practice to get used to. One helpful technique is to act like the computer; evaluate each part of the expression from left to right. By breaking down a complex expression into its simpler parts, it becomes easier to understand. Let’s walk through a more complicated example together:

    $very_nested = [1, "b", 33, ["cat", 6.1, [9, "LOST!", 6], "mouse"], 7.1];

We want to change the element which is currently "LOST!" to "Found!". Let’s breakdown the steps:

We need the outermost array first: $very_nested[3] evaluates to the array ["cat", 6.1, [9, "LOST!", 6], "mouse"]
Next we need the array located at the 2nd location index: $very_nested[3][2] evaluates to the array [9, "LOST!", 6]
And finally, the element we’re looking for: $very_nested[3][2][1] evaluates to "LOST!"

    $very_nested[3][2][1] = "Found!";
    
---------------------
Quick Review E
----------------------


-> Arrays are ordered collections of data that are a type of data structure fundamental to computer science.

-> In PHP, we refer to this data structure as ordered arrays.

-> The location of an element in an array is known as its index.

-> The elements in an ordered array are arranged in ascending numerical order starting with index zero.

-> We can construct ordered arrays with a built-in PHP function: array().

-> We can construct ordered arrays with short array syntax, e.g. [1,2,3].

-> We can print arrays using the built-in print_r() function or by converting them into strings using the implode() function.

-> We use square brackets ([]) to access elements in an array by their index.

-> We can add elements to the end of an array by appending square brackets ([]) to an array variable name and assigning the value with the assignment operator (=).

-> We can change elements in an array using array indexing and the assignment operator.

-> The array_pop() function removes the last element of an array.

-> The array_push() function adds elements to the end of an array.

-> The array_shift() function removes the first element of an array.

-> The array_unshift() function adds elements to the beginning of the array.

-> We can use chained square brackets ([]) to access and change elements within a nested array.

    -------------------------------
    Simple syntaxes to be remember
    -------------------------------
    
    <?php
    // Using array() to construct an array:
    $prime_numbers = array(2, 3, 5, 7, 11, 13, 17);  

    // Using short array syntax:
    $animals = ["dog", "cat", "turtle", "cow"];  

    // Printing with print_r():
    print_r($prime_numbers);

    echo "\n\n";

    // Printing with echo and implode()
    echo implode(", ", $animals);

    // Adding an element with square brackets:
    $prime_numbers[] = 19;

    // Accessing an array element:
    $favorite_animal = $animals[0];
    echo "\nMy favorite animal: " . $favorite_animal;

    // Reassigning an element:
    $animals[1] = "tiger";

    // Using array_pop():
    echo "\nBefore pop: " . implode(", ", $animals);
    array_pop($animals);
    echo "\nAfter pop: " . implode(", ", $animals);

    // Using array_push():
    echo "\nBefore push: " . implode(", ", $prime_numbers);
    array_push($prime_numbers, 23, 29, 31, 37, 41);
    echo "\nAfter push: " . implode(", ", $prime_numbers);

    //Using array_shift():
    echo "\nBefore shift: " . implode(", ", $animals);
    array_shift($animals);
    echo "\nAfter shift: " . implode(", ", $animals);

    //Using array_unshift():
    echo "\nBefore unshift: " . implode(", ", $animals);
    array_unshift($animals, "horse", "zebra", "lizard");
    echo "\nAfter unshift: " . implode(", ", $animals);

    //Using chained operations with nested arrays:
    $treasure_hunt = ["garbage", "cat", 99, ["soda can", 8, ":)", "sludge", ["stuff", "lint", ["GOLD!"], "cave", "bat", "scorpion"], "rock"], "glitter", "moonlight", 2.11];

    echo "\nWe found " . $treasure_hunt[3][4][2][0];

    -------------------------
    Output:

        Array
        (
            [0] => 2
            [1] => 3
            [2] => 5
            [3] => 7
            [4] => 11
            [5] => 13
            [6] => 17
        )


        dog, cat, turtle, cow
        My favorite animal: dog
        Before pop: dog, tiger, turtle, cow
        After pop: dog, tiger, turtle
        Before push: 2, 3, 5, 7, 11, 13, 17, 19
        After push: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41
        Before shift: dog, tiger, turtle
        After shift: tiger, turtle
        Before unshift: tiger, turtle
        After unshift: horse, zebra, lizard, tiger, turtle
        We found GOLD! 

------------------------------
F.Associative Arrays
------------------------------

--------------------
1.Introduction
-------------------

Ordered arrays are awesome when we have data that lends itself to being collected into an ordered (indexed) list. But data can be collected and organized in lots of ways. 

Ordered arrays are awesome when we have data that lends itself to being collected into an ordered (indexed) list. But data can be collected and organized in lots of ways.

Imagine we wanted a data structure to hold a bunch of information about ourself: our name, age, email address, birthday, social security number, and favorite food. We want all of these pieces of data in a single collection but not necessarily in any particular order. And it doesn’t make much sense to access these data items using indices, like in an ordered array. It would be hard to remember, for example, that index 0 corresponds to our name.

Time to meet another fundamental concept in computer science—the map. A map associates keys with values. A key is a string or integer that we use to access a value (of any type). We could create a map with a key "fullname" that points to a value of "Aisle Nevertell"; this is much more understandable than associating the name with index 0. Whenever we need to access a value, we’ll be able to use the associated key to find it.

The PHP array type that we’ve been working with is actually implemented as a map! In a PHP ordered array, the index locations are the keys. But the PHP array type also enables us to build more traditional map-like structures where we assign meaningful keys to values (as opposed to indices). We call data structures like this associative arrays.

![Associative array](https://content.codecademy.com/courses/learn-javascript-objects/javascript_illo.svg)


------------------------
2.Associative Arrays
------------------------

Associative arrays are collections of key=>value pairs. The key in an associative array must be either a string or an integer. The values held can be any type. We use the => operator to associate a key with its value. 

![Alt text](https://content.codecademy.com/courses/learn-javascript-objects/key%20value.svg)

We can think of keys as pointing to their values since the key points the computer to the space in memory where the value is stored.

    $my_array = ["panda" => "very cute", "lizard" => "cute", "cockroach" => "not very cute"];

In the code above, we created an associative array using short array syntax. $my_array has three key=>value pairs:

The key "panda" points to the value "very cute".
The key "lizard" points to the value "cute".
The key "cockroach" points to the value "not very cute".

We can also build associative arrays using the PHP array() function.

    $about_me = array(
        "fullname" => "Aisle Nevertell",
        "social" => 123456789
    );

In the code above, we created an associative array, $about_me, with two key=>value pairs:

The key "fullname" points to the value "Aisle Nevertell".
The key "social" points to the value 123456789.


------------------------------
3.Printing Associative Arrays
------------------------------

As with ordered arrays, using echo to print an entire associative array is not very useful:

    $grades = [
        "Jane" => 98,
        "Lily" => 74,
        "Dan" => 88,
    ];

    echo $grades; // Prints: Array

We can combine each of the values contained by the array into a single string and use echo to print that:

    echo implode(", ", $grades); // Prints: 98, 74, 88 

A problem with this technique is that it only displays the values. We don’t see the keys in the array or the relationships between the keys and values. To display this information, we can use the built-in print_r() function:

    print_r($grades);

The above code will produce the following output:

    Array
    (
        [Jane] => 98
        [Lily] => 74
        [Dan] => 88
    )
    
-----------------------------------
4.Accessing and Adding Elements
------------------------------------

We access the value a given key points to using square brackets ([]):

    $my_array = ["panda"=>"very cute", "lizard"=>"cute", "cockroach"=>"not very cute"];
    echo $my_array["panda"]; // Prints: very cute

In the code above, we accessed the value "very cute" using its key, "panda".

To add new elements to an associative array, we use the assignment operator (=):

    $my_array["capybara"] = "cutest";
    echo $my_array["capybara"]; // Prints: cutest

In the code above, we added a fourth key value pair to the array. We accessed the new value "cutest" using its key "capybara" and printed it using echo.

The computer treats code between the square brackets as an expression, so that code will be evaluated before the array is accessed. This enables us to use variables, functions, and operators within the square brackets:

    $favorites = ["favorite_food"=>"pizza", "favorite_place"=>"my dreams", "FAVORITE_CASE"=>"CAPS","favorite_person"=>"myself"];

    echo  $favorites["favorite" . "_" . "food"]; 
    // Prints: pizza

    $key =  "favorite_place";
    echo  $favorites[$key];  
    // Prints: my dreams

    echo $favorites[strtoupper("favorite_case")];
    // Prints: CAPS


----------------------------------
5.Changing and Removing Elements 
---------------------------------

The same syntax that adds new array elements can be used to change existing elements:

    $new_arr = ["first" => "I am first!", "second" => "I am second!"]; 

    $new_arr["third"] = "I am third!";

    echo $new_arr["third"]; // Prints: I am third!

    $new_arr["third"] = "I am the *NEW* third!";

    echo $new_arr["third"]; // Prints: I am the *NEW* third!

In the above code, we use the same syntax to add a key=>value pair ("third" => "I am third!") as we do to assign that key a new value ("third" => "I am the *NEW* third!").

Since PHP will allow us to add a new key=>value pair or change an existing value using exactly the same code, we’ll need to use caution to avoid accidentally overwriting an existing value.

We can remove a key=>value pair entirely using the PHP unset() function. Note: if the key used doesn’t exist in the array, then nothing happens.

    $nums = ["one" => 1,"two"=> 2];

    echo implode(", ", $nums); // Prints: 1, 2

    unset($nums["one"]);

    echo implode(", ", $nums); // Prints: 2

In the code above, we created an associative array with two key => value pairs. We then removed the pair "one" => 1 using the unset() function. 

--------------------------
6.Numerical Keys
--------------------------
Associative arrays can use integers as keys, in addition to strings.

    $num_array = [1000 => "one thousand", 100 => "one hundred", 600 => "six hundred"];
    echo $num_array[1000]; // Prints: one thousand

When we build ordered arrays in PHP, the association with numerical keys to values is done for us automatically. The first element is associated with the key 0, the second with 1, and so on. But ordered arrays are still the same structure as associative arrays. We can mix and match:

    $ordered = [99, 1, 7, 8];
    $ordered["special"] = "Cool!";
    echo $ordered[3]; // Prints: 8
    echo $ordered["special"]; // Prints: Cool!

When we add an element to an array without specifying a key (e.g. using array_push()), PHP will associate it with the “next” integer key. If no integer keys have been used, it will associate it with the key 0, otherwise it will associate it one more than the largest integer used thus far. This behavior is the same whether the array is being used as an ordered array or an associative array. Let’s look at an example:

    $num_array = [1000 => "one thousand", 100 => "one hundred", 600 => "six hundred"];
    $num_array[] = "New Element in \$num_array";
    echo $num_array[1001]; // Prints: New Element in $num_array
 
    $animals_array = ["panda"=>"very cute", "lizard"=>"cute", "cockroach"=>"not very cute"];
    array_push($animals_array, "New Element in \$animals_array");
    echo $animals_array[0]; // Prints: New Element in $animals_array

Even though associative arrays and ordered arrays are technically the same, we recommend treating them as separate data types. Only use the empty square brackets syntax (or functions like array_push()) with ordered arrays.

But, for now, let’s break this rule a little to get used to the ins and outs of PHP arrays!

    -------------------------
    Let's see one 
    
    Example:

        <?php
        namespace Codecademy;

        // Write your code below:
        $hybrid_array = ["cat", "dog", 9, 18.2];

        $hybrid_array[8] = "five more";

        print_r($hybrid_array);

        array_push($hybrid_array, rand());


        echo $hybrid_array[9];

    ------------------------------
    Output
    
    Array
    (
        [0] => cat
        [1] => dog
        [2] => 9
        [3] => 18.2
        [8] => five more
    )
    1348309497
    
    
--------------------------------
7.Joining Arrays
--------------------------------

PHP also lets us combine arrays. The union (+) operator takes two array operands and returns a new array with any unique keys from the second array appended to the first array.

    $my_array = ["panda" => "very cute", "lizard" => "cute", "cockroach" => "not very cute"];
    $more_rankings = ["capybara" => "cutest", "lizard" => "not cute", "dog" => "max cuteness"];
    $animal_rankings = $my_array + $more_rankings;

The $animal_rankings we created above will have each of the key=>value pairs from $my_array. In addition, it will contain the key=>value pairs from $more_rankings: "capybara"=>"cutest" and "dog"=>"max cuteness". However, since "lizard" is not a unique key, $animal_rankings["lizard"] will retain the value of $my_array["lizard"] (which is "cute").

The union operator can be a little tricky… consider the following union:

    $number_array = [8, 3, 7];

    $string_array = ["first element", "second element", "third element"];

    $union_array = $number_array + $string_array;

What values does $union_array hold? It has the elements 8, 3, and 7. Since the two arrays being joined have identical keys (0, 1, and 2), no values from the second array, $string_array, are included in $union_array.

---------------------------------
8.Assign by Value or by Reference
---------------------------------

There are two ways to assign one variable to another:

    -> By value—this creates two variables which hold copies of the same value but remain independent entities.
    
    -> By reference—this creates two variable names (aliases) which point to the same space in memory. They cannot be modified separately!

This remains true when dealing with array variables:

    $favorites = ["food"=>"pizza", "person"=>"myself", "dog"=>"Tadpole"];
    $copy = $favorites;
    $alias =& $favorites;
    $favorites["food"] = "NEW!";
 
    echo $favorites["food"]; // Prints: NEW!
    echo $copy["food"]; // Prints: pizza
    echo $alias["food"]; // Prints: NEW!

When passing arrays into functions, both built-in functions and those we write ourselves, we’ll want to be conscious of whether the arrays are being passed by value or by reference.

    function changeColor ($arr) 
    {
      $arr["color"] = "red";    
    }
    $object = ["shape"=>"square", "size"=>"small", "color"=>"green"];
    changeColor ($object);
    echo $object["color"]; // Prints: green

Our function above doesn’t accept its array argument by reference. Therefore, $arr is merely assigned a copy of the argument’s value. This copy array is changed when the function is invoked, but that doesn’t affect the orginal argument array ($object). To do that, we’d need to pass it by reference:

    function reallyChangeColor (&$arr) 
    {
      $arr["color"] = "red";    
    }
    $object = ["shape"=>"square", "size"=>"small", "color"=>"green"];
    reallyChangeColor ($object);
    echo $object["color"]; // Prints: red
    
----------------------
Quick Review F
----------------------


-> Associative arrays are data structures in which string or integer keys are associated with values.

-> We use the => operator to associate a key with its value. $my_array = ["panda"=>"very cute"]

-> To print an array’s keys and their values, we can use the print_r() function.

-> We access the value associated with a given key by using square brackets ([ ]). For example: $my_array["panda"] will return "very cute".

-> We can assign values to keys using this same indexing syntax and the assignment operator (=): $my_array["dog"] = "good cuteness";

-> This same syntax can be used to change existing elements. $my_array["dog"] = "max cuteness";


-> We can remove a key=>value pair entirely using the PHP unset() function.

-> Keys can be integers. In fact, ordered arrays are just arrays in which integer keys have been assigned to the values automatically.

-> In PHP, associative arrays and ordered arrays are different uses of the same data type.

-> The union (+) operator takes two array operands and returns a new array with any unique keys from the second array appended to the first array.
When writing function with array parameters, we can pass the array by value or by reference depending on our intent.


Now we are going to see File handling concept in PHP....
Let's start with basic

-----------------------
G.PHP and HTML
-----------------------

PHP can be used in many ways. It can be used to write standalone programs that run in our terminal:

    echo "Hello, World!";

When run, the code above will output the following to the terminal:

    Hello, World!

But PHP was designed as a back-end web development language—specifically it was designed to work well with HTML. PHP allowed a convenient way for developers to create HTML templates and programatically fill them out in order to send customized HTML to visitors of their sites.

PHP has evolved into a powerful programming language being used for more than templating HTML, but using PHP combined with HTML remains an important part of many web developers’ skill sets.

In this lesson, we’ll delve into the difference between the front-end and the back-end and learn how to use PHP to generate HTML.


---------------------------
2.What is the Front-End?
---------------------------

Let’s talk about the difference between a front-end language and a back-end language. HTML is a front-end language, but what exactly does that mean?

When navigating to a website from our web browser, the browser makes a request for content on our behalf. What we see and experience as a single website is actually composed of a number of files which come together to form a cohesive experience.

The files we receive consist of JavaScript, CSS, HTML, images, and other static assets. A static asset is a file that doesn’t change. When we navigate to a webpage, these assets are sent to a browser.

You may have heard front-end development referred to as client-side development. In web development, we are typically referring to the browser as the client. A human may be experiencing the website, but it’s the browser that makes requests for information and receives the responses.

The front-end of a website or web application consists of all the elements of the website that are sent to the client upon request. But something has to be listening for those requests and deciding what to send — it’s the back-end of the website that does all that and more.

----------------------------
3.What is the Back-End?
----------------------------

The back-ends of websites will differ depending on the needs of the site. Typically, they’ll have at least the following components:

A web server: a web server is a computer or program which listens for requests from clients and sends back responses. This component is well suited to handling delivery of static content.

An application server: this is actually often a collection of programming logic which is needed to deliver dynamic content to a client. The application server will often handle other tasks such as site security and interacting with data.

A data base: important information like usernames and passwords has to be stored and accessed somewhere. A large web application will often have multiple databases to store all different types of data needed to run the site smoothly.

PHP can be used in many capacities in the back-end. However, in this lesson, we’ll get started small by focussing on one small role the PHP application server can play in generating HTML which the web server will send to a client.

![Alt text](https://content.codecademy.com/courses/updated_images/NodeBackEndFrontEnd_Update_1.gif)

--------------------------
4.PHP in HTML
-------------------------

We can embed PHP scripts within HTML documents with the opening tag <?php and the closing tag ?>. The PHP processor will read the entire file, evaluate any PHP, translate it into HTML, and pass it off to the web server so it can be sent to the client.

Consider the following code:

    <html>
     <head>
      <title>My First PHP Site</title>
     </head>
     <body>
     <?php 
        echo "<h1>Oh hi!</h1>"; 
      ?> 
     </body>
    </html>

In the code above, the line echo "<h1>Oh hi!</h1>" will generate an HTML header of Oh hi!.

When we use echo within HTML we’re no longer printing to the terminal, rather we’re outputting to the HTML document.

Wouldn’t it have been simpler to just add <h1>Oh hi!</h1> directly? Yep. This example certainly doesn’t show us why we’d want to use PHP within our HTML. As we learn to develop more robust PHP scripts and harness some of the language’s more complex features, we’ll grow to understand how powerful it can be. 

------------------------
5.Beyond Strings
----------------------

We can also incorporate more complex PHP within our scripts.

    <?php
    $lucky_number = 5 * 2 - 1;

    echo "<h1>Your lucky number is ${lucky_number}</h1>";
    ?>

The code above will be translated into HTML with a header that reads: Your lucky number is 9.

We can incorporate all the language features we know about PHP, including functions:

    <?php
    function makeHeaderGreeting ($name){
      return "<h1>Hello, ${name}!</h1>";
    }

    echo makeHeaderGreeting("World");
    ?>

The code above will be translated into HTML with a header that reads: Hello, World!.

-----------------------
Quick Review G
-----------------------

Let’s review what we’ve learned so far:

-> The front-end of a website consists of JavaScript, CSS, HTML, images, and other static assets sent to the client.

-> When we navigate to a website the browser is the client, and it sends a request to the back-end for all the assets needed to view and interact with the website.

-> The back-end consists of a web server and all the logic and data needed to create and maintain a website or web application.

-> PHP is a back-end language.

-> PHP can be used to generate HTML files.

-> We embed PHP scripts within HTML by inserting PHP code between the opening (<?php) and closing (?>) tags.


----------------------------
H.HTML Form Handling in PHP
----------------------------

-----------------------------
1.Introduction
-----------------------------

Presenting and interacting with HTML is one of the primary uses of PHP. Our server takes each PHP file (in our examples, this is index.php), and translates them into HTML to present to the client in their web browser.

This process allows for developers to create customized experiences for individual users.

PHP also provides the capability to handle input from users through HTML forms in a straightforward manner. Before we cover working with forms, take a minute to review how PHP code can be embedded into HTML:

    <p>This HTML will get delivered as is</p>
    <?php echo "<p>PHP interprets this and turns it into HTML</p>";?>
    <p>This HTML will get delivered as is</p>

This example uses the PHP opening (<?php) and closing (?>) tags to insert PHP code. It uses echo to add text to the HTML. This practice is so common that PHP provides a shorthand syntax. Instead of using <?php echo to begin the statement, you can simply use <?=.

Our example becomes: (Noted)

    <p>This HTML will get delivered as is</p>
    <?="<p>PHP interprets this and turns it into HTML</p>";?>
    <p>This HTML will get delivered as is</p>
    
    
-----------------------
2.Request Superglobals
------------------------

Since PHP was built with web development as a primary use case, it has functionality to ease processing of HTML requests. When the front end client makes a request to a backend PHP server, several superglobals related to the request are available to the PHP script. Superglobals are automatic global variables which are available in all scopes throughout a script.

The list of superglobals in PHP includes the following:

    $GLOBALS
    $_SERVER
    $_GET
    $_POST
    $_FILES
    $_COOKIE
    $_SESSION
    $_REQUEST
    $_ENV

For this lesson, we are focusing on three of these:

    $_GET - this contains an associative array of variables passed to the current script using query parameters in the URL
    $_POST - this contains an associative array of variables passed to the current script using a form submitted using the “POST” method
    $_REQUEST - this contains the contents of $_GET, $_POST, and $_COOKIE

---------------------------
3.GET Form Handling
---------------------------

In HTML, setting a form’s method attribute to "get" specifies that you would like the form to be submitted using the GET method. When using this method, the form entries are passed as parameters in a URL query string.

For example, this is a request to www.codecademy.com with the URL parameters first (set to the value "ellen") and last (set to the value "richards"):

    www.example.com/?first=ellen&last=richards
 

The parameter names (first and last) come from the name attribute of each form input.

For example, the following form could be used to collect an individual’s name using the GET method:

    <form method="get">
    First name: <input type="text" name="first">
    <br>
    Last name: <input type="text" name="last">
    <br>
    <input type="submit" value="Submit Name">
    </form>

When the form is submitted, the form data is available in the $_GET superglobal array. (The data is also accessible using $_REQUEST if you do not care about which method was used by the client.)

In our example, if a user typed “ellen” into the first input and “richards” into the last input, then print_r($_GET) would look like this:
    
    Array ( [first] => ellen [last] => richards )
    
-----------------------
4.POST Form Handling
-----------------------

In HTML, setting a form’s method attribute to "post" specifies that you would like the form to be submitted using the POST method. When using POST to submit forms, you will not see the URL change. The form data is sent using the headers of the HTTP request instead of URL parameters.

To use the data from the form in PHP, each input needs to have a unique name attribute.

When the form is submitted, the input data is available in the $_POST superglobal. Similar to GET, it is also available in $_REQUEST.

For example, if a user typed “Katharine” into the first input and “McCormick” into the last input of this form:

    <form method="post">
    First name: <input type="text" name="first">
    <br>
    Last name: <input type="text" name="last">
    <br>
    <input type="submit" value="Submit Name">
    </form>

The URL would not change and print_r($_POST) would look like this:

    Array ( [first] => Katharine [last] => McCormick )
    
------------------------------
6.Using the "action" Attribute
-------------------------------
Until now, we’ve been handling the response to the form submission on the same page as the form itself. Often times there is no need to present a user with the same form over and over again. It might make sense to move them to a new page or thank them for their submission.

This is where the action form attribute comes into play. Since we have not specified an action yet, HTML defaults to submitting the form data back to the same script that defined the form.

If you would like to have the user navigate to a new URL and handle the form input there, you can specify the URL in the form’s action attribute. Since the action attribute specifies a relative URL, you can also enter the name of a PHP file in the same directory as the current one.

For example, given this directory:

    index.php
    receive_form.php

To handle a form using receive_form.php from index.php, you would use the following:

    <form method="get" action="receive_form.php">

This works for both GET and POST methods.

---------------------
Quick Review H
---------------------

You’re ready to start handling forms in PHP!

To review:

-> <?= is shorthand for <?php echo.

-> PHP provides superglobals which can be accessed anywhere in the script.

-> $_GET is an associative array containing data from a GET request.

-> $_POST is an associative array containing data from a POST request.

-> $_REQUEST is an associative array containing data from both GET and POST requests. It should only be used if you don’t care which method was used.

-> The array keys in the PHP request superglobals are set by the name attributes in the HTML form, which need to be unique.

-> The action attribute is used to specify which file should handle data from the form request.


------------------------------------
I.Booleans and Comparison Operators
------------------------------------

-----------------
1.Introduction
----------------

Have you ever noticed that hyperlinks change color after you click them? If the link has been clicked, then the web browser renders it in purple, rather than blue. The programming concept that makes this possible is called conditionals.

This might be a simple example, but conditionals underlie the complex behavior of computer programs from Gmail, to Mario games, to Microsoft Office. Conditionals make it possible for programs to decide how to react to a wide variety of situations.

But computers aren’t intelligent—in order for them to make decisions they have to be programmed with a set of rules to follow.

In this lesson, we’ll explore how we write programs that can make decisions with conditionals.

![Alt text](https://content.codecademy.com/courses/learn-cpp/conditionals-and-logic/streetsign.gif)

---------------------
2.If Statements
--------------------

We’re going to learn about a specific type of conditional called an if statement. An if statement follows this basic structure:

    if (/*some condition*/) {
     // Do something...
    }

The parentheses hold the condition we want the computer to check. If the condition is true, the code inside the code block ({ }) will run; if it’s not true, the code will not run.

The foundation of any conditional is the boolean data type. A boolean can have one of two values: TRUE or FALSE. Note that these are the words without quotation marks—the string "TRUE" is not the same as the boolean value TRUE. These values are not case sensitive, but we follow the convention of making them uppercase.

If we wanted to write code to approximate our hyperlink example from the previous exercise, we might write something like this:

    $is_clicked = TRUE;
    if ($is_clicked) {
      $link_color = "purple";
      echo $link_color;
    }

In the code above, we ask the computer to check the $is_clicked variable as the condition. If its value is TRUE, the value of $link_color will be assigned "purple" and printed.

In the code above, were our condition not met, we’d skip over the code turning the link purple, but what should we do instead? If the link has been clicked, the color should be purple, otherwise it should be blue. We can include a block of code to run when the condition is not met with the keyword else:

    $is_clicked = FALSE;
    if ($is_clicked) {
      $link_color = "purple";
      echo $link_color;
    } else {
      $link_color = "blue";
      echo $link_color;
    }

We changed the value of $is_clicked to FALSE so that the if block will not run. Rather, the else block will run and blue will be printed to the terminal. 


--------------------------
3.Comparison Operators
--------------------------

The condition, or expression, in an if statement can hold a boolean value—like TRUE or FALSE, a variable assigned to one of those values, or an expression that evaluates to TRUE or FALSE.

Just as we can represent a value of five with 5 or with an expression that evaluates to five e.g. 3 + 2, we can write expressions that evaluate to TRUE or FALSE. Comparison operators evaluate a relationship between two operands and return a boolean value.

The less than operator (<) will return TRUE if the left operand is less than the right operand and FALSE if it’s not:

    1 < 10; // Evaluates to: TRUE
    11 < 3; // Evaluates to: FALSE

The less than or equal to operator (<=) will return TRUE if the left operand is less than or equal to the right operand and FALSE if it’s not:

    1 <= 10; // Evaluates to: TRUE
    4 <= 4; // Evaluates to: TRUE
    18 <= 2; // Evaluates to: FALSE

The greater than operator (>) will return TRUE if the left operand is greater than the right operand and FALSE if it’s not. And the greater than or equal to operator (>=) will return TRUE if the left operand is greater than or equal to the right operand and FALSE if it’s not:

    1 > 10; // Evaluates to: FALSE
    11 > 3; // Evaluates to: TRUE
    1 >= 10; // Evaluates to: FALSE
    11 >= 11; // Evaluates to: TRUE
    54 >= 10; // Evaluates to: TRUE
    
---------------------------------------
4.Identical and Not Identical Operators
---------------------------------------

In this exercise we’re going to learn a few more comparison operators and see how we can use them to compare more than just number values.

The identical operator (===) will return TRUE if the left operand is the same as the right operand and FALSE if it’s not:

    $num = 5;
    $num === 5; // Evaluates to: TRUE
    10 === 10; // Evaluates to: TRUE
    $num === 20; // Evaluates to: FALSE

When we think about comparing two values, we’ll need to think like a computer. Are "hello" and "Hello" the same?

    $greeting = "hello";
    $greeting === "hello"; // Evaluates to: TRUE
    "hello" === "hel" . "lo";   // Evaluates to: TRUE
    $greeting === "HELLO"; // Evaluates to: FALSE

The not identical operator (!==) will return TRUE if the two operators are different and FALSE if they’re the same:

    $num = 5;
    $num !== 5; // Evaluates to: FALSE
    10 !== 10; // Evaluates to: FALSE
    $num !== 20; // Evaluates to: TRUE
 
    $greeting = "hello";
    "hello" !== "hello"; // Evaluates to: FALSE
    $greeting !== "HELLO"; // Evaluates to: TRUE

When looking through PHP code, you may encounter another operator—the equal operator (==). Like the identical operator, the equal operator will return TRUE if the left operand is the same as the right operand and FALSE if it’s not. But the equal operator is less strict than the identical operator and can have some hard to predict results, so we prefer to only use the identical operator. 


------------------------------
5.Elseif Statements
------------------------------

So far, we’ve been writing conditionals that can only handle one condition. If that condition is met, we do one thing, otherwise we do something else. This only allows us one or two courses of action. But programs can be far more complex.

Consider letter grades on a school assignment:

    If the grade is less than 60, it’s an F
    Or else, if the grade is less than 70, it’s a D.
    Or else, if the grade is less than 80, it’s a C.
    Or else, if the grade is less than 90, it’s a B.
    Or else, it’s an A.

We can write conditionals with multiple if statements using the elseif construction. The computer will continue through each condition until it finds a condition which is met or gets to the end—whichever comes first.

Let’s implement our letter grades example in code:

    $grade = 88;
    if ($grade < 60) {
      echo "You got an F";
    } elseif ($grade < 70) {
      echo "You got a D";
    } elseif ($grade < 80) {
      echo "You got a C";
    } elseif ($grade < 90) {
      echo "You got a B";
    } else {
      echo "You got an A";
    }

In the code above, $grade has a value of 88. The computer will check each condition until one is met and run that block of code. When it gets to the condition $grade < 90, it evaluates to TRUE. That code block executes, and You got a B is logged to the terminal.

Notice that the order of our conditionals is important. The grade 55 would satisfy the condition $grade < 90, but it meets the condition intended for it, $grade < 60 first. What if the elseif statements were in a different order?

    $grade = 55;
    if ($grade < 90) {
      echo "You got a B";
    } elseif ($grade < 80) {
      echo "You got a C";
    } elseif ($grade < 70) {
      echo "You got a D";
    } elseif ($grade < 60) {
      echo "You got an F";
    } else {
      echo "You got an A";
    }

The code above will output You got a B to the terminal since the computer will run the first TRUE condition. We need to take care when constructing our conditionals that they have the outcome we want.

Note: you may encounter the keywords else if with a space separating the two words. In many situations, else if will work the same way as elseif. Since elseif works more universally, that’s what we choose to use. 


-------------------------
6.Switch Statement
---------------------------

We often want to compare a value, expression, or variable against many different possible values and run different code depending on which it matches. We can use a series of if/elseif statements which use the identical operator (===) or we can use a switch statement—an alternate syntax.

We wrote some code with if/elseif statements to print a string based on a student’s letter grade:

    if ($letter_grade === "A"){
      echo "Terrific";
    } elseif ($letter_grade === "B") {
      echo "Good";
    } elseif ($letter_grade === "C") {
      echo "Fair";
    } elseif ($letter_grade === "D") {
      echo "Needs Improvement";
    } elseif ($letter_grade === "F") {
      echo "See me!";
    } else {
      echo "Invalid grade"; 
    }

Since this code involves a series of comparisons, it’s ripe for a switch statement! Let’s see it refactored with switch:

    switch ($letter_grade){
      case "A":
        echo "Terrific";
        break;
      case "B":
        echo "Good";
        break;
      case "C":
        echo "Fair";
        break;
      case "D":
        echo "Needs Improvement";
        break;
      case "F":
        echo "See me!";
        break;
      default:
        echo "Invalid grade"; 
    }

We begin the keyword switch followed by the value (or expression) we’ll be comparing—in this case, $letter_grade. We provide possible matches for the expression with the keyword case, the potential matching value, and the colon. For each case, we provide code that should run if that case matches. After each case, we include the keyword break to break out of the switch statement. We can provide a default that should run if none of the provided cases match.

A switch statement is a good example of code that might be preferable not because it’s shorter, but rather because it clearly indicates the purpose of the code; when looking at a switch statement we can quickly identify the important aspects of the code; this makes it easier to understand, extend, and debug.


----------------------------
7.Switch Statements: Fall through
-------------------------------

In the previous exercise, we taught you to use the keyword break after the block for each case. Without the keyword break, not only will the first matching case’s block run, but so will all the code in the subsequent cases! This is known as fall through. The keyword break tells the computer to break out of the switch statement, without it, it will fall through the rest of the switch executing all the code until it reaches a break, a return, or the end of the statement:

    $letter = "a";
    switch ($letter) {
      case "a":
        echo "a";
      case "b":
        echo "b";
      case "c":
        echo "c";
      case "d":
        echo "d";
    }

The code above will output abcd. Only the first case (case "a") actually matches the value of $letter, but since the above code doesn’t have any breaks all of the code in the switch will execute. Fall through may seem like a drag, but it can be useful when we want multiple cases to execute the same code:

    switch ($day_of_week) {
      case "Monday":
      case "Tuesday":
        echo "Just getting started!";
        break;
      case "Wednesday":
        echo "Humpday!";
        break;
      case "Thursday":
      case "Friday":
        echo "Almost the weekend!";
        break;
      case "Saturday":
      case "Sunday":
        echo "Enjoy!";
        break;
    }

In the code above, we use fall through to our advantage by placing cases that should execute the same code next to each other and having them share a code block. So, for example, if $day_of_week has the value "Monday" or "Tuesday", the string "Just getting started!" will be printed.

It’s ok if you don’t find fall through useful in your own code. But knowing how to use it should remind you that it exists and that you need those breaks!

-------------------------
8.Ternary Operator in PHP
--------------------------

PHP offers a short-hand syntax to conditionally return a value. Before learning it, let’s consider some example code:

    $isClicked = FALSE;
    if ( $isClicked ) {
      $link_color = "purple";
    } else {
      $link_color = "blue";
    }

In the code above, our condition checks the value of the $isClicked variable. If it’s TRUE we assign $link_color to "purple", otherwise we assign it the value "blue". Our code is somewhat repetitive—the code in each code block is only slightly different.

A ternary operator (?:) is another conditional operator. It takes three operands and returns a value:

    The first operand is a condition to check. This is followed by a question mark ?.
    The second operand is an expression to return if the condition is TRUE. This is followed by a colon (:).
    The third operand is an expression to return if the condition is FALSE.

Let’s see our previous example refactored with the ternary operator:

    $isClicked = FALSE;
$link_color = $isClicked ? "purple" : "blue";

The ternary operator allows us to write fewer lines of code while maintaining readability.

Note that code in the expression will be executed, but the intended use of the ternary is to conditionally return a value not to execute code.


----------------------------
9.Truthy and Falsy
-----------------------------

So far in our conditionals, we’ve been dealing with expressions that would evaluate to boolean values in any context. In practice, any value or expression in the condition will be converted to TRUE or FALSE. Take a look at the following real, working PHP code:

    if ("What's going on?"){
      echo "Let us explain…";
    } 
    // Prints: Let us explain…

In the above code, the condition checks the truthiness of the string "What's going on?". The computer converts this value to TRUE and therefore executes the code in the block. We sometimes refer to code that will be converted to TRUE as truthy and code that will be converted to FALSE as falsy since they aren’t actually equivalent to those boolean values, but they will be treated as such in certain contexts. Most values and expressions are treated as truthy, so we’ll focus on those that are falsy:

    Empty strings
    null
    an undefined or undeclared variable
    an empty array
    the number 0
    the string "0"

Let’s see this in action:

    if ("") {
      echo "this will not print";
    } elseif (null) {
      echo "this will not print";
    } elseif ([]) {
      echo "this will not print";
    } elseif (0) {
      echo "this will not print";
    } elseif ("0") {
      echo "this will not print";
    } else {
      echo "Finally!";
    }

Since none of the conditions above hold truthy values, the code will print Finally!. 

--------------------------
10.User Input: readline()
----------------------------

The outcomes of programs we’ve been writing so far have been predetermined. Unless we manually change our code, it will produce the same results each time it’s run. But this isn’t very realistic. Programs often receive unexpected inputs or results which is why we need conditionals. Conditionals allow us to write flexible programs that handle this variability.

One common reason our programs need to be flexible is when they have user interaction. When we create a website, we don’t know exactly when a user will press a button or exactly what text they’ll input in a form. Writing programs that can handle unique user interaction is a big part of software development.

User interaction isn’t restricted to web development. We can enable user interaction in our terminal-based programs as well.

The built-in readline() function takes a string with which to prompt the user. It waits for the user to enter text into the terminal and returns that value as a string.

    echo "Hi, I'm Aisle Nevertell. What's your name?\n";
    $name = readline(">> ");
    echo "\nNice to meet you, $name";

The code above prints, Hi, I'm Aisle Nevertell. What's your name?. Then, it prints >> to the terminal to prompt the user to type and awaits their input which it will save in the $name variable. If the user entered Alex, for example, the program would next print Nice to meet you, Alex to the terminal.

By incorporating in conditionals, we can take different actions depending on the user input:

    echo "\nWhat's your favorite color?\n";
    $color = readline(">> ");
    if ($color === "green"){
      echo "\nCool, that's my favorite too!";
    } else {
      echo "\nOh, $color is nice, I guess…";
    }

In the code above, we prompt the user to enter their favorite color. If they say our favorite color (green), we give one response, otherwise we give a different response. 

-------------------------
Quick Review I
-------------------------


-> Conditionals make it possible for programs to decide how to react to a wide variety of situations.

-> if statements allow us to run a block of code if a condition is met.

-> The boolean data type is either the value TRUE or FALSE and is the foundation of programmatic decision making.

-> We use else to include a block of code to run when the condition is not met.

-> Comparison operators evaluate a relationship between two operands and return a boolean value.

    The less than operator (<)
    The less than or equal to operator (<=)
    The greater than operator (>)
    The greater than or equal to operator (>=)
    The Identical operator (===)
    The not identical operator (!==)
    
-> We can write conditionals with multiple if statements using the elseif construction.

->Instead of using a series of if statements when we want to compare a value, expression, or variable against many different possible values and run different code depending on which it matches, we can use a switch statement.

-> The keyword break tells the computer to break out of the switch statement, without it, it will fall through the rest of the switch executing all the code until it reaches a break or the end of the statement.

-> A ternary operator (?:) is shorthand conditional operator. It takes three operands (a condition to check, an expression to return if the condition is TRUE, and an expression to return if the condition is FALSE).

-> Any value or expression inside a condition will be converted to TRUE or FALSE. We consider values that will convert to TRUE to be truthy and values that will convert to FALSE to be falsy.

-> We can get user input from the terminal with the readline() function.

-------------------------------------------
J.Logical Operators and Compound Conditions
------------------------------------------

-------------------------------
1.Nested Conditional Statements
-------------------------------

In the previous lesson, we explored the foundations of making decisions in programming: booleans and conditionals. In this lesson, we’ll deepen the complexity of our programs’ decision-making capabilities—we’ll be able to make programs where each decision made sends our program on a different route where it might encounter additional decisions.

We wrote some code to illustrate our decision-making process when taking an elevator. Read through the code to make sense of the process:

      $is_elevator_here = true;
      $elevator_direction = "down";
      $my_direction = "up";
      $is_button_pushed = false;

      if ($is_elevator_here){
          if ($elevator_direction === $my_direction){
            echo "I'm in the elevator.";
          } else {
              if ($is_button_pushed){
                echo "I'm waiting...!";
              } else {
                  echo "I'm pushing the button.";
              }
         }
      } else {
          if ($is_button_pushed){
              echo "I'm waiting...";
          } else {
              echo "I'm pushing the button.";
          }
       }

Notice that in order to implement this decision-making process with code, we nested conditionals inside each other. This is one way to make more complicated programs. In this lesson, we’ll also learn a new set of operators which will allow us to craft more elaborate decision-making programs. By the end, you’ll be equipped to make powerful, dynamic programs.


---------------------
2.The || Operator
---------------------

Expressions that use logical operators evaluate to boolean values.

The logical operator || takes two different boolean values or expressions as its operands and returns a single boolean value. It returns TRUE if either its left operand or its right operand evaluate to TRUE. We can use || in situations where more than one condition should lead to the same outcome.

    TRUE || TRUE;   // Evaluates to: TRUE

    FALSE || TRUE;  // Evaluates to: TRUE

    TRUE || FALSE;  // Evaluates to: TRUE

    FALSE || FALSE; // Evaluates to: FALSE

Let’s think about an example we might encounter in web development: when requesting a password change for a web application, the password can only be changed by either the user themselves or an administrator.

    $is_admin = FALSE;
    $is_user = TRUE;
    if ($is_admin || $is_user){
      echo "You can change the password";
    }

In the code above, the condition $is_admin || $is_user evaluates to TRUE and "You can change the password" is printed to the terminal. Note that while $is_admin is FALSE, $is_user is TRUE. The || operator is inclusive—it evaluates to TRUE if either or both of the operands are TRUE.

--------------------------
3.The && Operator
------------------------

Often, we’ll encounter situations where we have more than one condition we need satisfied in order to take an action.

The logical && operator returns TRUE only if both of its operands evaluate to TRUE. It returns FALSE if either or both of its operands evaluate to false.

    TRUE && TRUE;    // Evaluates to: TRUE
    FALSE && TRUE;   // Evaluates to: FALSE
    TRUE && FALSE;   // Evaluates to: FALSE
    FALSE && FALSE;  // Evaluates to: FALSE

Let’s think about a real-world example: when attempting to withdraw money from an ATM, the account holder must both provide the correct PIN and have enough money in their account.

    $correct_pin = TRUE;
    $sufficient_funds = TRUE;
    if ($correct_pin && $sufficient_funds){
      echo "You can make the withdrawal.";
    }

The && operator has a higher operator precedence than the || operator. This means that in a complex statement that includes both operators, the computer will evaluate the part of the expression with && first:

    TRUE || TRUE && FALSE // Evaluates to: TRUE

If we want to control the order in which the expression is evaluated, we can use parentheses for force the order:

    (TRUE || TRUE) && FALSE // Evaluates to: FALSE
    
    
------------------------
4.The Not Operator
-----------------------

The logical not operator (!) takes only a right operand. It reverses the boolean value of its operand.

    !TRUE;    // Evaluates to: FALSE
    !FALSE;   // Evaluates to: TRUE

The not operator has very high operator precedence; be sure to use parentheses so that code evaluation happens as intended:

    !10 < 11; // Evaluates to: TRUE
    !(10 < 11);  // Evaluates to: FALSE
    !TRUE || TRUE; // Evaluates to: TRUE
    !(TRUE || TRUE); // Evaluates to: FALSE

The not operator is useful when we only want to take a course of action if a condition is not true. For example, if a user is not logged in, a web application may show a pop-up telling them they must do so to continue.

    $is_logged_in = FALSE; 
    if (!$is_logged_in){
      echo "You must log in to continue.";
    }

We could accomplish this same functionality without using the ! operator, but look at how much more cumbersome that code is:

    $is_logged_in = FALSE; 
    if ($is_logged_in){
     // Do nothing... 
    } else {
      echo "You must log in to continue.";
    }
    
--------------------------------
5.The Xor Operator
----------------------------------

The logical operator xor stands for exclusive or. It takes two different boolean values or expressions as its operands and returns a single boolean value. Unlike regular or which evaluates to TRUE if either its left operand or its right operand evaluate to TRUE, xor evaluates to TRUE only if either its left operand or its right operand evaluate to TRUE, but not both.

    TRUE xor TRUE;   // Evaluates to: FALSE

    FALSE xor TRUE;  // Evaluates to: TRUE

    TRUE xor FALSE;  // Evaluates to: TRUE

    FALSE xor FALSE; // Evaluates to: FALSE

We can use xor to answer either/or questions: Did you wear either glasses or contacts today?

    If neither, the answer is “No”—I didn’t wear glasses nor did I wear contacts. My vision is impaired.
    If I wore both, the answer is “No”—I didn’t wear either glasses or contacts. My vision is impaired.
    If I wore contacts, the answer is “Yes”—I wore contacts, so my vision was corrected.
    If I wore glasses, the answer is “Yes”—I wore glasses, so my vision was corrected. .

Let’s code up this example:

    $is_wearing_glasses = TRUE;
    $is_wearing_contacts = TRUE;

    if ($is_wearing_glasses xor $is_wearing_contacts){
        echo "Your vision is corrected!";
    } else {
        echo "Your vision is impaired.";
    }
    
    
--------------------------
6.Alternate Syntax
--------------------------

An alternate syntax for logical || operator is the or operator, and an alternate syntax for logical && operator is the and operator. These operators have the advantage of making our code more human readable.

    // The or Operator:
    TRUE or TRUE;   // Evaluates to: TRUE
    FALSE or TRUE;  // Evaluates to: TRUE
    TRUE or FALSE;  // Evaluates to: TRUE
    FALSE or FALSE; // Evaluates to: FALSE

    // The and Operator:
    TRUE and TRUE;   // Evaluates to: TRUE
    FALSE and TRUE;  // Evaluates to: FALSE
    TRUE and FALSE;  // Evaluates to: FALSE
    FALSE and FALSE; // Evaluates to: FALSE

The computer treats these operators slightly differently from the symbol operators due to operator precedence. The or and and logical operators have a lower precedence than || and &&.

    TRUE || TRUE && FALSE // Evaluates to: TRUE
    TRUE || TRUE and FALSE // Evaluates to: FALSE

As we mentioned before, we can avoid operator precedence confusion by using parentheses for force the evaluation we want:

    (TRUE || TRUE) && FALSE // Evaluates to: FALSE
    TRUE || (TRUE and FALSE) // Evaluates to: TRUE

Going forward you can use whichever logical operators you prefer, but let’s get some practice with and and or.


-------------------------------
7.Multi-File Programs: include
-------------------------------

Separation of concerns is the programming design principle of organizing code into distinct sections each handling a specific task. It enables us to quickly navigate our code and know where to look if something isn’t working. We’ve seen how functions can allow us to practice separation of concerns—by packaging certain routines in functions, we’re able to write cleaner code. But when programs start to get very long, functions aren’t always enough.

Another way to improve our code and separate concerns is with modularity, separating a program into distinct, manageable chunks where each provides a piece of the overall functionality. Instead of having an entire program located in a single file, code is organized into separate files. Each file is then included in our main program with the keyword include. An include statement will bring the code from a file into the current file and also run the code. It’s as if all the code from that file was written right there. We provide the path to the file to be included as a string.

For example, let’s say we had three files one.php, two.php, and index.php, and we want to include the code from files one.php and two.php inside index.php:

    // one.php
    echo "How are";

    // two.php
    echo " you?";

    // index.php
    echo "Hello! ";
    include "one.php";
    include "two.php";
    // Prints: Hello! How are you?

When we run index.php Hello! How are you? is printed to the terminal. 


----------------------------------
K.Loops
--------------------------------

------------------
1.Intro
----------------

When attempting to repeat code over and over again, it can be monotonous to retype or copy and paste the same code. Worse, inadvertent typos can cause errors in your program.

Consider an example where you want your code to print the all the numbers from 1 to 10. Without loops, this would look something like:

    echo "1\n";
    echo "2\n";
    echo "3\n";
    echo "4\n";
    echo "5\n";
    echo "6\n";
    echo "7\n";
    echo "8\n";
    echo "9\n";
    echo "10";

That’s a lot of typing! And what if you decide later you want to change it to add "The count is currently: " at the beginning of each statement? You would need to copy and paste that into every single line.

Luckily, most programming languages contain a feature, called loops, for repeating code automatically until certain conditions are met. Sometimes the repetition is referred to as iterating and each time the code is executed is considered an iteration. Loops can be used to reduce the number of lines of code while also making it much easier to modify later on.

PHP is no exception and offers several ways to repeat execution of a code block.

This lesson will cover the following PHP loop types:

    while
    do … while
    for
    foreach

Each of these loops contain conditions for stopping execution of the loop. Improper implementation of these conditions can cause an infinite loop and the computer will never stop executing your code block. if it seems like your code is taking too long or never completes, consider refreshing the page and re-examining your loop structure.

[!Alt text](https://content.codecademy.com/courses/php-loops/roundabout.gif)

--------------------------
2.while 
-----------------------

The first PHP loop that we will cover is the while loop. This type of loop continues to iterate as long as its conditional is true.

This code outputs the numbers from 1-10, similar to the previous example:

    $count = 1;
    while ($count < 11)
    {
      echo "The count is: " . $count . "\n";
      $count += 1;
    }

The first time the interpreter encounters this code, it checks the condition. If it evaluates to TRUE, the code block is executed. It then checks the condition again, and if TRUE, executes the code block again. It continues in this fashion until the condition is FALSE.

In this example, the code within the curly braces ({}) executes while the conditional statement within the brackets ($count < 11) is still true. $count starts at a value of 1 so the conditional is true on the first iteration.

The variable $count is incremented by 1 during each iteration of the loop ($count += 1). When $count is equal to 11, the conditional is no longer true and the while loop terminates. Any code after this block is then executed.

---------------------
3.do while
---------------------

A do…while loop is very similar to a while loop. The main difference is that the code block will execute once without the conditional being checked. After the first iteration, it behaves the same as a while loop.

The syntax is slightly different, and the conditional goes at the end of the code block. Our counting to 10 example looks like:

    $count = 1;
    do {
      echo "The count is: " . $count . "\n";
      $count += 1;
    } while ($count < 11);

Unlike the other loop types, the do…while loop requires a semicolon at the end.

In practice, only use this type of loop when you always need the code block to execute at least one time.

For example, if you want to ask a user to guess a secret number, you could use code like:

    <?php
    do {
      $guess = readline("\nGuess the number\n");
    } while ($guess != "42");
    echo "\nYou correctly guessed 42!";

This code asks the user to "Guess the number" and continues asking them until they successfully guess 42.

----------------------
4.for
----------------------

A for loop is commonly used to execute a code block a specific number of times.

    for (#expression 1; #expression 2; #expression 3)
    {
      # code block
    }

The for loop syntax includes 3 expressions:

    The first is evaluated only one time before the first iteration.
    The second is evaluated before each iteration. If it is TRUE, the code block is executed. Otherwise, the loop terminates.
    The third is evaluated after each iteration. Note that expressions 1 and 2 have semicolons after them.

In our counting to 10 example, the syntax becomes:

    for ($count = 1; $count < 11; $count++)
    {
      echo "The count is: " . $count . "\n";
    }

The first expression is $count = 1, this initializes the $count variable to 1.

At each iteration, the second expression ($count < 11) is evaluated. As long as this is TRUE, the code block executes.

The final expression ($count++) executes after every iteration. In this example, $count is being incremented by 1 each iteration.

After 10 iterations, the value of the $count variable is 11. This makes the second expression FALSE and the loop execution terminates.


-----------------------
5.foreach
-----------------------

The foreach loop is used for iterating over an array. The code block is executed for every element in the array and the value of that element is available for use in the code block.

Our counting to 10 example becomes:

    $counting_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
    foreach ($counting_array as $count) {
      echo "The count is: " . $count . "\n";
    }

Here, we are iterating over $counting_array. On each iteration, the current element in the array is assigned to the variable $count.

We can also iterate over dictionary type arrays with keys and values:

    $details_array = ["color" => "blue", "shape" => "square"];
    foreach ($details_array as $detail) {
      echo "The detail is: " . $detail . "\n";
    }

This will print:

The detail is: blue
The detail is: square

But we can change the syntax slightly to get access to the keys as well as the values:

    $details_array = ["color" => "blue", "shape" => "square"];
    foreach ($details_array as $attribute => $detail) {
      echo "The " . $attribute . " is: " . $detail . "\n";
    }

This will print:

The color is: blue
The shape is: square

Since the loop is controlled by the structure of the array, you can encounter some unexpected behavior if you begin modifying the array during the execution of the foreach loop.

-----------------------
6.break and continue
-------------------------

Similar to switch statements, the break keyword can be used to terminate any of the loop types early. In our counting example of a while loop, if we add a conditional and a break statement:

    $count = 1;
    while ($count < 11)
    {
      echo "The count is: " . $count . "\n";
      if ($count === 5) {
        break;
      }
      $count += 1;
    }

The code will now count from 1 to 5 and then stop.

One downside of heavy usage of break statements is that code can become less readable. In this example, a quick glance might give someone the impression that the loop will iterate until $count is 10. In reality, the buried break statement is controlling the final iteration of the loop.

The continue keyword is similar to break except it only ends the current iteration early, not the entire loop. We could use this in our example to skip counting the number 5:

    $count = 1;
    while ($count < 11)
    {
      if ($count === 5) {
        $count += 1;
        continue;
      }
      echo "The count is: " . $count . "\n";
      $count += 1;
    }

Note that we needed to add an extra increment before the continue ($count += 1;) to avoid being caught in an infinite loop.

--------------------------
L.Loops in HTML
--------------------------

Using the traditional loop syntax in PHP with brackets ({}) to open and close code blocks can be used when embedding PHP code in HTML:

    <ul>
    <?php
    for ($i = 0; $i < 2; $i++) {
    ?>
    <li>Duck</li>
    <?php
    }
    ?>
    <li>Goose</li>
    </ul>

However, when adding nested loops, the readability of the code can suffer. To determine where loops end, we have to count and match brackets.

Luckily, PHP offers an alternate syntax which is especially useful when working with HTML. Instead of using an opening bracket ({), we use a colon (:) and instead of using a closing bracket (}), we use a closing keyword and semicolon (;). For the for loop, the closing keyword is endfor. Our duck, duck, goose example becomes:

    <ul>
    <?php
    for ($i = 0; $i < 2; $i++):
    ?>
    <li>Duck</li>
    <?php
    endfor;
    ?>
    <li>Goose</li>
    </ul>

Now, when reading this code, it becomes immediately apparent that the endfor keyword is closing the for loop.


------------------------
Loop Shorthand
-----------------------

We’ve already covered the shorthand for for loops in PHP. The versions for while and foreach loops are very similar.

The only difference is the closing keywords. For a while loop, the closing keyword is endwhile, and for the foreach loop, the closing keyword is endforeach.

Our duck, duck, goose example for the while loop becomes:

    <ul>
    <?php
    $i = 0;
    while ($i < 2):
    ?>
    <li>Duck</li>
    <?php
    $i++;
    endwhile;
    ?>
    <li>Goose</li>
    </ul>

And the same example using foreach becomes:

    <ul>
    <?php
    $array = [0, 1];
    foreach ($array as $i):
    ?>
    <li>Duck</li>
    <?php
    endforeach;
    ?>
    <li>Goose</li>
    </ul>
    

----------------------------
3.Code Block Considerations
-----------------------------

One frequent pattern that we encounter is iterating over an array using a foreach loop and creating HTML elements using the items from the array. The following approach does not work as one might hope:

    <?php
    $array = ["Alice", "Bob", "Charlie"];
    foreach($array as $name): ?>
    <p>$name</p>
    <?php endforeach; ?>

Since we are in HTML mode and not PHP mode when using $name here, it will simply print $name, instead of the corresponding item from the array.

Because of this behavior, it’s important to remember to re-enter PHP mode before using PHP variables. This can be done using the <?php opening and ?> closing tags. If you are going to simply be printing the variable using echo, you can also use the echo shorthand opening tag (<?=).

With this, our example can be fixed like this:

    <?php
    $array = ["Alice", "Bob", "Charlie"];
    foreach($array as $name): ?>
    <p><?=$name?></p>
    <?php endforeach; ?>
    
    
-----------------------------------
M.Introduction to Form Validation
----------------------------------

--------------
1.Intro
--------------

Modern websites require a lot of information to function as intended. Information like our usernames, passwords, “friends”, “likes”, credit card information, and shopping orders all have to be provided by users on the front-end and sent to the web applications’ servers so they can be processed. This information is used to create a personalized experience for the user.

User information is traditionally collected using HTML forms. If you’ve ever entered text in a website, selected from options on a list, or checked boxes and then hit enter or pressed a button, you likely filled out and submitted an HTML form!

In order for the data submitted through forms to be useful, it’s essential that the information is valid—if you were allowed to accidentally submit your last name where your address was expected, your package would never show up!

The process of checking that the information submitted through a form adheres to expectations is called form validation. In this lesson, we’ll explore the different techniques for validating form inputs.

--------------------------------
2.Why Validate Forms?
----------------------------

Most data, once submitted, is stored by a website or web application. It’s stored in a database on the server side. There are important reasons for us to make sure the information that will be stored in the database is accurate.

We want operations that depend on the data to work: Allowing a user to enter an incorrectly formatted email address, either on purpose or by accident, means that we won’t be able to contact that user later. Allowing a user to sign up for an account with a username that is already in use could cause numerous errors down the line. Making sure we collect all the data we need and checking that the data are formatted correctly can save a web application and its users a lot of trouble.

We want to keep our site secure: Unprotected data leaves entry points for malicious actors to hurt our application or our users. Allowing a user to submit a non-secure password means that their account will not be protected. Unprotected forms can also allow bits of code to be injected into our servers. This can potentially leave our users’ sensitive information exposed. The malicious actor could even gain control of our site or corrupt our existing data!


----------------------
3.Regular Expressions
----------------------

Data submitted through forms are stored as strings. Strings are a fundamental data type in computer science representing a series of characters “strung” together. As humans, we can intuitively recognize patterns within strings, and this allows us to catch errors. Try to notice what’s wrong in the following examples:

    ABCDEF2GHIJKLMNOPQRSTUVWXYZ
    My zip code is 9021
    The ct meowed
    <h1> Hello, World! </h2>

In the first example, we had the letters of the alphabet presented in order but interrupted by an out of place 2. In the second, we left off the 5th digit of a famous zip code. In the third, we omitted the “a” from the word cat. In the final example, we wrote some HTML with an <h1> opening tag but an unmatching </h2> closing tag. If you picked up on these mistakes, it’s because your brain has been trained to expect patterns in certain types of data.

Unlike humans, who can get this training passively over time, computers have to be precisely programmed to recognize patterns. To specify patterns for the computer to recognize, we use a special language called _regular expressions_—also known as regex or regexp. A regular expression is a sequence of characters representing a pattern. We can use that pattern to match a string, match parts of a string, confirm that data is formatted acceptably, or even replace parts of strings with different characters.

-------------------------------
4.Client-side Validation: HTML
-------------------------------

The first technique we can use to validate form data is to prevent problematic inputs from being submitted in the first place. This is called client-side validation. The client is the process interacting with the server on behalf of a user—in the case of websites, the web browser is the client. The logic for validating the form is included with the code that displays the form on the user’s device. No interaction with the back-end is required to perform client-side validations.

Since form validation is so common, modern HTML provides some of these validation features built-in. For example, we can use HTML to make parts of a form required and others optional. We can also use HTML to set minimum and maximum values for an input or minimum or maximum lengths for a text input. We can even necessitate that the input match a particular pattern, specified by a regular expression.

If any of the rules laid out in the HTML form validation aren’t followed, the user will not be able to submit their form, and they’ll receive an error message explaining why. With these checks in place, the back-end is less likely to be sent incorrect data. HTML form validation will also benefit the user—the client provides the user immediate feedback, without having to wait for time-consuming communication with the back-end.

Example:

    <!DOCTYPE html>
    <html lang="en" dir="ltr">
      <body>
        <h1>Basic HTML Validation</h1>
        <form action="" method="POST">
          <label for="text">Enter your name here:</label>
            <input id="name" name="name" type="text" required minlength="3" maxlength="100">
          <br><br>
          <label for="number">Enter your age here:</label>
          <input type="number" name="age" id="age" required min="1" max="123">
          <br><br>
            <label for="code">Best place to learn to code: (hint: starts with a "C")</label>
      <input id="code" name="code" type="text" required pattern="[cC]odecademy">
          <br><br>
          <input type="submit" value="Submit">
        </form>
      </body>
    </html>
    
    
    Explanation:
    
        The provided HTML form has three input fields that are required. Try submitting the form without any one of them. Notice now a message appears on the form. We didn’t have to design that ourselves. It’s built into HTML.

        Each input has additional requirements.

        The "name" input requires a text input with a length between 3 and 100.
        The "age" input requires a number value between 1 and 123.
        The "code" input requires an input of either Codecademy or codecademy.

        Try out the form with correct and incorrect inputs for each field.

-------------------------------------
5.Client-side Validation: JavaScript
-------------------------------------

Client-side validation has two main advantages. First, it’s a better experience for the user to be alerted to problematic data immediately rather than having to wait for that information to come back from the server and have to fill out the form again. Second, catching mistakes earlier in the process saves the application time and resources as well. But not all issues can be handled with the built-in HTML validations.

In order to truly customize validation or to perform more complex validations, we can incorporate JavaScript form validations. We can do this by either writing the JavaScript ourselves or by incorporating a JavaScript library. If we have unique requirements for usernames on our site, for example, we’ll have to provide these systems of validation ourselves.

If we’re creating a relatively simple website, it makes sense to code the form validation ourselves or use a simple vanilla JavaScript library—just-validate, for example. But most basic validation libraries will involve directly accessing or manipulating the DOM. This can get tricky when working with a framework that relies on a virtual DOM—like React or Vue. In those situations, it might be best to incorporate a library that works well with your specific framework. For example, the formik library is a lightweight library that simplifies validating forms in a React app.


--------------------------------------------------
N.Introduction to Regular Expressions
-----------------------------------------------

--------------------------
1.Introduction
------------------------

When registering an account for a new social media app or completing an order for a gift online, nearly every piece of information you enter into a web form is validated. Did you enter a properly formatted email including an @ symbol? Did you enter a phone number 10 digits long, with or without -s and parentheses? And then there’s the king of them all — did your new password meet the seemingly growing number of requirements for inclusion (and exclusion) of symbols, digits, and both upper and lower case letters?

While correcting each field in our digital lives for proper format can be a pain, it’s integral to ensuring that our accounts are secure, our packages are successfully delivered, and that we can be contacted by phone and email.

The technology that fuels this verification system on nearly every website and application is the ever reliable, often quirky language of regular expressions, commonly shortened to regex, as we will use here, or regexp (pronunciation is up for debate). A regular expression is a special sequence of characters that describe a pattern of text that should be found, or matched, in a string or document. By matching text, we can identify how often and where certain pieces of text occur, as well as have the opportunity to replace or update these pieces of text if needed.

Regular Expressions have a variety of use cases including:

    -> validating user input in HTML forms
    -> verifying and parsing text in files, code and applications
    -> examining test results
    -> finding keywords in emails and web pages

![Alt text](https://content.codecademy.com/courses/regex/regular_expressions_xkcd_2.png)

-----------------------------
2.Literals
--------------------------

The simplest text we can match with regular expressions are literals. This is where our regular expression contains the exact text that we want to match. The regex a, for example, will match the text a, and the regex bananas will match the text bananas.

We can additionally match just part of a piece of text. Perhaps we are searching a document to see if the word monkey occurs, since we love monkeys. We could use the regex monkey to match monkey in the piece of text The monkeys like to eat bananas..

Not only are we able to match alphabetical characters — digits work as well! The regex 3 will match the 3 in the piece of text 34, and the regex 5 gibbons will completely match the text 5 gibbons!

Regular expressions operate by moving character by character, from left to right, through a piece of text. When the regular expression finds a character that matches the first piece of the expression, it looks to find a continuous sequence of matching characters.


-------------------------
3.Alternation
-----------------------

Do you love baboons and gorillas? You can find either of them with the same regular expression using alternation! Alternation, performed in regular expressions with the pipe symbol, |, allows us to match either the characters preceding the | OR the characters after the |. The regex baboons|gorillas will match baboons in the text I love baboons, but will also match gorillas in the text I love gorillas.

Are you thinking about how to match the whole piece of text I love baboons or I love gorillas? We will get to that later on!

---------------------------
4.Character Sets
-----------------------------

Spelling tests may seem like a distant memory from grade school, but we ultimately take them every day while typing. It’s easy to make mistakes on commonly misspelled words like consensus, and on top of that, there are sometimes alternate spellings for the same word.

Character sets, denoted by a pair of brackets [], let us match one character from a series of characters, allowing for matches with incorrect or different spellings.

The regex con[sc]en[sc]us will match consensus, the correct spelling of the word, but also match the following three incorrect spellings: concensus, consencus, and concencus. The letters inside the first brackets, s and c, are the different possibilities for the character that comes after con and before en. Similarly for the second brackets, s and c are the different character possibilities to come after en and before us.

Thus the regex [cat] will match the characters c, a, or t, but not the text cat.

The beauty of character sets (and alternation) is that they allow our regular expressions to become more flexible and less rigid than by just matching with literals!

We can make our character sets even more powerful with the help of the caret ^ symbol. Placed at the front of a character set, the ^ negates the set, matching any character that is not stated. These are called negated character sets. Thus the regex [^cat] will match any character that is not c, a, or t, and would completely match each character d, o or g.


--------------------
5.Wild for Wildcards
--------------------

Sometimes we don’t care exactly WHAT characters are in a text, just that there are SOME characters. Enter the wildcard .! Wildcards will match any single character (letter, number, symbol or whitespace) in a piece of text. They are useful when we do not care about the specific value of a character, but only that a character exists!

Let’s say we want to match any 9-character piece of text. The regex ......... will completely match orangutan and marsupial! Similarly, the regex I ate . bananas will completely match both I ate 3 bananas and I ate 8 bananas!

What happens if we want to match an actual period, .? We can use the escape character, \, to escape the wildcard functionality of the . and match an actual period. The regex Howler monkeys are really lazy\. will completely match the text Howler monkeys are really lazy..

-------------------------
6.Ranges
-------------------------

Character sets are great, but their true power isn’t realized without ranges. Ranges allow us to specify a range of characters in which we can make a match without having to type out each individual character. The regex [abc], which would match any character a, b, or c, is equivalent to regex range [a-c]. The - character allows us to specify that we are interested in matching a range of characters.

The regex I adopted [2-9] [b-h]ats will match the text I adopted 4 bats as well as I adopted 8 cats and even I adopted 5 hats.

With ranges we can match any single capital letter with the regex [A-Z], lowercase letter with the regex [a-z], any digit with the regex [0-9]. We can even have multiple ranges in the same character set! To match any single capital or lowercase alphabetical character, we can use the regex [A-Za-z].

Remember, within any character set [] we only match one character.

------------------------------
7.Shorthand Character Classes
------------------------------

While character ranges are extremely useful, they can be cumbersome to write out every single time you want to match common ranges such as those that designate alphabetical characters or digits. To alleviate this pain, there are shorthand character classes that represent common ranges, and they make writing regular expressions much simpler. These shorthand classes include:

    \w: the “word character” class represents the regex range [A-Za-z0-9_], and it matches a single uppercase character, lowercase character, digit or underscore
    \d: the “digit character” class represents the regex range [0-9], and it matches a single digit character
    \s: the “whitespace character” class represents the regex range [ \t\r\n\f\v], matching a single space, tab, carriage return, line break, form feed, or vertical tab

For example, the regex \d\s\w\w\w\w\w\w\w matches a digit character, followed by a whitespace character, followed by 7 word characters. Thus the regex completely matches the text 3 monkeys.

In addition to the shorthand character classes \w, \d, and \s, we also have access to the negated shorthand character classes! These shorthands will match any character that is NOT in the regular shorthand classes. These negated shorthand classes include:

    \W: the “non-word character” class represents the regex range [^A-Za-z0-9_], matching any character that is not included in the range represented by \w
    \D: the “non-digit character” class represents the regex range [^0-9], matching any character that is not included in the range represented by \d
    \S: the “non-whitespace character” class represents the regex range [^ \t\r\n\f\v], matching any character that is not included in the range represented by \s

-----------------------------
8.Grouping
-----------------------------

Remember when we were in love with baboons and gorillas a few exercises ago? We were able to match either baboons or gorillas using the regex baboons|gorillas, taking advantage of the | symbol.

But what if we want to match the whole piece of text I love baboons and I love gorillas with the same regex? Your first guess might be to use the regex I love baboons|gorillas. This regex, while it would completely match the string I love baboons, would not match I love gorillas, and would instead match gorillas. This is because the | symbol matches the entire expression before or after itself.

Grouping to the rescue! Grouping, denoted with the open parenthesis ( and the closing parenthesis ), lets us group parts of a regular expression together, and allows us to limit alternation to part of the regex.

The regex I love (baboons|gorillas) will match the text I love and then match either baboons or gorillas, as the grouping limits the reach of the | to the text within the parentheses.

These groups are also called capture groups, as they have the power to select, or capture, a substring from our matched text.

    Example:
    
        # Possible Solution
        # Regex: (puppies|kitty cats) are my favorite!
        

-------------------------------
9.Quantifiers - Fixed
-----------------------------

Here’s where things start to get really interesting. So far we have only matched text on a character by character basis. But instead of writing the regex \w\w\w\w\w\w\s\w\w\w\w\w\w, which would match 6 word characters, followed by a whitespace character, and then followed by more 6 word characters, such as in the text rhesus monkey, is there a better way to denote the quantity of characters we want to match?

The answer is yes, with the help of quantifiers! Fixed quantifiers, denoted with curly braces {}, let us indicate the exact quantity of a character we wish to match, or allow us to provide a quantity range to match on.

    \w{3} will match exactly 3 word characters
    \w{4,7} will match at minimum 4 word characters and at maximum 7 word characters

The regex roa{3}r will match the characters ro followed by 3 as, and then the character r, such as in the text roaaar. The regex roa{3,7}r will match the characters ro followed by at least 3 as and at most 7 as, followed by an r, matching the strings roaaar, roaaaaar and roaaaaaaar.

An important note is that quantifiers are considered to be greedy. This means that they will match the greatest quantity of characters they possibly can. For example, the regex mo{2,4} will match the text moooo in the string moooo, and not return a match of moo, or mooo. This is because the fixed quantifier wants to match the largest number of os as possible, which is 4 in the string moooo.


    Example:
    
    # Possible Solution
    # Regex: squea{3,5}k
    
    Match strings:     
    
    🚫squeaaak
    🚫squeaaaak
    🚫squeaaaaak

--------------------------
10.Quantifiers - Optional
--------------------------

You are working on a research project that summarizes the findings of primate behavioral scientists from around the world. Of particular interest to you are the scientists’ observations of humor in chimpanzees, so you whip up some regex to find all occurrences of the word humor in the documents you have collected. To your dismay, your regex misses the observations of amusement written by scientists hailing from British English speaking countries, where the spelling of the word is humour. Optional quantifiers to the rescue!

Optional quantifiers, indicated by the question mark ?, allow us to indicate a character in a regex is optional, or can appear either 0 times or 1 time. For example, the regex humou?r matches the characters humo, then either 0 occurrences or 1 occurrence of the letter u, and finally the letter r. Note the ? only applies to the character directly before it.

With all quantifiers, we can take advantage of grouping to make even more advanced regexes. The regex The monkey ate a (rotten )?banana will completely match both The monkey ate a rotten banana and The monkey ate a banana.

Since the ? is a metacharacter, you need to use the escape character in your regex in order to match a question mark ? in a piece of text. The regex Aren't owl monkeys beautiful\? will thus completely match the text Aren't owl monkeys beautiful?.

    Example:
    
    # Possible Solution
    # Regex: \d ducks? for adoption\?
    
--------------------------------------
11.Quantifiers - 0 or More, 1 or More
---------------------------------------

In 1951, mathematician Stephen Cole Kleene developed a system to match patterns in written language with mathematical notation. This notation is now known as regular expressions!

In his honor, the next piece of regular expressions syntax we will learn is known as the Kleene star. The Kleene star, denoted with the asterisk *, is also a quantifier, and matches the preceding character 0 or more times. This means that the character doesn’t need to appear, can appear once, or can appear many many times.

The regex meo*w will match the characters me, followed by 0 or more os, followed by a w. Thus the regex will match mew, meow, meooow, and meoooooooooooow.

Another useful quantifier is the Kleene plus, denoted by the plus +, which matches the preceding character 1 or more times.

The regex meo+w will match the characters me, followed by 1 or more os, followed by a w. Thus the regex will match meow, meooow, and meoooooooooooow, but not match mew.

Like all the other metacharacters, in order to match the symbols * and +, you need to use the escape character in your regex. The regex My cat is a \* will completely match the text My cat is a *.

-------------------------------
12.Anchors
-------------------------------

When writing regular expressions, it’s useful to make the expression as specific as possible in order to ensure that we do not match unintended text. To aid in this mission of specificity, we can use the anchor metacharacters. The anchors hat ^ and dollar sign $ are used to match text at the start and the end of a string, respectively.

The regex ^Monkeys: my mortal enemy$ will completely match the text Monkeys: my mortal enemy but not match Spider Monkeys: my mortal enemy in the wild or Squirrel Monkeys: my mortal enemy in the wild. The ^ ensures that the matched text begins with Monkeys, and the $ ensures the matched text ends with enemy.

Without the anchor tags, the regex Monkeys: my mortal enemy will match the text Monkeys: my mortal enemy in both Spider Monkeys: my mortal enemy in the wild and Squirrel Monkeys: my mortal enemy in the wild.

Once again, as with all other metacharacters, in order to match the symbols ^ and $, you need to use the escape character in your regex. The regex My spider monkey has \$10\^6 in the bank will completely match the text My spider monkey has $10^6 in the bank.

    Example:
    
    # Possible Solution
    # Regex: ^penguins are cooler than regular expressions$
    
    
-------------------
Quick Review N
-------------------

Do you feel those regular expression superpowers coursing through your body? Do you just want to scream ah+ really loud? Awesome! You are now ready to take these skills and use them out in the wild. Before beginning your adventures, let’s review what we’ve learned.

    -> Regular expressions are special sequences of characters that describe a pattern of text that is to be matched
    
    -> We can use literals to match the exact characters that we desire
    
    -> Alternation, using the pipe symbol |, allows us to match the text preceding or following the |
    
    -> Character sets, denoted by a pair of brackets [], let us match one character from a series of characters
    
    -> Wildcards, represented by the period or dot ., will match any single character (letter, number, symbol or whitespace)
    
    -> Ranges allow us to specify a range of characters in which we can make a match
    
    -> Shorthand character classes like \w, \d and \s represent the ranges representing word characters, digit characters, and whitespace characters, respectively
    
    -> Groupings, denoted with parentheses (), group parts of a regular expression together, and allows us to limit alternation to part of a regex
    
    -> Fixed quantifiers, represented with curly braces {}, let us indicate the exact quantity or a range of quantity of a character we wish to match
    
    -> Optional quantifiers, indicated by the question mark ?, allow us to indicate a character in a regex is optional, or can appear either 0 times or 1 time
    
    -> The Kleene star, denoted with the asterisk *, is a quantifier that matches the preceding character 0 or more times
    
    -> The Kleene plus, denoted by the plus +, matches the preceding character 1 or more times
    
    -> The anchor symbols hat ^ and dollar sign $ are used to match text at the start and end of a string, respectively

-------------------------------------
O.Introduction to PHP Form Validation
-------------------------------------

------------------------
1.Introduction
------------------------

In this lesson, we’ll be using PHP to handle user input submitted through HTML forms. We’ll be performing form validations on the submitted data in order to protect our website and its users.

Websites and applications in production nearly always use front-end validations (HTML and JavaScript validations done on the client-side), but these validations are designed to provide a better user experience—NOT for security. A user could circumvent front-end validation by intentionally or accidentally turning off JavaScript in their browser. We also need to protect against man-in-the-middle attacks, where a malicious actor changes data after it has been submitted by the client.

The back-end should never trust the data it receives from the client. Either intentionally or not, bad data from the client has the potential to expose sensitive information, corrupt our data, or significantly slow down our server. In this lesson, we’ll be working with forms with no front-end validations in place; this will simulate the untrustworthy nature of client-side validation.

We’ll be using PHP to handle the logic to receive POST requests, validate the data, store the data in the back-end, and display meaningful feedback to the user.


-------------------
2.Form Handling
-------------------

Throughout this lesson, we’ll be using a PHP file to present an HTML form to users. We’ll be using the POST method attribute for more secure input submission. This means all the data submitted will be available in the superglobal associative array: $_POST.

In order for the user’s input to be included in the $_POST array, we provide a name attribute within the HTML. After submitting the form, this name will be the key in the $_POST array and the user’s input will be the value assigned to that key.

    <form method="post" action="">
    Your Favorite Programming Language: <input type="text" name="language">
    <input type="submit" value="Submit Language">
    </form>

Above we have an HTML form with a method of "post". We could provide an alternate URL for users to navigate to after submitting their form (eg. action="some_page.php"). Since we want users to have the opportunity to submit the form again if they have errors, we’ll leave the action as an empty string—this means that once it’s submitted, users will be served the same PHP file that originally served them the form. Our form contains an input assigned the name "language". If a user entered “PHP” (as we would assume…) into the language input of the above form and then submitted the form, their URL would not change. However, within the PHP code, the $_POST array would contain a key => value pair of "language" => "PHP".

    echo $_POST["language"]; // Prints: PHP


-------------------
3.Simple Validation
--------------------

In the previous exercise, we simply displayed the user input we received. Now we want to provide the user with feedback if their input isn’t correct. We’ll validate (confirm the correctness of) the data we receive. If the input is deemed invalid, we’ll want to give the user meaningful feedback so that they can correct their mistake and attempt to submit the form again.

We’ll need to make several modifications to the PHP file that we use to serve our form to users:

    -> Add PHP code to check the validity of a user’s input if the form has been submitted.
    -> Add an HTML element to display an error message to the user if their submission is not valid.
    -> Fill each field in the form with the user’s previously submitted input.

Our third task has to do with creating an improved user experience. Have you ever had to refill every field in a form after submitting it incorrectly? It’s so frustrating! By filling in the user’s submitted values, they’ll be able to quickly correct any fields with errors without having to start over from scratch. To accomplish this, we’ll assign each of the HTML form element’s value attribute—aside from the "submit" input itself—to the data submitted by the user for each field.

For the purposes of this exercise, let’s assume that “PHP” is the only valid submission for the user’s favorite language. Here’s how we might update our form from the previous exercise to accomplish the three tasks above:

    <?php
    $validation_error = "";
    $user_language = "";

    if ($_SERVER["REQUEST_METHOD"] === "POST") {
    $user_language = $_POST["language"];
      if ($user_language != "PHP") {
        $validation_error = "* Your favorite language must be PHP!";
      } 
    }
    ?>

    <form method="post" action="">
    Your Favorite Programming Language: <input type="text" name="language" value="<?php echo $user_language;?>">
    <p class="error"><?= $validation_error;?></p>
    <input type="submit" value="Submit Language">
    </form>

Let’s walk through the above code.

We first assign $validation_error and $user_language to empty strings. We use these PHP values in our HTML, but, if a user has NOT yet submitted their form, we don’t want these elements to have filled in values.

Remember that we’re validating the form data only AFTER it’s been submitted by the user at least once. To ensure that, we only run our validation code if ($_SERVER["REQUEST_METHOD"] === "POST"), which indicates that the current form has been submitted.

Within our if block, we grab the relevant value from the $_POST array: $_POST["language"]. We assign this value to our $user_language variable. This one step actually accomplishes two things! It gives us an easy way to talk about the value the user submitted to this field, and it also means the value of the HTML element will now be the user’s submission rather than an empty string.

If the value the user submitted is NOT correct, we assign an error message to $validation_error so that this part of the HTML will now give the user important feedback.

-------------------------
4.Basic Data Sanitizing
-------------------------

In the previous exercise, we performed a simple validation to check the user’s input, but we made a mistake by directly displaying the data we received from them. Remember that we must never simply trust the data we receive from the client. In order to protect against innocent but dangerous user mistakes, malicious users, or man-in-the-middle attacks, we need to sanitize the data—transform it into a safe and standardized format. In this exercise, we’ll focus on making data safe to display on the user’s browser.

PHP provides several built-in functions to help with sanitization:

We can use the built-in PHP trim() function to remove any whitespace characters from the beginning or end of a string we receive as form input. Though not a security concern, this can help standardize the data prior to validation.

    $email = "     aisle.nevertell@yahoo.com   ";
    echo trim($email); // Prints: aisle.nevertell@yahoo.com

When we want to display the user’s input within our own HTML, we should first run it through htmlspecialchars(). This built-in function transforms HTML elements into HTML entities (characters that represent HTML elements but won’t display as HTML), so that the PHP interpreter doesn’t recognize them as HTML. This prevents, for example, a man-in-the-middle attack in which malicious HTML is injected into a user’s view of our site.

    $data = "<a href=\"https://www.evil-spam.biz/html/\">Your account has been compromised! Click here to get technical support!!</a>";

    echo htmlspecialchars($data);

    // Prints: &lt;a href=&quot;https://www.evil-spam.biz/html/&quot;&gt;Your account has been compromised! Click here to get technical support!&lt;/a&gt;

Sometimes we will also want to perform custom sanitizations that cannot be accomplished with built-in functions, but we’ll discuss these later in the lesson.

---------------------------------------
5.Basic Sanitization with filter_var()
-------------------------------------

