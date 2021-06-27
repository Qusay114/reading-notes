# Packages and Import : 

### Packages : package is a way to gather a group of classes . 

	package declaration syntax : 
	
	1. Package statment (optional).
	2. Imports (optional).
	3. Class or interface definitions.

### imports : is a way to call a package and use its class in your program .
	
	Example:

	      import javax.swing.JOptionPane;

here are some common imports :

        import java.awt.*;	Common GUI elements.
        import java.awt.event.*;	The most common GUI event listeners.
        import javax.swing.*;	More common GUI elements. Note "javax".
        import java.util.*;	Data structures (Collections), time, Scanner, etc classes.
        import java.io.*;	Input-output classes.
        import java.text.*;	Some formatting classes.
        import java.util.regex.*;	Regular expression classes.


# Loops :
we can define the loop is a way to iterate(excute) a block of code n times .
As every programming langauge has loop statements , we can loop in java using these statements :

* For-Loop : 
In for-loop the nested code(inside the loop) will be excuted as long as the condition is true .

### Syntax:
        for (initialization; Boolean-expression; step) 
          statement;



* While-Loop : 
In while-loop the nested code(inside the loop) will be excuted as long as the condition is true .

### Syntax:
        while (Boolean-expression) 
            statement;

* Do-While-Loop : 
here we excuted the nested code then we check the condition

### Syntax:
        do {
              statement;
          } while (Boolean-expression);
