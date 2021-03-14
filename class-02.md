# Text 
There many ways to include our text content inside the html code such as :
* Heading tags:
	there is 6 types of headings where is the difference between each of them is the size :
                    <h1> The largest size </h1>  . . . <h6>the smallest size </h6>

* Paragraphs :
	we can write our texts inside the paragraph tag :
		<p> here we can write our paragraph </p>

there is many font weights that we can make our text look like such as :
* Bold  	we can assign it using this attribute: font-weight:bold;
* Italic 	we can assign it using this attribute : font-weight:italic;
* Emphasis 	we can assign it by putting the text inside em tags such as :	
                <em>here we put the text</em>


# Introduce you to how CSS works:

CSS allows you to create rules that control the
way that each individual box (and the contents
of that box) is presented.

And these styles could be :
* for a box :
Width and height
Borders (color, width, and style)
Background color and images
Position in the browser window.

* for a text:
Typeface
Size
Color
Italics, bold, uppercase,
lowercase, small-caps


CSS works by associating rules with HTML elements. These rules govern
how the content of specified elements should be displayed. A CSS rule
contains two parts: a selector and a declaration.

Example:
                p		--> SELECTOR
                {
                color:white;	--> DECLARTION
                }

CSS declarations sit inside curly brackets and each is made up of two
parts: a property and a value, separated by a colon. You can specify
several properties in one declaration, each separated by a semi-colon.

Example:
h1, h2, h3 
{
font-family: Arial;		-->font-family is a property , Arial is a value
color: yellow;
}

# Internal CSS style
We can write the style in our html file inside the head tag using style tag
Example:
                <style>
                body
                {
                color:red;
                }
                </style>

# Use external CSS file
We can create an external css file to write the style inside it
then we can link it to our html file using link tag 
Example:
	<link rel="stylesheet"  href="fileName.css" >

 

# CSS selectors
There are many different types
of CSS selector that allow you to
target rules to specific elements
in an HTML document
 We can target our elements such as :

                p
                {

                }

                #idName
                {

                }

                .className
                {

                }




# Modify Html content using JS
In order to make our web pages more interactive , 
we use JavaScript language it allows us to access and modify the markup codes we used in the web page and that access and modifying it happens in according the actions that the user did in the browser 
such as clicking on a button , filling text boxes or hovers on a link . When an action happens we can access a specific elements by using the id attribute and modify our codes such as adding a paragraph of text after a specific element , change the value of class attributes to tigger new CSS rules for those elements 
or change the size or position of an <img> element . 

In order to modify a part of content we can reload part of the page which it can make the site fell like it is faster to 
load and more like an application , and we can do that by :
* **React**   :Script triggered when user clicks on link
* **Access**  :The link that they clicked on
* **Program** :load the new content that was requested from that link 
* **Access**  :find the element to replace in the page
* **Modify**  :Replace that content with the new content .                                                                                                        

# Script
As for people to be able to do a new skill they learned they will need a series of instructions to guide them to do task,
and in order to make the computer do a specific task we write something called the script which is a series of instructions .
we can write a script by breaking the task into smaller steps:

**1: DEFINE THE GOAL**  : before we start to write the script we need to define the task we want to acheive .

**2: DESIGN THE SCRIPT**: we split the main task into a series of smaller tasks and we can represent that by using a flowchart,then we can write the necessary setps for each individual task

**3: CODE EACH STEP**   : after we wrote the steps , now we need to write them in a way that the computer understands, and we can do that by using a programming language(in our case, it will be JavaScript)


# Syntax of the JavaScript language:
To write a variable it has to start with a letter, dollar sign ($),or an
underscore (_). It must not start
with a number . you can't use a dash(#) or a dot (.) in the variable name .You cannot use keywords or reserved words in the variable name .
All variables are case sensitive, so score and Score would be different variable names.
There is many data types of the variable such as strings and arrays.
Array variables store a list of values , code example :

