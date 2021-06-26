# Java Basics :

### Variables : 
.In Java, there are different types of variables : 

          * String - stores text, such as "Hello". String values are surrounded by double quotes

          * int - stores integers (whole numbers), without decimals, such as 123 or -123

          * float - stores floating point numbers, with decimals, such as 19.99 or -19.99

          * char - stores single characters, such as 'a' or 'B'. Char values are surrounded by single quotes

          * boolean - stores values with two states: true or false

###### Syntax : type variable = value ;


### Operators:

        Operators		Precedence
        postfix	 		expr++ expr--
        unary			++expr --expr +expr -expr ~ !
        multiplicative		* / %
        additive		+ -
        shift			<< >> >>>
        relational		< > <= >= instanceof
        equality		== !=
        bitwise AND		&
        bitwise exclusive OR	^
        bitwise inclusive OR	|
        logical AND		&&
        logical OR		||
        ternary	? :
        assignment		= += -= *= /= %= &= ^= |= <<= >>= >>>=



### Expressions , Statements and Block :
An expression is a construct made up of variables, operators, and method invocations, which are constructed according to the syntax of the language, that evaluates to a single value .

Example: 

        int cadence = 0;
        anArray[0] = 100;
        System.out.println("Element 1 at index 0: " + anArray[0]);

        int result = 1 + 2; // result is now 3
        if (value1 == value2) 
            System.out.println("value1 == value2");

### Control Flow Statements :

The statements inside your source files are generally executed from top to bottom, in the order that they appear. Control flow statements, however, break up the flow of execution by employing decision making, looping, and branching, enabling your program to conditionally execute particular blocks of code. This section describes the decision-making statements (if-then, if-then-else, switch), the looping statements (for, while, do-while), and the branching statements (break, continue, return) supported by the Java programming language.