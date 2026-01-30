# Questions on Inverse and Composite functions:


### **1.** If $ f : \mathbb{R} \to \mathbb{R} $ is defined by

$
f(x) = 3x - 4
$
find $ f^{-1}$, $ f^{-1}(-2) $ and $ f^{-1}(-16) $.

 **Step 1: Find the inverse function**

Let
$
y = 3x - 4
$
Solve for (x):
$
y + 4 = 3x
$
$
x = \frac{y+4}{3}
$

So,
$
f^{-1}(y) = \frac{y+4}{3}
$



 **Step 2: Evaluate the given values**

1. $ f^{-1}(9) $
   $
   f^{-1}(9) = \frac{9+4}{3} = \frac{13}{3}
   $

2. $ f^{-1}(-2) $
   $
   f^{-1}(-2) = \frac{-2+4}{3} = \frac{2}{3}
   $

3. $ f^{-1}(-16) $
   $
   f^{-1}(-16) = \frac{-16+4}{3} = \frac{-12}{3} = -4
   $

 **Answers**

$$
f^{-1}(9) = \frac{13}{3}, \quad f^{-1}(-2) = \frac{2}{3}, \quad f^{-1}(-16) = -4
$$

---

### **2.** If $ f : \mathbb{R} \to \mathbb{R} $ is defined by

$
f(x) = x^2
$
find $ f^{-1}(9) $.

 **Explanation**

* The function $ f(x) = x^2 $ is **not one-to-one** on $ \mathbb{R} $.
* Hence, its inverse is **not a function** unless the domain is restricted.

Solving:
$
x^2 = 9
$

$
x = \pm 3
$

 **Answer**

$$
f^{-1}(9) = {-3,, 3}
$$

*(If the domain were restricted to $ x \ge 0 $, then $ f^{-1}(9) = 3 $ only.)*

---



### **3.** If $ f : \mathbb{R} \rightarrow \mathbb{R} $ is defined by
$
f(x) = 2x + 3,
$
prove that ( f ) is **one-one and onto**, and hence find the **inverse of ( f )**.


---

 **Given**

Let
$
f : \mathbb{R} \to \mathbb{R}
$
be defined by
$
f(x) = 2x + 3
$

---

**Proof that ( f ) is One-One**

Assume
$
f(x_1) = f(x_2)
$

$
2x_1 + 3 = 2x_2 + 3
$

$
2x_1 = 2x_2
$

$
x_1 = x_2
$

Since $ f(x_1) = f(x_2) \Rightarrow x_1 = x_2 $,
the function ( f ) is **one-one**.

---

**Proof that ( f ) is Onto**

Let $ y \in \mathbb{R} $ be any element in the codomain.

We must show that there exists $ x \in \mathbb{R} $ such that
$
f(x) = y
$

$
2x + 3 = y
$

$
2x = y - 3
$

$
x = \frac{y - 3}{2}
$

Since $ x \in \mathbb{R} $ for every $ y \in \mathbb{R} $,
the function ( f ) is **onto**.

---

 **Finding the Inverse of ( f )**

Since ( f ) is both **one-one and onto**, it is **bijective** and hence has an inverse.

Let
$
y = f(x) = 2x + 3
$

Solve for ( x ):
$
x = \frac{y - 3}{2}
$

Thus,
$
f^{-1}(y) = \frac{y - 3}{2}
$

Replacing ( y ) by ( x ),
$$
\boxed{f^{-1}(x) = \frac{x - 3}{2}}
$$



---

### **4.** Consider the functions ( f ) and ( g ) defined by
$
f(x) = x^2 + 5 \quad \text{and} \quad g(x) = 5x - 2.
$
Find the composite functions:
(a) $ f \circ g $
(b) $ g \circ f $
(c) $ f \circ f $

---
**Answer**

 **(a) Find $ f \circ g $**

By definition,
$
(f \circ g)(x) = f(g(x))
$

Substitute $ g(x) = 5x - 2 $ into ( f ):
$
f(g(x)) = f(5x - 2) = (5x - 2)^2 + 5
$

$
= 25x^2 - 20x + 4 + 5
$

$$
\boxed{(f \circ g)(x) = 25x^2 - 20x + 9}
$$

---

### **(b) Find $ g \circ f $**

By definition,
$
(g \circ f)(x) = g(f(x))
$

Substitute $ f(x) = x^2 + 5 $ into ( g ):
$
g(f(x)) = g(x^2 + 5) = 5(x^2 + 5) - 2
$

$
= 5x^2 + 25 - 2
$

$$
\boxed{(g \circ f)(x) = 5x^2 + 23}
$$

---

**(c) Find $ f \circ f $**

By definition,
$
(f \circ f)(x) = f(f(x))
$

Substitute $ f(x) = x^2 + 5 $ into itself:
$
f(f(x)) = f(x^2 + 5) = (x^2 + 5)^2 + 5
$

$
= x^4 + 10x^2 + 25 + 5
$

$$
\boxed{(f \circ f)(x) = x^4 + 10x^2 + 30}
$$

