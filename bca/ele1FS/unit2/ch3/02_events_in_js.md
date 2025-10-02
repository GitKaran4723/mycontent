**Comparison of Methods:**

| Method | Selects By | Returns | Live/Static |
| :---- | :---- | :---- | :---- |
| document.querySelector | CSS Selector | Single Element | Static |
| document.querySelectorAll | CSS Selector | NodeList | Static |
| document.getElementById | ID | Single Element | Live |
| document.getElementsByClassName | Class Name | HTML Collection | Live |
| document.getElementsByTagName | Tag Name | HTML Collection | Live |
| document.getElementsByName | Name Attribute | NodeList | Live |

**JavaScript’s addEventListener method** is the most powerful and flexible way to handle events. With this method, you can attach multiple event listeners to a single element, control the event flow, and manage events dynamically.

Here, we’ll explore various events and how to handle them using addEventListener, with real-world examples.

**1\. Mouse Events**  
\- click  
Triggered when an element is clicked.  
document.querySelector('\#myButton').addEventListener('click', () \=\> {  
    console.log('Button clicked\!');  
});

\- dblclick  
Triggered when an element is double-clicked.  
document.querySelector('\#myButton').addEventListener('dblclick', () \=\> {  
    console.log('Button double-clicked\!');  
});

\- mouseover  
Triggered when the mouse pointer enters the element.  
document.querySelector('\#myDiv').addEventListener('mouseover', () \=\> {  
    console.log('Mouse over the element\!');  
});

\- mouseout  
Triggered when the mouse pointer leaves the element.  
document.querySelector('\#myDiv').addEventListener('mouseout', () \=\> {  
    console.log('Mouse left the element\!');  
});

\- mousemove  
Triggered when the mouse moves within an element.  
document.querySelector('\#myDiv').addEventListener('mousemove', (event) \=\> {  
    console.log(\`Mouse position: (${event.clientX}, ${event.clientY})\`);  
});

**2\. Keyboard Events**  
\- keydown  
Triggered when a key is pressed down.  
document.addEventListener('keydown', (event) \=\> {  
    console.log(\`Key pressed: ${event.key}\`);  
});

\- keyup  
Triggered when a key is released.  
document.addEventListener('keyup', (event) \=\> {  
    console.log(\`Key released: ${event.key}\`);  
});

**3\. Form Events**  
\- submit  
Triggered when a form is submitted.  
document.querySelector('\#myForm').addEventListener('submit', (event) \=\> {  
    event.preventDefault(); // Prevents page refresh  
    console.log('Form submitted\!');  
});

\- change  
Triggered when the value of an input changes.  
document.querySelector('\#myInput').addEventListener('change', (event) \=\> {  
    console.log(\`Input changed to: ${event.target.value}\`);  
});

\- focus  
Triggered when an element gains focus (like an input field).  
document.querySelector('\#myInput').addEventListener('focus', () \=\> {  
    console.log('Input field focused\!');  
});

\- blur  
Triggered when an element loses focus.  
document.querySelector('\#myInput').addEventListener('blur', () \=\> {  
    console.log('Input field lost focus\!');  
});

\- input  
Triggered every time a user types in an input field.  
document.querySelector('\#myInput').addEventListener('input', (event) \=\> {  
    console.log(\`Current value: ${event.target.value}\`);  
});

**4\. Window Events**  
\- DOMContentLoaded  
Triggered when the HTML document is fully loaded.  
document.addEventListener('DOMContentLoaded', () \=\> {  
    console.log('DOM fully loaded and parsed');  
});

\- resize  
Triggered when the browser window is resized.  
window.addEventListener('resize', () \=\> {  
    console.log('Window resized');  
});

\- scroll  
Triggered when the user scrolls.  
window.addEventListener('scroll', () \=\> {  
    console.log('User is scrolling\!');  
});