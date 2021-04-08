# Learn-PHP

-----------------------------------------
A. Introduction to PHP
-----------------------------------------

How is PHP used in HTML?

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

