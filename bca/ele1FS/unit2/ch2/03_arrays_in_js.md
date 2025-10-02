                                             **Arrays in JS:-**

**Arrays in Javascript:**  
In JavaScript, arrays are a fundamental data type used to store ordered collections of items, whether numbers, strings, objects, or other arrays. Arrays provide a way to organize data and come with a robust set of built-in methods for adding, removing, modifying, and accessing items. Let’s dive into what arrays are, their structure, and a complete overview of array operations.

**1\. What is an Array?**  
An array in JavaScript is a list-like object used to store multiple values under a single variable. Each item in an array is called an element, and each element has an index (position), starting from 0\. Arrays are ideal for managing lists, collections, or groups of related data.  
Example:  
let fruits \= \["apple", "banana", "cherry"\];  
console.log(fruits\[0\]); // Output: "apple"

**2\. Declaring Arrays:**  
Arrays can be created in two main ways:  
1\.	Using square brackets \[\] (most common):  
let numbers \= \[1, 2, 3, 4\];

2\.	Using the Array constructor:  
let colors \= new Array("red", "green", "blue");

**3\. Array Operations:**  
 Adding, Removing, and Accessing Elements  
JavaScript provides numerous methods for manipulating arrays. Here’s a comprehensive list of array operations:

**Adding Elements:**  
1\.	push(): Adds one or more elements to the end of the array.  
	let numbers \= \[1, 2, 3\];  
	numbers.push(4); // Adds 4 to the end  
console.log(numbers); // Output: \[1, 2, 3, 4\]

2\.	unshift(): Adds one or more elements to the beginning of the array.  
	let numbers \= \[1, 2, 3\];  
	numbers.unshift(0); // Adds 0 at the beginning  
console.log(numbers); // Output: \[0, 1, 2, 3\]

**Removing Elements:**  
1\.	pop(): Removes the last element from the array.  
	let fruits \= \["apple", "banana", "cherry"\];  
	fruits.pop(); // Removes "cherry"  
console.log(fruits); // Output: \["apple", "banana"\]

 2\.	shift(): Removes the first element from the array.  
	let fruits \= \["apple", "banana", "cherry"\];  
	fruits.shift(); // Removes "apple"  
console.log(fruits); // Output: \["banana", "cherry"\]

**Modifying and Accessing Elements:**  
1\.	Accessing by Index: Use square brackets to access elements by their index.  
	let colors \= \["red", "green", "blue"\];  
console.log(colors\[1\]); // Output: "green"

 2\.	**The splice() method** in JavaScript is a powerful tool for adding, removing, or replacing elements in an array at specific positions. The syntax of splice looks like this:  
array.splice(start, deleteCount, item1, item2, ...)

**Each parameter has a specific role:**  
1\.	start: The index at which to begin modifying the array.  
2\.	deleteCount: The number of elements to remove, starting from the start index.  
3\.	item1, item2, ... (optional): The elements to add into the array at the start position.

**Example:**  
let colors \= \["red", "green", "yellow", "pink"\];   
colors.splice(1, 2, "Blue");   
console.log(colors); // Output: \["red", "Blue", "pink"\]

4\.	slice(): Returns a shallow copy of a portion of an array without modifying the original array.  
	let numbers \= \[1, 2, 3, 4, 5\];   
	let part \= numbers.slice(1, 3); // Extracts from index 1 to index 3 (exclusive)   
console.log(part); // Output: \[2, 3\]

**4\. Array Searching and Sorting**  
1\.	indexOf(): Returns the first index of a specified element or \-1 if not found.  
	let fruits \= \["apple", "banana", "cherry"\];  
console.log(fruits.indexOf("banana")); // Output: 1

2\.	includes(): Checks if an array contains a specific element.  
	let fruits \= \["apple", "banana", "cherry"\];  
console.log(fruits.includes("banana")); // Output: true

3\.	sort(): Sorts elements in place as strings by default.  
	let letters \= \["b", "a", "c"\];  
	letters.sort();  
console.log(letters); // Output: \["a", "b", "c"\]

4\.	reverse(): Reverses the order of elements in the array.  
	let numbers \= \[1, 2, 3\];  
	numbers.reverse();  
console.log(numbers); // Output: \[3, 2, 1\]

**5\. Array Iteration Methods**  
JavaScript provides powerful methods to iterate over arrays:  
1\.	forEach(): Executes a function once for each array element.  
	let fruits \= \["apple", "banana", "cherry"\];  
	fruits.forEach(fruit \=\> console.log(fruit));  
// Output: "apple", "banana", "cherry"

2\.	**The map() method** in JavaScript creates a new array by applying a specified function to each element of an existing array. It does not modify the original array but instead returns a new array with transformed values based on the function.  
•	**Syntax:**  
array.map((element, index, array) \=\> { return newElement; });  
For each element in the array, the function you provide is executed, and the result of each function call is placed in a new array.  
**Example:**  
let numbers \= \[1, 2, 3\];  
let squared \= numbers.map(num \=\> num \* num);  
console.log(squared); // Output: \[1, 4, 9\]

2\.	filter(): Creates a new array with elements that pass a test.  
	let numbers \= \[1, 2, 3, 4, 5\];  
	let evenNumbers \= numbers.filter(num \=\> num % 2 \=== 0);  
console.log(evenNumbers); // Output: \[2, 4\]

3\.	reduce(): Reduces array to a single value by applying a function.  
	let numbers \= \[1, 2, 3, 4\];  
	let sum \= numbers.reduce((acc, num) \=\> acc \+ num, 0);  
console.log(sum); // Output: 10

4\.	concat(): Combines two or more arrays and returns a new array.  
	let arr1 \= \[1, 2\];•	let arr2 \= \[3, 4\];  
	let combined \= arr1.concat(arr2);  
console.log(combined); // Output: \[1, 2, 3, 4\]  
	join(): Joins all elements of an array into a string.  
	let words \= \["Hello", "world"\];  
	let sentence \= words.join(" ");  
console.log(sentence); // Output: "Hello world"

5\. Array Destructuring:  
Array destructuring is a way to unpack values from arrays into distinct variables.  
Example:  
let fruits \= \["apple", "banana", "cherry"\];  
let \[first, second\] \= fruits;  
console.log(first); // Output: "apple"  
console.log(second); // Output: "banana"

**Summary of Array Operations :**

| Operation | Method | Description |
| :---- | :---- | :---- |
| **Adding Elements** | push,unshift | Adds elements to the end or start of the array |
| **Removing Elements** | pop,shift | Removes elements from the end or start |
| **Accessing** | \[index\] | Accesses element at specific index |
| **Modifying** | splice,fill | Modifies elements at specific positions |
| **Searching** | indexOf, includes | Finds elements by value |
| **Sorting** | Sort, reverse | Sorts or reverses the array |
| **Iteration** | forEach, map, filter, reduce | Iterates and processes elements |
| **Combining** | Concat, join | Combines arrays or joins elements into a string |
| **Destructuring** | \[a,b\] \= array | Unpacks array elements into separate variables |

