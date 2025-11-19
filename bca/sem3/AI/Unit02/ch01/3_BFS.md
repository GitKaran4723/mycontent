Uninformed Search:-

**Search Algorithm Terminologies:**

* **Search:** Searching is a step by step procedure to solve a search-problem in a given

        search space.

* A search problem can have three main factors  
  **– Search Space:** Search space represents a set of possible solutions, which a system may have.  
  **– Start State:** It is a state from where agent begins the search.  
  **– Goal test:** It is a function which observe the current state and returns whether the goal state is achieved or not.  
    
* **Search tree:** A tree representation of search problem is called Search tree. The root of the search tree is the root node which is corresponding to the initial state.  
    
* **Actions**: It gives the description of all the available actions to the agent.  
    
* **Transition model**: A description of what each action do, can be represented as a transition model.  
    
* **Path Cost**: It is a function which assigns a numeric cost to each path.  
    
* **Solution:** It is an action sequence which leads from the start node to the goal node.  
    
* **Optimal Solution:** If a solution has the lowest cost among all solutions.

**Properties of Search Algorithms:**  
Following are the four essential properties of search algorithm to compare the efficiency of these algorithms:

– **Completeness:** A search algorithm is said to be complete if it guarantees to return a solution if at least any solution exists for any random input.

**– Optimality:** If a solution found for an algorithm is guaranteed to be the best solution (lowest path cost) among all other solutions, then such a solution for is said to be an optimal solution.

**– Time Complexity:** Time complexity is a measure of time for an algorithm to complete its task.

**– Space Complexity**: It is the maximum storage space required at any point during the search, as the complexity of the problem.

                          
            **Search Algorithm:**  
    
    

| Uninformed search | Informed search |
| :---- | :---- |
| **→**Breadth first search | **→**Best first search |
| **→**Uniform cost search | **→**A\*search |
| **→**Depth first search |  |
| **→**Depth limited search |  |
| **→**Iterative deeping depth first search |  |
| **→**bidirectional search |  |

   
**1.Informed Search (Heuristic Search)**

* Informed search uses **domain-specific knowledge** to guide the search.   
* It is also called **heuristic search.**   
* More efficient than uninformed search in complex problems.   
* Helps find a **good** solution faster, though not always the best one.   
* Suitable for solving **complex problems** like: **Traveling Salesman Problem.**

**2.Uninformed Search: Breadth-First Search (BFS)**

* BFS is a common **uninformed search strategy.**   
* It explores nodes **level by level** (i.e., breadth-wise), starting from the **root node**.   
* All the **nodes at the current depth** are expanded before moving to the next level.  
* It is a **general graph-search algorithm** and works for bot**h** trees and graphs.   
* BFS uses a **FIFO (First-In, First-Out) queue** to store nodes for exploration.

| Informed Search | Uninformed Search |
| :---- | :---- |
| Also known as Heuristic search | Also known as Blind search  |
| Requires information to perform search | Do not require information to perform search |
| Quick solution to problem | May be time consuming |
| Cost is low | Comparitively high in cost |
| It can be both complete and incomplete | It is always bound to complete |
| The AI gets suggestions regarding how and where to find a solution to any problem | The AI does not get any suggestions regarding what solution to find and where to find it. Whatever knowledge it gets is out of the information provided. |
| Eg: greedy Search A\* search AO\* Search Hill Climbing Algorithm | Eg: Depth-First Search(DFS) Breadth first Search Branch and Bound |

**How BFS Works:**

* Start from the root node.   
* Enqueue the root into the FIFO queue.   
* While the queue is not empty:   
- Dequeue a node.  
- Check if it's the goal.  
- If not, enqueue all its unvisited children.   
* Repeat the process level-by-level.