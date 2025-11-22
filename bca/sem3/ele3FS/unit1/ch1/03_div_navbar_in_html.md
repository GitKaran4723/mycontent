**HTML Div Element:**

\<div\> →Defines a section in a document (block-level)

The \<div\> element is used as a container for other HTML elements.

**The \<div\> Element:**  
The \<div\> element is by default a block element, meaning that it takes all available width, and comes with line breaks before and after.

**Example:**

| A \<div\> element takes up all available width: Lorem Ipsum \<div\>I am a div\</div\> dolor sit amet. |
| :---- |

**Result:**

| Lorem Ipsum I am a div dolor sit amet. |
| :---- |

The \<div\> element has no required attributes, but style, class and id are common.

**\<div\> as a container**

The \<div\> element is often used to group sections of a web page together.

**Example:**  
A \<div\> element with HTML elements:

| \<div\>   \<h2\>London\</h2\>   \<p\>London is the capital city of England.\</p\>   \<p\>London has over 9 million inhabitants.\</p\> \</div\> |
| :---- |

**Result:**

| London London is the capital city of England. London has over 9 million inhabitants. |
| :---- |

**Center align a \<div\> element:**

If you have a \<div\> element that is not 100% wide, and you want to center-align it, set the CSS margin property to auto.  
**Example:**

| \<style\> div {   width:300px;   margin:auto; } \</style\> |
| :---- |

**Result:**

| London London is the capital city of England. London has over 9 million inhabitants. |
| :---- |

**Multiple \<div\> elements:**

It  have many \<div\> containers on the same page.

**Example:**

| \<div\>   \<h2\>London\</h2\>   \<p\>London is the capital city of England.\</p\>   \<p\>London has over 9 million inhabitants.\</p\> \</div\> \<div\>   \<h2\>Oslo\</h2\>   \<p\>Oslo is the capital city of Norway.\</p\>   \<p\>Oslo has over 700,000 inhabitants.\</p\> \</div\> \<div\>   \<h2\>Rome\</h2\>   \<p\>Rome is the capital city of Italy.\</p\>   \<p\>Rome has over 4 million inhabitants.\</p\> \</div\> |
| :---- |

**Result:**

| London London is the capital city of England. London has over 9 million inhabitants. |
| :---- |

| Oslo Oslo is the capital city of Norway. Oslo has over 700,000 inhabitants. |
| :---- |

| Rome Rome is the capital city of Italy. Rome has over 4 million inhabitants. |
| :---- |

**Aligning \<div\> elements side by side:**

When building web pages, you often want to have two or more \<div\> elements side by side, like this:

| London London is the capital city of England. London has over 9 million inhabitants.  | Oslo Oslo is the capital city of Norway. Oslo has over 700,000 inhabitants. Rome | Rome Rome is the capital city of Italy. Rome has over 4 million inhabitants.  |
| :---- | :---- | :---- |

There are different methods for aligning elements side by side, all include some CSS styling. We will look at the most common methods:

**Float:**

The CSS float property was not originally meant to align \<div\> elements side-by-side, but has been used for this purpose for many years.  
The CSS float property is used for positioning and formatting content and allows elements to be positioned horizontally, rather than vertically.

**Example:**

How to use float to align div elements side by side:

| \<style\> .mycontainer {   width:100%;   overflow:auto; } .mycontainer div {   width:33%;   float:left; } \</style\> |
| :---- |

**Result:**

| London  London is the capital city of England. London has over 9 million inhabitants.  | Oslo  Oslo is the capital city of Norway. Oslo has over 700,000 inhabitants. | Rome  Rome is the capital city of Italy. Rome has over 4 million inhabitants.  |
| :---- | :---- | :---- |

**Inline-block**

If you change the \<div\> element's display property from block to inline-block, the \<div\> elements will no longer add a line break before and after, and will be displayed side by side instead of on top of each other.

**Example:**

How to use display: inline-block to align div elements side by side:

| \<style\> div {   width: 30%;   display: inline-block; } \</style\> |
| :---- |

**Result:**

| London  London is the capital city of England. London has over 9 million inhabitants. | Oslo Oslo is the capital city of Norway. Oslo has over 700,000 inhabitants. | Rome Rome is the capital city of Italy. Rome has over 4 million inhabitants.  |
| :---- | :---- | :---- |

**Flex**

The CSS Flexbox Layout Module was introduced to make it easier to design flexible responsive layout structure without using float or positioning.  
To make the CSS flex method work, surround the \<div\> elements with another \<div\> element and give it the status as a flex container.

**Example:**

How to use flex to align div elements side by side:

| \<style\> .mycontainer {   display: flex; } .mycontainer \> div {   width:33%; } \</style\> |
| :---- |

**Result:**

| London  London is the capital city of England. London has over 9 million inhabitants. Oslo | Oslo  Oslo is the capital city of Norway. Oslo has over 700,000 inhabitants. | Rome  Rome is the capital city of Italy. Rome has over 4 million inhabitants.  |
| :---- | :---- | :---- |

**Grid**

The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

Sounds almost the same as flex, but has the ability to define more than one row and position each row individually.

The CSS grid method requires that you surround the \<div\> elements with another \<div\> element and give the status as a grid container, and you must specify the width of each column.

**Example:**

How to use grid to align \<div\> elements side by side:

| \<style\> .grid-container {   display: grid;   grid-template-columns: 33% 33% 33%; } \</style\> |
| :---- |

**Result:**

| London  London is the capital city of England. London has over 9 million inhabitants. | Oslo  Oslo is the capital city of Norway. Oslo has over 700,000 inhabitants. | Rome  Rome is the capital city of Italy. Rome has over 4 million inhabitants.  |
| :---- | :---- | :---- |

# **HTML Iframes:**

An HTML iframe is used to display a web page within a web page.

## **HTML Iframe Syntax:**

The HTML \<iframe\> tag specifies an inline frame.

An inline frame is used to embed another document within the current HTML document.

### **Syntax:** \<iframe src="*url*" title="*description*"\>\</iframe\>

### **Navigation Bar \= List of Links:**

### A navigation bar needs standard HTML as a base.

### A navigation bar is basically a list of links, so using the \<ul\> and \<li\> elements makes perfect sense:

### **Example:**

\<ul\>  
  \<li\>\<a href="default.asp"\>Home\</a\>\</li\>  
  \<li\>\<a href="news.asp"\>News\</a\>\</li\>  
  \<li\>\<a href="contact.asp"\>Contact\</a\>\</li\>  
  \<li\>\<a href="about.asp"\>About\</a\>\</li\>  
\</ul\>

Now let's remove the bullets and the margins and padding from the \<ul\> element:

**Example:**  
ul {  
  list-style-type: none;  
  margin: 0;  
  padding: 0;  
}

**Example explained:**

* Set list-style-type: none; \- Removes the bullet points from list.  
* Set margin: 0; \- Resets default browser margins.  
* Set padding: 0; \- Resets default browser paddings.

**Note:** The HTML and CSS code in the example above is the base code used for both vertical and horizontal navigation bars, which you will learn more about in the next chapters.

