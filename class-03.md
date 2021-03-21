# Lists 
There are three types of lists we can use in html :
1. Ordered lists : thery are lists where each item in the list is
numbered. For example, the list might be a set of steps for
a recipe that must be performed in order, or a legal contract
where each point needs to be identified by a section
number .

Example:
	
	```<ol>```
		```<li>```
		```<li>```
	```</ol>```


2. Unordered lists: they are lists that begin with a bullet point
(rather than characters that indicate order).

Example:

	```<ol>```
		```<li>```
		```<li>```
	```</ol>


3. Definition lists : they  are made up of a set of terms along with the
definitions for each of those terms.

Example:  


	```<dl>```
		```<dt>```
		```</dt>```

		```<dd>```
		```</dd>``

		```<dt>```
		```</dt>```

		```<dd>```
		```</dd>``
		
	```</dl>




# Boxes
every elemant in html is considered as a box , and by default the width and height is according to the content of this box , but we can also set the height and the width for it .

Example:

	'''div'''
	'''{'''
	'''width:50%;
	'''heght:100px;
	'''}'''

and we can also set the minimum values for the box 

Example:

	'''div'''
	'''{'''
	'''width-min:50%;
	'''heght-min:100px;
	'''}'''


There are three important properties to control the boxes:

* Padding : we use it to control the space between the content and box border where we can use :

	* padding-top
	* padding-right
	* padding-bottom
	* padding-left

or padding : top-value right-value bottom-value left-value


* border : we use it to control the size , color and the style of the border by using these properties :

	* border-width
	* border-style
	* border-color

or border: width-value style-value color-value ;


* margin : we use it to control the space between the elements(boxes) :
	
	* margin-top
	* margin-right
	* margin-bottom
	* margin-left

or margin : top-value right-value bottom-value left-value



# Array

array is a special type variable to store a list of values .

Example:
	
	'''colors = ['red' , 'green' , 'blue' ] ;'''

and each of these values has an index to access the value and modify it , where the first elememt is 0 and the second element is 1 and so on .

Example:

	'''colors[0] = 'black' ; '''
	'''colors[2] = 'white' ; '''



# Check condition :
	
there is to method to check on a value and if it's true do something :

	* if statement : where it check on a condition and if it's true it will excute the first block and if it's not , then it will excute the second block (else block .)
	
	Example:
	
		if( 5 > 4)
		{
			alert('it excuted the first block');
		}
		else 
		{
			alert('the second block (else block) ' ); 
		}



	* switch statement : it will check if the value is the same as in the case , then it will excute statements inside the case .

	Example:

		switch(5)
		{
			case 4 :  alert('it's not the same value');
				  break;
			
			case 5 :  alert('it's the same value , so it will excute it');
				  break;
	
			default: alert('it will excute the default if the value didn't match any case value');
				 break;
		}




# Loops 

there are three different types of loop :

	* for loop 

	* while loop

	* do while loop 