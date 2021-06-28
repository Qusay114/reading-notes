# Pirmitives Vs Objects 

### Pirmitive types is basic data types such as :
          -boolean 	    which consumes 1bit from the memory
          -byte		      which consumes 8bits from the memory
          -short,char 	which consumes 16bits
          -int,float	  which consumes 32bits
          -long,double	which consumes 64bits

### Objects types such as :
          -Boolean 		      which consumes 128bit from the memory
          -Byte			        which consumes 128bits from the memory
          -Short,Character 	which consumes 128bits
          -Integer,Float		which consumes 128bits
          -Long,Double		  which consumes 192bits

and their default values are null .



# Exceptions :

exception happens when an error happens in our program , so instead of let the program crashes we use the exception .
in case an error happended we can throw an exception and try catch finally

# Scanners : 
we use the scanner package to get user data  , Example : 

          scanner myObj = new Scanner(System.in);  // Create a Scanner object
          System.out.println("Enter username");
          String userName = myObj.nextLine();  // Read user input 