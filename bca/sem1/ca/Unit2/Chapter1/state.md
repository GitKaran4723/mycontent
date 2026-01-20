## **State Table (Sequential Circuits) – Full Explanation**

### **1\. Definition**

A **State Table** is a **tabular representation** of a sequential circuit that shows:

* The **present state** of the system

* The **inputs** applied

* The resulting **next state**

* (Optional) the **output** corresponding to that state and input

In simple words: it tells you **“If I’m in this state and I apply these inputs, what will the next state and outputs be?”**

---

### **2\. Components of a State Table**

A state table typically includes:

| Present State | Inputs | Next State | Output |
| :---: | :---: | :---: | :---: |

**Definitions:**

* **Present State (PS):** Current stored value(s) of the flip-flops

* **Inputs (X, Y…):** External signals applied to the circuit

* **Next State (NS):** Value(s) that the flip-flops will store after the clock edge

* **Output (Z):** Circuit output, depends on PS (and sometimes inputs, depending on Mealy or Moore type)

---

### **3\. Purpose of a State Table**

1. Shows **all possible states** of a sequential circuit

2. Helps in designing the **next-state logic** and **output logic**

3. Basis for deriving:

   * **Flip-Flop input equations**

   * **Boolean expressions** for next states and outputs

4. Essential for **state diagram** creation

---

### **4\. Types of Sequential Circuits**

* **Moore Machine:** Output depends **only on the present state**

* **Mealy Machine:** Output depends **on present state and inputs**

**State table difference:**

| Type | Output Depends On |
| ----- | ----- |
| Moore | Present State only (Z = f(Q)) |
| Mealy | Present State \+ Inputs (Z = f(Q, X)) |

---

### **5\. How to Construct a State Table**

**Step 1:** Identify flip-flops and number of states

* Number of flip-flops = n → number of possible states = 2^n

**Step 2:** List all **present states** in binary form

* Example: 2 flip-flops → states 00, 01, 10, 11

**Step 3:** List all **possible inputs**

**Step 4:** Determine **next state** for each combination of present state and input

* Use **flip-flop excitation table** to decide the input signals to the flip-flop

**Step 5:** Determine **outputs**

* For Moore → based on present state

* For Mealy → based on present state \+ input

---

### **6\. Example: D Flip-Flop Sequential Circuit**

Suppose a sequential circuit has **1 D flip-flop** and 1 input X.

**Step 1:** Flip-flop → 1 → possible states = 0, 1  
 **Step 2:** Inputs → X = 0, 1  
 **Step 3:** Determine next state using D = X ⊕ Q

**State Table:**

| Present State Q | Input X | Next State Q' | Description |
| ----- | ----- | ----- | ----- |
| 0 | 0 | 0 | No change |
| 0 | 1 | 1 | Toggle to 1 |
| 1 | 0 | 1 | No change |
| 1 | 1 | 0 | Toggle to 0 |

*   
  Here, **D = Q\_next** (D Flip-Flop rule)

* Next state column shows **Q after the clock edge**

---

### **7\. Relation to Flip-Flop Input Equations**

* From the state table, you can **derive the input equations for flip-flops**:

  * For **D flip-flop:** D = Q\_next

  * For **T flip-flop:** T = Q ⊕ Q\_next

  * For **JK flip-flop:** J = Q’ • Q\_next, K = Q • Q\_next’

* This is how **state tables are the foundation for sequential circuit design**.

---

### **8\. Key Points / Summary**

1. State table shows **present state, input, next state, and output**

2. Essential for **designing sequential circuits**

3. Different for **Moore vs Mealy machines**

4. Directly used to **derive flip-flop input equations**

5. Always consider **all combinations of inputs and present states**

---

💡 **Tip:**

* **Always label your states clearly** (binary or symbolic: A, B, C…)

* **Next state = what flip-flop outputs after clock edge**

* **Outputs = depend on Moore (PS) or Mealy (PS \+ input)**

## **1\. State Diagram – Definition**

A **State Diagram** is a **graphical representation of a sequential circuit**, showing:

* **States** as circles (or nodes)

* **Transitions between states** as arrows

* **Inputs** that cause transitions

* **Outputs** (for Moore or Mealy machines)

Simply: It’s a **visual version of the State Table**.

---

### **2\. Components of a State Diagram**

1. **States (Circles)**

   * Represent the **flip-flop outputs** (present state)

   * Example: Q = 0 or 1, or for multiple flip-flops: Q1Q0 = 00, 01, 10, 11

2. **Transitions (Arrows)**

   * Show **movement from one state to another** based on **input conditions**

   * Labeled with **input / output** if needed

3. **Start State**

   * Often marked with an **arrow pointing to the first state**

4. **Outputs**

   * **Moore machine:** Output inside the state circle

   * **Mealy machine:** Output on the transition arrow

---

### **3\. State Diagram vs State Table**

| State Table | State Diagram |
| ----- | ----- |
| Tabular form | Graphical form |
| Lists PS, Inputs, NS, Outputs | Shows states as circles & transitions |
| Easy for Boolean derivation | Easy to visualize behavior |
| Good for **input equations** | Good for **conceptual understanding** |

---

### **4\. Steps to Draw a State Diagram**

1. Identify **flip-flops** → number of states = 2^n

2. Label **all possible present states** (PS)

3. Determine **next state (NS)** for each PS based on inputs

4. Draw **arrows from PS → NS**

5. Label arrows with **input / output** (Mealy) or states with outputs (Moore)

---

### **5\. Example: D Flip-Flop with One Input X**

* **Flip-flop:** D (1 flip-flop → 2 states: 0,1)

* **Input:** X

* **Next state:** D = X ⊕ Q (toggle if X=1, else hold)

**State Table:**

| Q (Present) | X | Q' (Next) |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**State Diagram:**

* **State 0:**

  * X=0 → stay in 0

  * X=1 → go to 1

* **State 1:**

  * X=0 → stay in 1

  * X=1 → go to 0

*(Arrows labeled with X values)*

---

### **6\. Problems / Examples with State Diagrams**

**Problem 1:** Design a sequential circuit to **toggle output Q on input X=1** using a D Flip-Flop.

**Solution:**

1. Identify states → Q = 0 or 1

2. Determine next state: Q\_next = Q ⊕ X

3. Draw state table:

| Q | X | Q' |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

4.   
   Draw state diagram:

* Circle for Q=0, arrow X=0 stays in 0, X=1 goes to 1

* Circle for Q=1, arrow X=0 stays in 1, X=1 goes to 0

**Problem 2:** Convert a **Moore machine** to a **Mealy machine**.

* Moore outputs depend on **state**, Mealy depends on **state \+ input**

* Use **state diagram** to redraw transitions with outputs on arrows

**Problem 3:** Given a **state diagram**, derive **flip-flop input equations**

* Step 1: Label states as binary values (flip-flop outputs)

* Step 2: Make **state table from diagram**

* Step 3: Use **excitation table** to find flip-flop inputs

---

### **7\. Tips for State Diagram Problems**

1. Always label **states clearly** (binary or symbolic A,B,C…)

2. Draw **all transitions** for each input combination

3. Use **different arrow styles or labels** for Mealy vs Moore outputs

4. Check **completeness** → ensure every PS \+ input has an arrow

---

✅ **Summary**

* **State diagram:** visual version of state table

* **States:** circles, **outputs:** inside or on arrows

* **Transitions:** arrows labeled with input/output

* Used to **design sequential circuits, derive input equations, and understand behavior**

