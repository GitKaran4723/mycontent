# **Types of Data & Features**

---

## **1\. Why Learn Types of Features?**

* Not all data is the same – some are **numbers**, some are **categories**, some are **ordered levels**.

* Different **preprocessing techniques** are applied depending on the type.

* Knowing feature type ensures the **right ML algorithm** and **right transformation** are used.

Example:

* "Age \= 20" → numeric (can calculate mean, std).

* "Gender \= Male" → category (no numerical order).

---

## **2\. Main Types of Data & Features**

### **A. Numerical Features**

* Represent measurable quantities.

* Divided into:

  1. **Discrete** – Countable, finite values (e.g., number of children, goals scored).

  2. **Continuous** – Infinite possible values in a range (e.g., height, temperature).

*Use in ML*:

* Can be scaled, normalized, used directly in regression/classification.

---

### **B. Categorical Features**

* Represent categories, labels, or groups.

* No numeric meaning unless encoded.

* Example: Gender (Male/Female), City (Delhi, Mumbai, Chennai).

*Use in ML*:

* Require **encoding** → One-hot encoding, Label encoding.

---

### **C. Ordinal Features**

* Ordered categories (ranking matters, but gap between values is not measurable).

* Example:

  * Education Level: Primary \< Secondary \< Graduate \< Postgraduate

  * Customer feedback: Poor \< Average \< Good \< Excellent

*Use in ML*:

* Must preserve **order** when encoding (use label encoding carefully).

---

### **D. Interval Features**

* Numeric data with meaningful differences, but **no true zero**.

* Example: Temperature in Celsius (0 °C ≠ absence of temperature).

*Use in ML*:

* Can add/subtract but cannot multiply/divide meaningfully.

---

### **E. Ratio Features**

* Numeric data with **absolute zero** (zero means absence).

* Example: Height, weight, age, income.

*Use in ML*:

* All operations (add, subtract, multiply, divide) valid.

* Most powerful type of feature.

---

## **3\. Summary Table**

| Type | Examples | Operations Allowed | Notes |
| ----- | ----- | ----- | ----- |
| Discrete | Number of children, goals | Count, compare | Whole numbers only |
| Continuous | Height, weight, temperature | All numeric ops | Infinite values possible |
| Categorical | Gender, City, Blood group | Equality check | Needs encoding |
| Ordinal | Education level, Rankings | Compare order | Order matters, not distance |
| Interval | Temperature (°C, °F), Calendar | Add/Subtract | No true zero |
| Ratio | Income, Age, Distance | All operations | Has absolute zero |

---

## **4\. Example**

Imagine we are predicting **Student Performance**:

| Name | Age | Gender | Attendance | Grade |
| ----- | ----- | ----- | ----- | ----- |
| A | 18 | Male | 80% | Good |
| B | 19 | Female | 90% | Excellent |
| C | 20 | Male | 60% | Average |

* Age → **Ratio (continuous numeric)**

* Gender → **Categorical**

* Attendance → **Ratio (continuous numeric)**

* Grade → **Ordinal**

---

## **5\. Why Does This Matter in ML?**

* **Numerical features** → scale/normalize before distance-based models (KNN, SVM).

* **Categorical features** → encode (one-hot, label).

* **Ordinal features** → preserve order when encoding.

* **Interval & Ratio** → decide what mathematical operations are meaningful.

---

