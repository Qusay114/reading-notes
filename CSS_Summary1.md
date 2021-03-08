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