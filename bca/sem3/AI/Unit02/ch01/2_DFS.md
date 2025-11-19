# **Depth First Search (DFS)**

## **1. Introduction**

Depth First Search (DFS) is an important **uninformed search algorithm** used in AI and Data Structures.
It explores a graph or tree **deeply**, going down one branch completely before backtracking.

DFS is useful when the solution is located **deep in the search space** or when memory is limited.

---

## **2. What is DFS?**

* DFS explores the search space by going **as deep as possible** from the start state.
* When no further nodes exist, it **backtracks**.
* It uses a **Stack (LIFO)** for node exploration.
* DFS is a **blind/uninformed** search (no heuristics).

---

## **3. Characteristics of DFS**

### **3.1 Uninformed Search**

DFS does not use heuristic information.
It only uses available actions and the transition model.

### **3.2 Uses LIFO Strategy**

DFS is implemented using a **stack** (explicit or implicit through recursion).

### **3.3 Deep Exploration**

DFS tries to reach the bottom of the search tree before exploring siblings.

### **3.4 Completeness**

* **Not complete** for infinite depth spaces or cyclic graphs.

### **3.5 Optimality**

* **Not optimal**, because it may find a long-cost path instead of the shortest.

---

## **4. How DFS Works (Step-by-Step)**

### **4.1 DFS Algorithm Flow**

1. Start at the **initial node**.
2. Push it into the **stack**.
3. Repeat until stack becomes empty:

   * Pop top element (current node).
   * If goal, **stop**.
   * Else, push all **unvisited children** into the stack.
4. Continue deep exploration with backtracking.

---

## **5. DFS Example**

### **5.1 Graph Example**

```
     A
   /   \
  B     C
 / \   / 
D   E F
```

### **5.2 DFS Order**

**A → B → D → E → C → F**

* DFS goes deep into **B → D**, then backtracks to **E**, and then enters **C → F**.

---

## **6. DFS Implementation Approaches**

### **6.1 Iterative DFS Using Stack**

* Uses an explicit stack to manage nodes.
* Easy to control order and avoid recursion depth issues.

### **6.2 Recursive DFS**

* Function calls maintain the stack implicitly.
* Simple and readable but risky for very deep trees.

---

## **7. Advantages of DFS**

* **Memory Efficient** – stores only one path at a time.
* **Easy to Implement** – recursion or stack.
* Good for searching **deep solutions**.
* Useful in:

  * **Cycle detection**
  * **Topological sorting**
  * **Pathfinding in puzzles**

---

## **8. Disadvantages of DFS**

* **Not complete** for infinite or cyclic graphs.
* **Not optimal** (may return a longer path).
* May get stuck in **deep or infinite branches**.
* Requires careful handling of **visited nodes**.

---

## **9. Time and Space Complexity**

### **9.1 Time Complexity**

* **O(bᵐ)**
  where
  *b = branching factor*,
  *m = maximum depth*.

### **9.2 Space Complexity**

* **O(b × m)**
  Stores only one path + siblings.

---

## **10. Applications of DFS**

* Maze solving
* Finding connected components
* Detecting cycles in graphs
* Topological sorting
* Backtracking algorithms (N-Queens, Sudoku)
* Solving puzzles like Tower of Hanoi

---

## **11. Depth-Limited DFS**

* A variation of DFS with a **maximum depth limit L**.
* Avoids infinite loops in deep or unbounded trees.
* Used in **Iterative Deepening Search (IDS)**.

---

## **12. Summary**

DFS is a fundamental search technique that expands nodes deeply before backtracking.
Although it is not optimal or always complete, its low memory usage and ability to explore depth make it valuable in many AI and graph-based problems.

---

If you want, I can prepare:

📘 **Full Chapter Notes (with BFS, IDS, UCS, A*, etc.)**
📄 **PDF format with formatted headings**
🧾 **2-mark, 5-mark, 10-mark answers**

Just tell me: **“Continue with BFS”** or **“Make PDF”**.
