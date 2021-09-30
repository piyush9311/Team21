# Functions

## [Defining functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#defining_functions "Permalink to Defining functions")

### [Function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_declarations "Permalink to Function declarations")

A  **function definition**  (also called a  **function declaration**, or  **function statement**) consists of the  [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)  keyword, followed by:

-   The name of the function.
-   A list of parameters to the function, enclosed in parentheses and separated by commas.
-   The JavaScript statements that define the function, enclosed in curly brackets,  `{...}`.

Primitive parameters (such as a number) are passed to functions  **by value**; the value is passed to the function, but if the function changes the value of the parameter,  **this change is not reflected globally or in the calling function**.

If you pass an object (i.e., a non-primitive value, such as  [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)  or a user-defined object) as a parameter and the function changes the object's properties, that change is visible outside the function

    function myFunc(theObject) {
	  theObject.make = 'Toyota';
	}

	var mycar = {make: 'Honda', model: 'Accord', year: 1998};
	var x, y;

	x = mycar.make; // x gets the value "Honda"

	myFunc(mycar);
	y = mycar.make; // y gets the value "Toyota"
	                // (the make property was changed by the function)


### [Function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_expressions "Permalink to Function expressions")

While the function declaration above is syntactically a statement, functions can also be created by a  [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function).

Such a function can be  **anonymous**; it does not have to have a name. For example, the function  `square`  could have been defined as:

    const square = function(number) { return number * number }
	var x = square(4) // x gets the value 16


