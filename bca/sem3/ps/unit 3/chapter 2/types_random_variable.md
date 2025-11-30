# **RANDOM VARIABLES – TYPES**

Random Variables are mainly classified into **two types** based on the kind of values they can take:

1. **Discrete Random Variable**

2. **Continuous Random Variable**

Both describe how outcomes of a random experiment are represented numerically — but they differ in *how many* and *what type* of values they can take.

---

## **🔹 1\. DISCRETE RANDOM VARIABLE**

---

### **Definition**

A **Discrete Random Variable (DRV)** is one that can take only **finite or countable number of possible values**.

In other words, you can **list** all possible values of X, even if they go on infinitely (like 0, 1, 2, 3, ...).

Each of these values has a specific probability assigned to it.

---

### **Explanation**

* The values of a discrete random variable are **separate and distinct**.

* There are “gaps” between the possible values.

* The probability of each value is **non-zero**, but probabilities of all values together must sum to 1\.

---

### **Examples**

1. **Tossing Three Coins**

   * Let X \= number of heads.

   * Possible values: 0, 1, 2, 3

   * Each value has a specific probability.

2. 

| X | 0 | 1 | 2 | 3 |
| ----- | ----- | ----- | ----- | ----- |
| P(X) | 1/8 | 3/8 | 3/8 | 1/8 |

3.   
   → X is **discrete**, because it takes a few separate values (0,1,2,3).

---

2. **Rolling a Die**

   * X \= number on the die

   * Possible values: 1,2,3,4,5,6

   * Each with probability 1/6

3. → Finite set of outcomes → **discrete random variable**.

---

3. **Number of Students Absent in Class**

   * X can be 0,1,2,3,… up to total class strength.

   * These are countable → **discrete**.

---

4. **Number of Defective Items in a Batch**

   * X \= number of defective items among 10 tested.

   * Possible values: 0,1,2,…,10 → discrete.

---

### **Probability Mass Function (PMF)**

The **Probability Mass Function (PMF)** describes the distribution of a discrete random variable.

* PMF gives the probability that the random variable takes a particular value.

   **Written as:** P(X \= x)

* **Conditions for PMF:**

  1. P(X \= x) ≥ 0 for every x

  2. The sum of all probabilities \= 1

---

### **Graphical Representation**

The PMF is shown using a **bar graph**,  
 where:

* X-axis → possible values of X

* Y-axis → corresponding probabilities P(X=x)

Each bar represents a “mass” of probability at a particular value of X.

---

### **Why the Name “Mass”?**

Because each possible value of X carries a **mass of probability** —  
 the probability is *stored* at specific discrete points, not spread continuously.

Imagine small stones placed at separate positions along the X-axis — that’s a PMF.

---

### **Key Features of Discrete Random Variable**

| Feature | Description |
| ----- | ----- |
| Type of values | Countable (finite or infinite) |
| Probability | Assigned to each individual value |
| Function | Probability Mass Function (PMF) |
| Graph type | Bars |
| Example | Dice outcome, number of heads, students present |

---

---

## **🔹 2\. CONTINUOUS RANDOM VARIABLE**

---

### **Definition**

A **Continuous Random Variable (CRV)** is one that can take **any value within a given range or interval**.

This means the number of possible values is **uncountable and infinite**.

Instead of probabilities for individual points, we use a **Probability Density Function (PDF)** to describe how probabilities are distributed over a range.

---

### **Explanation**

* Values of a continuous random variable are **not countable**, because between any two numbers there are infinitely many possible values.

* Example: Between 4 and 5 seconds, we can have 4.1, 4.11, 4.111, 4.1111, and so on.

* So, the probability of X taking any single exact value is **zero**.

* Probabilities are calculated over **intervals** using the **area under the curve** of f(x).

---

### **Examples**

1. **Time Taken to Run 100 Meters**

   * X \= time (in seconds)

   * Possible values: any real number between 10 and 15 seconds.

   * Uncountably infinite → continuous random variable.

---

2. **Height of Students in a Class**

   * X \= height (in cm)

   * Can be 150.2, 150.25, 150.251, etc.

   * Infinitely many possible values → continuous.

---

3. **Voltage Across a Circuit**

   * X \= voltage (in volts)

   * Values could be 4.95, 4.96, 4.961, etc.

   * Continuous.

---

4. **Rainfall in a Day**

   * X \= rainfall (in mm)

   * Can be 12.5, 12.51, 12.512, etc.

   * Continuous.

---

### **Probability Density Function (PDF)**

The **Probability Density Function (f(x))** represents the distribution of a continuous random variable.

It describes how the total probability (which equals 1\) is **spread** or **distributed** over the range of possible values.

---

**Conditions for a valid PDF:**

1. f(x) ≥ 0 for all x

2. The total area under the curve \= 1

(That is, the integral of f(x) over all x equals 1.)

---

**Important:**  
 The probability of X being exactly equal to a single point (like X \= 3.5) is 0\.  
 Only the **area between two points** has meaning:

P(a ≤ X ≤ b) \= area under f(x) between a and b.

---

### **Example: PDF Example**

Let f(x) \= 2x for 0 ≤ x ≤ 1  
 and f(x) \= 0 otherwise.

Check total area:  
 Area \= integral of 2x from 0 to 1 \= 1 → valid PDF.

Now,  
 P(0 ≤ X ≤ 0.5) \= area under curve from 0 to 0.5  
 \= 0.25 (or 25% probability).

---

### **Graphical Representation**

The PDF is shown as a **smooth curve**,  
 where:

* X-axis → possible values of X

* Y-axis → probability density (f(x))

* Area under the curve between two X-values → probability.

---

### **Why the Name “Density”?**

Because probability is **spread like a continuous density** across a range of values —  
 not concentrated at single points.

Imagine sand spread along a surface — the total “mass” of sand represents the total probability (1).

---

### **Key Features of Continuous Random Variable**

| Feature | Description |
| ----- | ----- |
| Type of values | Uncountable and infinite |
| Probability | Measured over intervals, not single points |
| Function | Probability Density Function (PDF) |
| Probability of a single point | Always zero |
| Probability of a range | Area under curve between two points |
| Graph type | Smooth curve |
| Example | Height, time, rainfall, voltage |

---

## **🔸 3\. Comparison Between Discrete and Continuous Random Variables**

| Feature | Discrete Random Variable | Continuous Random Variable |
| ----- | ----- | ----- |
| Nature of values | Countable | Uncountable (infinite) |
| Probability of each value | Non-zero | Zero |
| Probability for a range | Sum of P(X=x) | Area under curve |
| Function type | Probability Mass Function (PMF) | Probability Density Function (PDF) |
| Graph shape | Bar chart | Smooth curve |
| Representation | P(X=x) | f(x) |
| Example | Number of heads, dice roll | Height, time, temperature |
| Probability total | Sum \= 1 | Total area \= 1 |

---

## **🔹 4\. Key Points to Remember**

1. **Discrete Random Variable:**

   * Countable outcomes (whole numbers)

   * Probability assigned to specific values

   * Represented by PMF

2. **Continuous Random Variable:**

   * Infinite outcomes (including decimals)

   * Probability spread over a range

   * Represented by PDF

3. The **total probability** in both cases is always equal to 1\.

4. PMF → Probability “Mass” at points  
    PDF → Probability “Density” spread continuously

---

## **5\. Simple Way to Remember**

If you **count** it → Discrete Random Variable

If you **measure** it → Continuous Random Variable

