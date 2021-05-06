# Call Stack :

The call stack is primarily used for function invocation (call).Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.
LIfO: it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

Example on call stack LIFO :

        function firstFunction(){
        throw new Error('Stack Trace Error');
        }

        function secondFunction(){
        firstFunction();
        }

        function thirdFunction(){
        secondFunction();
        }

        thirdFunction();


Stack Overflow : A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

Example :

        stackOverFlow = () => stackOverFlow() ;

        stackOverFlow();



# JavaScript error messages :

Error objects are thrown when runtime errors occur. The Error object can also be used as a base object for user-defined exceptions. See below for standard built-in error types.

## Types of error messages:

* Reference errors: 
This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

Example :

        console.log(foo) // Uncaught ReferenceError: foo is not defined


* Syntax errors:
this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

Example: 

        JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1

* Range errors: 
Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

Example: 

        var foo= []
        foo.length = foo.length -1 // Uncaught RangeError: Invalid array length


* Type errors:
this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.
