# **📘 EXPECTATION AND VARIANCE OF A RANDOM VARIABLE**

---

## **1\. Meaning**

### **(a) Expectation (or Expected Value or Mean)**

The **Expectation** of a random variable is the **average or mean value** you would expect to get if an experiment is repeated a large number of times.

It represents the **center** or **typical value** of the probability distribution.

---

### **In Simple Words**

* It is what we **expect on average** from a random process.

* It gives the **weighted average** of all possible values of a random variable, weighted by their probabilities.

---

### **(b) Variance**

The **Variance** of a random variable measures **how much the values of the variable spread out** around the mean.

It shows the **degree of uncertainty or variability** in the random outcomes.

---

# **🔹 2\. Expectation of a Discrete Random Variable**

Let X be a discrete random variable taking values x₁, x₂, x₃, … with probabilities P(X \= x₁), P(X \= x₂), etc.

Then, the **Expected Value of X** is calculated as:

**E(X) \= Σ \[x \* P(X \= x)\]**

This is simply:

Multiply each possible value by its probability, then add them all up.

---

### **Example 1: Tossing Two Coins**

Let X \= number of heads.  
 Possible values of X: 0, 1, 2  
 Probabilities: 1/4, 1/2, 1/4

E(X) \= (0 × 1/4) \+ (1 × 1/2) \+ (2 × 1/4)  
 E(X) \= 0 \+ 1/2 \+ 1/2 \= **1**

✅ Expected number of heads \= 1

---

### **Example 2: Rolling a Die**

X \= number shown on die  
 Each number (1–6) has probability 1/6.

E(X) \= (1 \+ 2 \+ 3 \+ 4 \+ 5 \+ 6\) × (1/6)  
 E(X) \= 21 × (1/6) \= **3.5**

✅ Expected value \= 3.5 → this is the long-run average result when you roll a die many times.

---

# **🔹 3\. Expectation of a Continuous Random Variable**

If X is a continuous random variable with **probability density function (PDF)** f(x), then:

**E(X) \= ∫ \[x \* f(x)\] dx**  
 where the integration is taken over the entire range of X.

---

### **Example 3: f(x) \= 2x for 0 ≤ x ≤ 1**

E(X) \= ∫ from 0 to 1 of x(2x) dx  
 \= ∫ from 0 to 1 of 2x² dx  
 \= \[ (2x³) / 3 \] from 0 to 1  
 E(X) \= 2/3

✅ Expected value \= 0.667

---

### **Real-Life Meaning**

* In a factory, if X is the lifetime of a machine (in hours), then E(X) \= 2000 means:  
   “On average, a machine lasts about 2000 hours.”

* It doesn’t mean each machine lasts exactly that long — it’s the **average** of many similar outcomes.

---

# **🔹 4\. Expectation of a Function of a Random Variable**

If g(X) is any function of X, then the expectation of g(X) is:

* **For discrete X:** E\[g(X)\] \= Σ \[g(x) \* P(X=x)\]

* **For continuous X:** E\[g(X)\] \= ∫ \[g(x) \* f(x)\] dx

**Example:**  
 If X \= 0, 1, 2 with P(X) \= 1/4, 1/2, 1/4,  
 and g(X) \= X²,  
 then E(X²) \= (0²×1/4) \+ (1²×1/2) \+ (2²×1/4) \= 0 \+ 0.5 \+ 1 \= **1.5**

---

# **🔹 5\. Variance of a Random Variable**

Variance measures how far the values of a random variable are **spread out around the mean**.

It tells us how much the variable **deviates from its expected value**.

**Formula:**

* For discrete random variable:  
   Var(X) \= Σ \[(x − E(X))² \* P(X \= x)\]

* For continuous random variable:  
   Var(X) \= ∫ \[(x − E(X))² \* f(x)\] dx

---

### **Alternative (Shortcut) Formula**

Var(X) \= E(X²) − \[E(X)\]²

That is,  
 First find E(X²) → the expected value of X squared,  
 then subtract the square of E(X).

---

### **Example 4: Tossing Two Coins**

X \= number of heads  
 X \= 0, 1, 2  
 P(X) \= 1/4, 1/2, 1/4

Step 1: E(X) \= (0×1/4) \+ (1×1/2) \+ (2×1/4) \= 1  
 Step 2: E(X²) \= (0²×1/4) \+ (1²×1/2) \+ (2²×1/4) \= (0 \+ 0.5 \+ 1\) \= 1.5  
 Step 3: Var(X) \= E(X²) − \[E(X)\]² \= 1.5 − 1² \= 0.5

✅ Variance \= 0.5  
 Standard Deviation \= √0.5 ≈ 0.707

---

### **Example 5: Rolling a Die**

X \= number shown (1 to 6\)  
 Each probability \= 1/6

