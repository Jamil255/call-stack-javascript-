# What is Call Stack in JavaScript ?

This article explains the need for a Call Stack in JavaScript. JavaScript uses a Call Stack to track the functions in a program. The call stack works on the Last In, First Out (LIFO) principle. This means that the most recently called function will be the first to be completed. Whenever a function is called, a new frame is added to the top of the stack. Similarly, when the function has completed its execution, its frame is removed from the stack. JavaScript Engine uses Call Stack to track all the functions.
# Purpose of Call Stack in JavaScript

The main purpose of a call stack is to keep track of the order in which functions are called and to manage the context of each function execution. This includes:
# Storing function return addresses:
When a function is called, its return address is pushed onto the call stack. This address is used to know where to return control when the function finishes executing.
 # Managing local variables and arguments:
 Each function execution has its own set of local variables and arguments. The call stack keeps track of these variables and arguments for each function execution so that they can be accessed when needed.
 # Handling recursion:
 Recursion is a technique in which a function calls itself. The call stack is essential for handling recursion, as it keeps track of the nested function calls and allows the program to unwind the recursion stack when all the nested functions have finished executing.
 # Managing memory allocation and deallocation: 
 The call stack helps to manage memory allocation and deallocation by keeping track of which functions are currently active and which ones have finished executing. This information can be used to collect unused memory when it is no longer needed.
 # How Call Stack Works
When a function is called, a new frame is pushed onto the call stack. This frame contains the following information:
The function's code
The function's arguments
The function's local variables
Here's a simple explanation of how the call stack works:
#  Function Calls:  
When a function is called, a new frame is added to the call stack containing information about the function call, such as the function's arguments and local variables.
# Execution:  
The function's code is executed line-by-line. If it calls another function, a new frame is added to the top of the stack, and execution continues in the new function.
# Return:
When a function completes its execution, its frame is popped off the stack, and the control returns to the calling function.
 # code
function greet(name) {
  console.log("Hello, " + name);
}

function welcome() {
  console.log("Welcome to the program!");
}
 
function main() {
  let userName = "John";
  greet(userName);
  welcome();
}

main();
#
In this example, when main() is called, a frame for main() is added to the call stack. Inside main(), greet(userName) is called, so a new frame for greet() is added on top of the stack. After greet() completes, its frame is popped off, and then welcome() is called, adding a new frame for welcome() to the top of the stack. When all functions are complete, the stack becomes empty.
 # Conclusion
In summary, the call stack is a critical component of JavaScript execution that plays a vital role in managing function calls, handling recursion, and optimizing memory usage. Understanding the call stack is crucial for debugging, as it helps you trace the flow of your program's execution. If the stack becomes too large due to excessive function calls, it can lead to a "stack overflow" error.
