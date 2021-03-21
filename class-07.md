# Domain Modeling :

Domain modeling is the process of creating a conceptual model for a specific problem. And a domain model that's articulated well can verify and validate your understanding of that problem.

Example :
	
	let car = function(price , year)
			{
				this.price = price;
				this.year = year;
			}

	let audi = new car(10000 , 2015);
	console.log(audi.price)
	console.log(audi.year)

here in this example it will create a car object with price and year properties ,
then audi will get object of it with price propery value is 10000 and year property value is 2015


# Table :

There are several types of information
that need to be displayed in a grid or
table. For example: sports results, stock
reports, train timetables.
When representing information in a table, you need to think
in terms of a grid made up of rows and columns (a bit like a
spreadsheet).

Example on how to create a table element :

    <table>
    <tr>
    <td>15</td>
    <td>15</td>
    <td>30</td>
    </tr>
    <tr>
    <td>45</td>
    <td>60</td>
    <td>45</td>
    </tr>
    <tr>
    <td>60</td>
    <td>90</td>
    <td>90</td>
    </tr>
    </table>


# Functions, Methods, and Objects :

The new keyword and the object constructor create a blank object , then we can 
add properties and methods .

Example :

	let laptop = new Object();
	laptop.model = 'Hp';
	laptop.ram   = 8;

	laptop.checkSpeed = function()
	{
		if(this.ram >=8)
			return 'high';
		else if(this.ram >=4)
			return 'medium';
		else 
			return 'slow';
	}



you can create instances of the object using the constructor function .

Example:

	let sony = new laptop('sony',16)