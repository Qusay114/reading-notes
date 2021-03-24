# Error Handling & Debugging :

Errors, bugs, and therefore debugging are a part of life for a programmer. As the saying goes, if you haven’t made any mistakes, then you aren’t trying hard enough.

Dealing with errors actually involves two very different processes: error handling and debugging. Error handling is a combination of coding and methodology that allows your program to anticipate user and other errors. It allows you to create a robust program. Error handling does not involve weeding out bugs and glitches in your source code, although some of the error handling techniques covered in this chapter can be used to great advantage at the debugging stage. In general, error handling should be part of your overall program plan, so that when you have an error-free script, nothing is going to bring it to a screeching halt. With some sturdy error handling in place, your program should be able to keep running despite all the misuse that your users can—and certainly will—throw at it.

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.

Scope in JavaScript refers to the current context of code, which determines the accessibility of variables to JavaScript. The two types of scope are local and global:

Global variables are those declared outside of a block
Local variables are those declared inside of a block
In the example below, we will create a global variable.

      var creature = "wolf";

We learned that variables can be reassigned. Using local scope, we can actually create new variables with the same name as a variable in an outer scope without changing or reassigning the original value.

In the example below, we will create a global species variable. Within the function is a local variable with the same name. By sending them to the console, we can see how the variable’s value is different depending on the scope, and the original value is not changed.

      // Initialize a global variable
      var species = "human";
      console.log(species);
      function transform() {
        // Initialize a local, function-scoped variable
        var species = "werewolf";
        console.log(species);
      }

      // Log the global and local variable
      console.log(species);

      Output
      human
      werewolf
      human








