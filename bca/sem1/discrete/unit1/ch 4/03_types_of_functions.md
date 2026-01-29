# Types of Functions 

## 1. One–One Function (Injective Function)

A function $ f : A \to B $ is said to be a **one–one function** or **injective function** if **distinct elements of the domain are mapped to distinct elements of the codomain**. In other words, no two different inputs produce the same output. Mathematically, a function is injective if
$$
f(x_1) = f(x_2) \Rightarrow x_1 = x_2
$$
This type of function preserves uniqueness of inputs in its outputs, ensuring that each element of the codomain is associated with **at most one** element of the domain.

**Example:**
Let $ f : {1,2,3} \to {2,4,6} $ be defined by $ f(x) = 2x $.
Here, $ f(1)=2 $, $ f(2)=4 $, and $ f(3)=6 $. Since all outputs are distinct, the function is one–one.

---

## 2. Many–One Function

A function $ f : A \to B $ is called a **many–one function** if **two or more distinct elements of the domain are mapped to the same element of the codomain**. This means the function does not preserve uniqueness of inputs in its outputs. Such a function is **not injective**.

**Example:**
Let $ f : {-2,-1,1,2} \to {1,4} $ be defined by $ f(x)=x^2 $.
Here, $ f(-2)=4 $ and $ f(2)=4 $, also $ f(-1)=1 $ and $ f(1)=1 $. Since different inputs have the same output, the function is many–one.

---

## 3. Onto Function (Surjective Function)

A function $ f : A \to B $ is said to be an **onto function** or **surjective function** if **every element of the codomain has at least one pre-image in the domain**. In this case, the **range of the function is equal to its codomain**. This means no element in the codomain is left unmapped.

Mathematically,
$$
\text{Range}(f) = \text{Codomain}(f)
$$

**Example:**
Let $ f : {1,2,3} \to {a,b,c} $ be defined as
$ f(1)=a $, $ f(2)=b $, $ f(3)=c $.
Since every element of the codomain is mapped, the function is onto.

---

## 4. Into Function

A function $ f : A \to B $ is called an **into function** if **at least one element of the codomain has no pre-image in the domain**. In this case, the **range is a proper subset of the codomain**. Into functions are the opposite of onto functions.

**Example:**
Let $ f : {1,2,3} \to {2,4,6,8} $ be defined by $ f(x)=2x $.
The range is $ {2,4,6} $, but the codomain contains 8, which has no pre-image. Hence, the function is into.

---

## 5. One–One and Onto Function (Bijective Function)

A function is said to be **bijective** if it is **both one–one and onto**. In a bijective function, every element of the domain maps to a unique element of the codomain, and every element of the codomain is mapped by exactly one element of the domain. Such functions establish a **perfect pairing** between the domain and codomain.

**Example:**
Let $ f : {1,2,3} \to {a,b,c} $ be defined as
$ f(1)=a $, $ f(2)=b $, $ f(3)=c $.
This function is both injective and surjective, so it is bijective.

---
## Solved important questions 


**1. If $ f : \mathbb{R} \to \mathbb{R} $ is defined by $ f(x) = 2x + 5 $, prove that ( f ) is one–one and onto.**


Given:
$$
f : \mathbb{R} \to \mathbb{R}, \quad f(x) = 2x + 5
$$



 (i) Proof that ( f ) is One–One (Injective)

To prove that ( f ) is one–one, we assume:
$$
f(x_1) = f(x_2)
$$

Then,
$$
2x_1 + 5 = 2x_2 + 5
$$

Subtract 5 from both sides:
$$
2x_1 = 2x_2
$$

Divide both sides by 2:
$$
x_1 = x_2
$$

Hence,
$$
f(x_1) = f(x_2) \Rightarrow x_1 = x_2
$$

Therefore, **( f ) is one–one**.



(ii) Proof that ( f ) is Onto (Surjective)

To prove that ( f ) is onto, we must show that **for every** $ y \in \mathbb{R} $, **there exists** an $ x \in \mathbb{R} $ such that:
$$
f(x) = y
$$

Let:
$$
y = 2x + 5
$$

Solve for ( x ):
$$
x = \frac{y - 5}{2}
$$

Since $ y \in \mathbb{R} $, the value
$$
x = \frac{y - 5}{2} \in \mathbb{R}
$$

Thus, for every real number ( y ), there exists a real number ( x ) such that $ f(x) = y $.

Hence, **( f ) is onto**.

Since the function $ f(x) = 2x + 5 $ is **both one–one and onto**, it is a **bijective function**.

$$
\boxed{\text{Therefore, } f \text{ is one–one and onto.}}
$$

---
**2. If $ f : \mathbb{R} \to \mathbb{R} $ is defined by $ f(x) = 2x + 3 $, prove that ( f ) is one–one and onto.**

Given:
$ f:\mathbb{R}\to\mathbb{R} $ defined by
$$
f(x)=2x+3
$$

We must prove that (f) is **one–one (injective)** and **onto (surjective)**



 (i) To prove (f) is one–one

Assume
$$
f(x_1)=f(x_2)
$$

$$
2x_1+3 = 2x_2+3
$$

Subtract 3 from both sides:
$$
2x_1 = 2x_2
$$

Divide by 2:
$$
x_1 = x_2
$$

Since $f(x_1)=f(x_2)\Rightarrow x_1=x_2$,
$$
\boxed{f \text{ is one–one}}
$$



 (ii) To prove (f) is onto

Let $y\in\mathbb{R}$.
We must show that there exists (x\in\mathbb{R}) such that
$$
f(x)=y
$$

$$
2x+3 = y
$$

Solve for (x):
$$
2x = y-3
$$
$$
x = \frac{y-3}{2}
$$

Since $\frac{y-3}{2}\in\mathbb{R}$ for every real (y), such an (x) exists.

Hence,
$$
\boxed{f \text{ is onto}}
$$





Since (f) is both one–one and onto,
$$
\boxed{f \text{ is bijective}}
$$

---
**3. If $ f : \mathbb{R} \to \mathbb{R} $ is defined by $ f(x) = 4x+5 $, prove that ( f ) is one–one and onto.**

Given:
$ f:\mathbb{R}\to\mathbb{R}$ defined by
$$
f(x)=4x+5
$$

We prove that (f) is **one–one** and **onto**.



 (i) To prove (f) is one–one (Injective)

Assume
$$
f(x_1)=f(x_2)
$$

$$
4x_1+5 = 4x_2+5
$$

Subtract 5 from both sides:
$$
4x_1 = 4x_2
$$

Divide by 4:
$$
x_1 = x_2
$$

Hence,
$$
\boxed{f \text{ is one–one}}
$$


(ii) To prove (f) is onto (Surjective)

Let $y \in \mathbb{R}$.

We need to show there exists $x \in \mathbb{R}$ such that
$$
f(x)=y
$$

$$
4x+5 = y
$$

Solve for (x):
$$
4x = y-5
$$

$
x = \frac{y-5}{4}
$

Since $\frac{y-5}{4} \in \mathbb{R}$ for every real (y), such an (x) exists.

Thus,
$$
\boxed{f \text{ is onto}}
$$



Since (f) is both one–one and onto,

$$
\boxed{f \text{ is bijective}}
$$
---
