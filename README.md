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

