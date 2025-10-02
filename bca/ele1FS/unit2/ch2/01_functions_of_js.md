**Introduction to Functions:**

**What Are Functions?**  
This is where functions come in. A function is a block of code designed to perform a specific task. You write the steps once, and whenever you want coffee, you just call the function to get it done. Functions help us avoid repetition, organize code, and make tasks easier.

**Why Use Functions?**  
Functions let us:  
•	Organize code by grouping related instructions together.  
•	Avoid repetition by reusing the same code whenever we need it.  
•	Simplify complex tasks by breaking them down into smaller parts.

**How Functions Work ?**  
When you define a function, you create a set of instructions. When you call a function, those instructions are executed. Functions can:  
•	Take inputs (called parameters) to work with different values.  
•	Return a result after performing a task.

**Basic Function Structure and Examples:**  
A function definition has:  
1\.	Function name – the name of the task it performs.  
2\.	Parameters – placeholders for values the function will use.  
3\.	Code block – instructions for the task.  
4\.	Return statement – sends a result back to where the function was called (optional).

**1️⃣ Functions Without Parameters and Without Return Value**  
These are the simplest functions. They perform a task but don’t take any input (parameters) and don’t return a value. Think of them as one-time-use tasks that execute some instructions without giving anything back.  
Example: Greeting Function  
function greet() {  
    console.log("Hello, world\!");  
}

// Calling the function  
greet(); // Output: Hello, world\!  
Explanation: In this example, the greet function doesn’t take any input and simply prints a greeting message to the console. It doesn’t return any value, so it just completes its task and stops.

**2️⃣ Functions With Parameters but Without Return Value**  
This type of function takes inputs (parameters) but does not return a value. Parameters act like placeholders for values that the function uses to perform its task.  
Example: Personalized Greeting Function  
function greetUser(name) {  
    console.log("Hello, " \+ name \+ "\!");  
}

// Calling the function with a parameter  
greetUser("Alice"); // Output: Hello, Alice\!  
Explanation: Here, greetUser takes one parameter, name, and uses it to print a personalized greeting. This function doesn’t return a value; it simply displays the greeting.

**3️⃣ Functions Without Parameters but With a Return Value**  
These functions don’t need any input, but they return a value after performing a task. They’re useful when you want to generate or calculate something without needing any external input.  
Example: Get Current Year Function  
function getCurrentYear() {  
    return new Date().getFullYear();  
}

// Calling the function and storing the return value  
let year \= getCurrentYear();  
console.log("Current year is:", year); // Output: Current year is: 2023 (or the current year)  
Explanation: The getCurrentYear function doesn’t take any parameters. It simply returns the current year by using the Date object. We can then store this return value in a variable to use it as needed.

**4️⃣ Functions With Parameters and With Return Value**  
These functions take inputs (parameters) and return a result after processing those inputs. They’re highly flexible and commonly used for calculations or transformations.  
Example: Addition Function  
function add(a, b) {  
    return a \+ b;  
}

// Calling the function and storing the return value  
let sum \= add(5, 10);  
console.log("The sum is:", sum); // Output: The sum is: 15  
Explanation: Here, the add function accepts two parameters, a and b, adds them together, and returns the result. This type of function is useful for tasks like calculations where you want to pass in values and get a result back.

