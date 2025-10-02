## **What is an HTML Element?**

An HTML element is defined by a start tag, some content, and an end tag

\<tagname\> Content goes here... \</tagname\>

Examples of some HTML elements:

| \<h1\>My First Heading\</h1\> \<p\>My first paragraph.\</p\>  |
| :---- |

The \<html\> element is the root element and it defines the whole HTML document.

It has a start tag \<html\> and an end tag \</html\>.

Then, inside the \<html\> element there is a \<body\> element:

| \<body\> \<h1\>My First Heading\</h1\> \<p\>My first paragraph.\</p\> \</body\>  |
| :---- |

The \<body\> element defines the document's body.

It has a start tag \<body\> and an end tag \</body\>.

Then, inside the \<body\> element there are two other elements: \<h1\> and \<p\>:

| \<h1\>My First Heading\</h1\> \<p\>My first paragraph.\</p\>  |
| :---- |

* The \<h1\> element defines a heading.

It has a start tag \<h1\> and an end tag \</h1\>:

\<h1\>My First Heading\</h1\>

* The \<p\> element defines a paragraph.

It has a start tag \<p\> and an end tag \</p\>:

\<p\>My first paragraph.\</p\>

**Example:**

\<html\>

\<body\>

\<p\>This is a paragraph

\<p\>This is a paragraph

\</body\>

\</html\>

**The href Attribute:-**

The \<a\> tag defines a hyperlink.

**Example:**

\<a href="[https://www.google.com](https://www.google.com)"\>Visit Google\</a\>

**The src Attribute:-**

The \<img\> tag is used to embed an image in an HTML page. The src attribute specifies the path to the image to be displayed.

**Example:**\<img src="img\_girl.jpg"\>

**The alt attribute:-**

The required alt attribute for the \<img\> tag specifies an alternate text for an image, if the image for some reason cannot be displayed. This can be due to a slow connection, or an error in the src attribute, or if the user uses a screen reader.

**Example:**\<img src="img\_girl.jpg" alt="Girl with a jacket"\>

**The style Attribute:-**

The style attribute is used to add styles to an element, such as color, font, size, and more.

**Example:**\<p style="color:red;"\>This is a red paragraph.\</p\>

**The title Attribute:-**

The title attribute defines some extra information about an element.

The value of the title attribute will be displayed as a tooltip when you mouse over the element:

**Example:**\<p title="I'm a tooltip"\>This is a paragraph.\</p\>

**HTML Headings:-**

HTML headings are titles or subtitles that you want to display on a webpage.

### **Example:**

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

###### *HTML headings are defined with the \<h1\> to \<h6\> tags.*

###### *\<h1\> defines the most important heading. \<h6\> defines the least important heading.*

### **Example:**

\<h1\>Heading 1\</h1\>

\<h2\>Heading 2\</h2\>

\<h3\>Heading 3\</h3\>

\<h4\>Heading 4\</h4\>

\<h5\>Heading 5\</h5\>

\<h6\>Heading 6\</h6\>

**HTML Paragraphs:**

The HTML \<p\> element defines a paragraph.

A paragraph always starts on a new line, and browsers automatically add some white space (a margin) before and after a paragraph.

### **Example:**

\<p\>This is a paragraph.\</p\>

\<p\>This is another paragraph.\</p\>

**HTML Paragraphs:**

The HTML \<p\> element defines a paragraph.

A paragraph always starts on a new line, and browsers automatically add some white space (a margin) before and after a paragraph.

### **Example:**

\<p\>This is a paragraph.\</p\>

\<p\>This is another paragraph.\</p\>

**HTML Lists:**

HTML lists allow web developers to group a set of related items in lists.

**Unordered HTML List:**

An unordered list starts with the \<ul\> tag. Each list item starts with the \<li\> tag.

The list items will be marked with bullets (small black circles) by default:

**Example:**

\<ul\>

  \<li\>Coffee\</li\>

  \<li\>Tea\</li\>

  \<li\>Milk\</li\>

\</ul\>

**Ordered HTML List:**

An ordered list starts with the \<ol\> tag. Each list item starts with the \<li\> tag.

The list items will be marked with numbers by default:

### **Example:**

\<ol\>

  \<li\>Coffee\</li\>

  \<li\>Tea\</li\>

  \<li\>Milk\</li\>

\</ol\>

**HTML Description Lists:**

HTML also supports description lists.

A description list is a list of terms, with a description of each term.

The \<dl\> tag defines the description list, the \<dt\> tag defines the term (name), and the

\<dd\> tag describes each term:

### **Example:**

\<dl\>

  \<dt\>Coffee\</dt\>

  \<dd\>- black hot drink\</dd\>

  \<dt\>Milk\</dt\>

  \<dd\>- white cold drink\</dd\>

\</dl\>