Step 1: E(X) \= 3.5  
 Step 2: E(X²) \= (1² \+ 2² \+ 3² \+ 4² \+ 5² \+ 6²) × (1/6)  
 \= (91 × 1/6) \= 15.1667  
 Step 3: Var(X) \= E(X²) − \[E(X)\]²  
 \= 15.1667 − (3.5)² \= 15.1667 − 12.25 \= 2.9167

✅ Variance \= 2.92 (approx.)  
 Standard Deviation \= √2.92 \= 1.71

---

### **Example 6: Continuous Random Variable**

f(x) \= 2x for 0 ≤ x ≤ 1

E(X) \= 2/3 (from earlier)  
 E(X²) \= ∫ from 0 to 1 of x²(2x) dx \= 2∫₀¹ x³ dx \= 0.5  
 Var(X) \= E(X²) − \[E(X)\]² \= 0.5 − (2/3)² \= 0.5 − 4/9 \= 1/18 ≈ 0.0556

✅ Variance \= 1/18

---

# **🔹 6\. Interpretation**

| Measure | Meaning | Description |
| ----- | ----- | ----- |
| **Expectation (E\[X\])** | Average / Mean | Center of the distribution; what we expect on average |
| **Variance (Var\[X\])** | Spread | How much the values differ from the average |
| **Standard Deviation (σ)** | √Variance | Spread in original units |

---

### **Real-Life Examples**

| Situation | Random Variable | Interpretation of E(X) | Interpretation of Var(X) |
| ----- | ----- | ----- | ----- |
| Coin toss | Number of heads | Average heads per toss | Consistency in results |
| Machine lifetime | Hours of operation | Average lifetime | How much lifetime varies |
| Customer arrivals | Number of customers/hour | Expected number of arrivals | Variation in arrivals |
| Investment returns | Return rate | Average profit | Risk or volatility |

---

# **🔹 7\. Properties of Expectation and Variance**

### **Properties of Expectation**

1. E(aX \+ b) \= aE(X) \+ b  
    (a, b are constants)

2. E(X \+ Y) \= E(X) \+ E(Y)

3. E(c) \= c (if c is a constant)

---

### **Properties of Variance**

1. Var(aX \+ b) \= a² Var(X)  
    (Adding a constant b doesn’t change variance)

2. Var(X \+ Y) \= Var(X) \+ Var(Y) (if X and Y are independent)

3. Standard Deviation (σ) \= √Var(X)

---

# **🔹 8\. Comparison Summary**

| Concept | Discrete Random Variable | Continuous Random Variable |
| ----- | ----- | ----- |
| Formula for Mean | E(X) \= Σ x P(X=x) | E(X) \= ∫ x f(x) dx |
| Formula for Variance | Var(X) \= Σ (x − E(X))² P(X=x) | Var(X) \= ∫ (x − E(X))² f(x) dx |
| Example | Dice, coins | Time, height |
| Interpretation | Long-run average | Weighted average by density |

---

# **🔹 9\. Quick Practice Questions**

### **Q1. A coin is tossed three times. Find E(X) and Var(X) where X \= number of heads.**

| X | 0 | 1 | 2 | 3 |
| ----- | ----- | ----- | ----- | ----- |
| P(X) | 1/8 | 3/8 | 3/8 | 1/8 |

E(X) \= (0×1/8)+(1×3/8)+(2×3/8)+(3×1/8)=1.5  
 E(X²) \= (0²×1/8)+(1²×3/8)+(2²×3/8)+(3²×1/8)=3  
 Var(X) \= E(X²) − \[E(X)\]² \= 3 − (1.5)² \= 0.75

✅ Mean \= 1.5, Variance \= 0.75

---

### **Q2. A random variable X has PDF f(x) \= 3x² for 0 ≤ x ≤ 1\.**

Find E(X) and Var(X).

E(X) \= ∫₀¹ x(3x²)dx \= 3∫₀¹ x³ dx \= 3/4  
 E(X²) \= ∫₀¹ x²(3x²)dx \= 3∫₀¹ x⁴ dx \= 3/5  
 Var(X) \= E(X²) − \[E(X)\]² \= 3/5 − (3/4)² \= 3/80 \= 0.0375

✅ Mean \= 0.75, Variance \= 0.0375

---

# **🔹 10\. Summary**

| Concept | Formula (in words) | Meaning |
| ----- | ----- | ----- |
| **Expectation (Mean)** | Multiply each value by its probability and add | Average outcome of the experiment |
| **E(X)** | Sum of xP(X=x) or area of xf(x) | Expected value |
| **Variance** | Weighted average of squared deviations from mean | Measures spread or variability |
| **Var(X)** | E(X²) − \[E(X)\]² | Shortcut formula |
| **Standard Deviation** | Square root of variance | Measure of consistency |

---

# **✅ Final Conceptual Summary**

* **Expectation** → the long-term average value of the random variable.

* **Variance** → how much the random variable’s values fluctuate around that average.

* **Together**, they describe the *shape and behavior* of a probability distribution.

---

