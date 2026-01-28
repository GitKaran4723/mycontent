# **Closure of Relations**

# **1\. Inverse relation R^{−1}**

### **Definition**

For a relation R on a set A, R−1 = { ( b, a ) ∣ ( a, b ) ∈ R }

**Example**

If R = { ( 1, 2 ), ( 2, 3 ) }

Then R−1 = { ( 2, 1 ), ( 3, 2 ) }

### **Intuition**

Look at the relation **in the opposite direction**.

If a is related to b in R, then in R−1, b is related to a.

### **Use**

* To check **symmetry** of a relation

* To reverse dependencies (e.g., “is child of” vs “is parent of”)

* In graph theory: reversing all edges

# **2\. Transitive closure R+**

## **Definition**

The transitive closure of R is the **smallest transitive relation** containing R.

R+ = R ∪ R2 ∪ R3 ∪ ⋯

### **Example**

If R = { ( a, b ), ( b, c ) }

Then R+ = { ( a, b ), ( b, c ), ( a, c ) }

### **Intuition**

If you can go from a to c using **one or more steps**, then add ( a, c ). It captures **indirect relationships**.

### **Use**

* Finding **reachability** in graphs

* Prerequisite chains (course → course)

* “Can eventually influence” relations

* Ensuring a relation becomes **transitive**

## **3\. Reflexive–Transitive closure R∗**

## **Definition**

The reflexive–transitive closure of R is the **smallest reflexive and transitive relation** containing R.

R∗ = I ∪ R+

where I = { ( a, a ) ∣ a ∈ A }

### **Example**

If R = { ( a, b ), ( b, c ) }

Then R∗ = { ( a, a ), ( b, b ), ( c, c ), ( a, b ), ( b, c ), ( a, c ) }

### **Intuition**

You can either **stay where you are** or move through the relationship any number of times.

Includes paths of **zero or more steps**.

### **Use**

* Program execution steps

* State machines and automata

* Formal languages (Kleene star )

* Modeling repeated actions or processes

