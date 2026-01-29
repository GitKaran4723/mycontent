# Function Composition

###  Definition

Function composition is the process of combining two functions to form a new function. Let $ f : A \to B $ and $ g : B \to C $ be two functions. The composition of ( f ) and ( g ), denoted by $ g \circ f $, is defined as a function from set ( A ) to set ( C ) such that for every element $ x \in A $, $ (g \circ f)(x) = g(f(x)) $. This means that the output of the first function becomes the input of the second function. Function composition is defined only when the range of the first function lies within the domain of the second function.


Let
$$
f: A \to B \quad \text{and} \quad g: B \to C
$$
be two functions.

The **composition of (f) and (g)** is a function
$$
g \circ f : A \to C
$$
defined by
$$
(g \circ f)(x) = g(f(x)) \quad \text{for all } x \in A
$$

**Meaning:** First apply (f), then apply (g).

---



### Example 

Let
$$
f(x) = x + 2,\quad g(x) = 3x
$$

$$
(g \circ f)(x) = g(f(x)) = g(x+2) = 3(x+2) = 3x + 6
$$

$$
(f \circ g)(x) = f(g(x)) = f(3x) = 3x + 2
$$

**Note:** $g \circ f \neq f \circ g$

---

##  Rules for Function Composition

### 1. **Range of first = Domain of second**
   Composition $g \circ f$ exists **only if**
   $$
   \text{Range}(f) \subseteq \text{Domain}(g)
   $$

### 2. **Order matters**
  $$
   g \circ f \neq f \circ g \quad \text{(in general)}
   $$

### 3. **Notation rule**
   $$
   (g \circ f)(x) = g(f(x))
   $$

---

##  Properties of Function Composition

### 1. Associative Property

$$
h \circ (g \circ f) = (h \circ g) \circ f
$$



---

### 2. Not Commutative

$$
f \circ g \neq g \circ f
$$



---

### 3. Identity Property

Let (I(x) = x) be the identity function.

$$
f \circ I = I \circ f = f
$$

---

### 4. Composition of Injective Functions

* If (f) and (g) are **injective**, then
  $$
  g \circ f \text{ is injective}
 $$

---

### 5. Composition of Surjective Functions

* If (f) and (g) are **surjective**, then
  $$
  g \circ f \text{ is surjective}
  $$

---

### 6. Composition of Bijective Functions

* If (f) and (g) are **bijective**, then
  $$
  g \circ f \text{ is bijective}
  $$

---

### 7. Inverse and Composition

If (f) and (g) are bijections, then
$$
(g \circ f)^{-1} = f^{-1} \circ g^{-1}
$$

---