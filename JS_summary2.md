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

We can Write the JavaScript script inside the html file using script tag 
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