colors ['white', 'black', ' custom '];
var el document.getElementByld('col ors');
el . textContent = col ors[O];

each value inside the array has an index ,so we can access it and change it .



# HOW HTML, CSS, JAVASCRIPT fit together ?

We should create Html file (Ex:fileName.html) , CSS file (Ex:fileName:css) and JavaScript (Ex:fileName.js) 
, then we should link them .

# CREATING A BASIC JAVASCRIPT 

JavaScript is written in plain text, just like HTML and CSS, so you do not
need any new tools to write a script. This example adds a greeting into an
HTML page. The greeting changes depending on the time of day

* Example:
            var today= new Date();
            var hourNow = today.getHours();
            var greeting;
            if (hourNow > 18) {
            greeting= 'Good evening!';
            else if (hourNow > 12) {
            greeting = ' Good afternoon!';
            else if (hourNow > 0) {
            greeting = 'Good morni ng!';
            else {
            greeting = 'Welcome! ' ;
            document .write( ' <h3>' +greeting + ' </ h3> ');

# LINKING TO A JAVASCRIPT FILE FROM AN HTML PAGE :
There is two ways to to write our javascript scripts :
1. External :
* Example:
            <!DOCTYPE html>
            <html>
            <head>
            <title>Constructive &amp; Co.</ title>
            <link rel ="stylesheet" href="css/ cOl.css" />
            </ head>
            <body>
            <hl>Constructive &amp ; Co. </ hl>
            <script src="js/ add-content.js"></ script>
            <p>For all orders and i nquiries please cal l
            <em>SSS-3344</ em></ p>
            </ body>
            </html>

2. Internal ,We can Write the JavaScript script inside the html file using script tag :
* Example:
            <!DOCTYPE html >
            <html >
            <head>
            <title>Constructive &amp; Co.</title>
            <li nk rel ="stylesheet" href="css/ cOl . css" / >
            </ head>
            <body>
            <hl>Constructive &amp; Co.</hl>
            <script>document.write(' <h3>Welcome !</h3>');
            </script>
            <p>For all orders and inquiries please call
            <em>555-3344</ em></ p>
            </ body>
            </ html >

Programming Statement: A script is a series of instructions that a computer can follow one-by-one.
Each individual instruction or step

* Example:
            var today= new Date{);
            var hourNow = today.getHours{) ;
            var greeting;
            if (hourNow > 18) {
            greeting= 'Good evening';
            else if (hourNow > 12) {
            greeting= 'Good afternoon';
            else if (hourNow > O) {
            greeting 'Good morning';
            else {
            greeting 'Welcome';
            document.write(greeting) ; 

Comments:is somtehing you write to explain your code to make it easier to read and understand , while the compiler will not excute it 
* Example:
  /* Th i s script displays a greeting to the user based upon the current time.
  It is an example from JavaScript & jQuer y book */

Variable is to store the value we want 
Example:
  var variableName = "value";

like any other programming language there is many data types in JavaScript :
 * Numaber : 5 , 10.6 , -5.8
 * String  :"a", "10" , "true"
 * bolean  :true , false



# Comparison and Logical operators:
we use the comparison operators(such as: > , < , >= , <=) to comapre between the any values and it will return true or false:
Example:
5  > 4    it will return true 
10 < 15   it will return false

logical operators( such as: && , || ) :
Example:
(4>3) && (5>4)   it will return true
(4>3) && (5<4)   it will return false
(4<3) || (5>4)   it will return true
(4<3) || (5<4)   it will return false

 # Loops:
We use loops to iterate specific statements as many as I want .
Example:
                var j = 0;
                for(var i =0; i<7; i++)
                {
                    j++;
                }
 here it will iterate 7 times 

we can do it using another loop statement:
Example:

                var j = 0;
                var i = 0;
                while(j<7)
                {
                    j++;

                    i++;
                }
it will do the same exactly
