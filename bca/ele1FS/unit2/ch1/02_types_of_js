**Types of JavaScript Integration:**

 **Internal vs. External**  
When adding JavaScript to a website, you can choose to include the code in different ways: ***internally*** within the HTML file or externally by linking to a separate JavaScript file. Here’s an overview of each approach:

•	**Definition:** Internal JavaScript is JavaScript code written directly within the HTML file, usually inside the \<script\> tag in the \<head\> or \<body\> section.

•	How It’s Used:  
•	\<html\>  
•	  \<head\>  
•	    \<title\>My Web Page\</title\>  
•	    \<script\>  
•	      function showMessage() {  
•	        alert("Hello, World\!");  
•	      }  
•	    \</script\>  
•	  \</head\>  
•	  \<body\>  
•	    \<button onclick="showMessage()"\>Click Me\!\</button\>  
•	  \</body\>  
•	\</html\>  
•	**Advantages:**

-           Convenient for small scripts or quick changes, as you don’t need to create a separate file.  
-           Useful for prototyping or testing small features directly in the   HTML.  
-          Reduces the number of external files, which can simplify the project structure for very small projects.


•	**Disadvantages:**

- Can make the HTML file cluttered and harder to maintain, especially with longer scripts.  
- Less efficient for larger projects, as the code is embedded in every page that uses it, potentially slowing down load times.


•	**Best for:** Small projects or one-off scripts where you want quick, direct access to JavaScript within the HTML.

**External JavaScript:-**

•	**Definition:** External JavaScript is written in a separate .js file and linked to the HTML using the \<script src="filename.js"\>\</script\> tag. This keeps the JavaScript code and HTML structure separate.

•	How It’s Used:  
1\.	Create an external file:  
2\.	// script.js  
3\.	function showMessage() {  
4\.	  alert("Hello, World\!");  
}  
5\.	Link it in the HTML file:  
6\.	\<html\>  
7\.	  \<head\>  
8\.	    \<title\>My Web Page\</title\>  
9\.	    \<script src="script.js"\>\</script\>  
10\.	  \</head\>  
11\.	  \<body\>  
12\.	    \<button onclick="showMessage()"\>Click Me\!\</button\>  
13\.	  \</body\>  
\</html\>

•	**Advantages:**  
1\.	Keeps HTML files clean and organized, as the JavaScript code is managed separately.  
2\.	Makes code easier to reuse and maintain, especially in larger projects where the same script may be used across multiple pages.  
3\.	Improves load times and caching efficiency; the browser can cache the external .js file, reducing the need to reload it on each page visit.

•	**Disadvantages:**  
1\.	Adds an additional HTTP request for each external file, which can slightly increase initial load time, although this is often offset by caching.  
2\.	Requires organizing multiple files, which might complicate smaller projects.

•	**Best for:** Larger projects, reusable code, or cases where you want to maintain a clean HTML structure and separate your JavaScript files for easier management and caching.

**Choosing Between Internal and External JavaScript:**  
•	Use Internal JavaScript for small, single-page projects or for quick prototyping where the JavaScript code is minimal and doesn’t need to be reused.

•	Use External JavaScript for medium to large projects, or when you plan to reuse the code across multiple pages. This approach is more scalable, organized, and allows for better code maintenance.  
Modern Variable Declarations in JavaScript.

In JavaScript, variables are used to store data that can be referenced and manipulated throughout your code. Think of variables as containers that hold values, which you can use and update as needed. Variables allow you to store everything from numbers and text to complex data like arrays and objects.

**Declaring Variables:**  
In JavaScript, there are three main ways to declare a variable:  
1\.	let – used to declare a variable that can be reassigned.  
2\.	const – used for variables whose values should not change.  
3\.	var – an older way of declaring variables; it’s best avoided in modern JavaScript due to potential scope issues.

**Syntax**  
Here’s how you declare a variable in JavaScript:  
let age \= 25;      // a variable that can be changed later  
const name \= "Sam"; // a constant that cannot be reassigned  
var city \= "New York"; // not recommended for new code

**Basic Program Examples:**  
**Example 1:** Printing Variables to the Console  
The console.log() function is a great way to see the output of your variables in the console. Here’s a simple program that declares a variable and prints it:  
let greeting \= "Hello, World\!";  
console.log(greeting);

Expected Output:  
Hello, World\!  
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_  
**Example 2:** Simple Addition Program  
Let’s declare two variables, add them together, and display the result.  
let number1 \= 10;  
let number2 \= 20;  
let sum \= number1 \+ number2;  
console.log("The sum is: " \+ sum);

Expected Output:  
The sum is: 30  
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_  
**Example 3:** Changing Variable Values  
With let, you can reassign values to a variable. Here’s an example:  
let score \= 50;  
console.log("Initial score:", score);

score \= 75; // reassigning a new value  
console.log("Updated score:", score);

Expected Output:  
Initial score: 50   
Updated score: 75  
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_  
**Example 4:** Working with Constants  
Using const prevents a variable from being reassigned. Here’s an example:  
const pi \= 3.14159;  
console.log("Value of pi:", pi);  
// Trying to reassign will cause an error  
// pi \= 3.14; // Uncommenting this line will cause an error

Expected Output:  
Value of pi: 3.14159  
Note: Attempting to reassign a const variable will produce an error in the console.  
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_  
**Example 5:** Basic String Concatenation  
In JavaScript, you can join strings together using the \+ operator. This is called concatenation.  
let firstName \= "John";  
let lastName \= "Doe";  
let fullName \= firstName \+ " " \+ lastName;

console.log("Full Name:", fullName);

Expected Output:  
Full Name: John Doe  
