## **04.Create a dictionary with students name(minimum 5\) as keys and a list of (students,marks) tuples as values:**

```
print("Students details:")

students = {
    "maya": [("ai", 77), ("dbms", 67), ("java", 56)],
    "piya": [("ai", 56), ("dbms", 45), ("java", 89)],
    "rahul": [("ai", 88), ("dbms", 72), ("java", 91)],
    "kiran": [("ai", 69), ("dbms", 80), ("java", 73)],
    "anu": [("ai", 95), ("dbms", 89), ("java", 84)]
}

for name, marks in students.items():
    print(f"Name: {name}")
    total_marks = 0

    for subject, cc in marks:
        print(f"{subject} = {cc}")
        total_marks += cc

    print(f"Total Marks: {total_marks}")
    percentage = (total_marks / 300) * 100
    print(f"Percentage: {percentage}\n")
```

### **Output:**

- **Students details:**  
- **Name:maya**

      **\> ai=77**  
      **\> dbms=67**  
      **\> java=56**  
      **\> total\_marks:200**  
      **\> Percentage:66.66666666666666**

- **Name:priya**

     **\> ai=56**  
     **\> dbms=45**  
     **\> java=89**  
     **\> total\_marks:190**  
     **\> Percentage:63.33333333333333**

- **Name:rahul**

     **\> ai=88**  
     **\> dbms=72**  
     **\> java=91**  
     **\> total\_marks:251**  
     **\> Percentage:83.66666666666667**

- **Name:kiran**

     **\> ai=69**  
     **\> dbms=80**  
     **\> java=73**  
     **\> total\_marks:222**  
     **\> Percentage:74.0**

- **Name:anu**

     **\> ai=95**  
     **\> dbms=89**  
     **\> java=84**  
     **\> total\_marks:268**  
     **\> Percentage:89.33333333333333**

## **05.Implement depth-first search (DFS) on a small graph:**

```
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    print(start)

    for neighbour in graph[start]:
        if neighbour not in visited:
            dfs(graph, neighbour, visited)

print("DFS nodes:")
dfs(graph, 'A')
```

### **Output:**

- **DFS nodes:** 

      **A**  
      **B**  
      **D**  
      **E**  
      **F**  
      **C**

## **06.Solve the Water Jug Problem using Breadth-first search:**

```
from collections import deque
def bfs(cap1, cap2, target):
    start = (0, 0)
    visited = set([start])
    queue = deque([(start, [start])])

    while queue:
        start, path = queue.popleft()
        x, y = start

        if x == target or y == target:
            return path

        for nxt in get_successor(start, cap1, cap2):
            if nxt not in visited:
                visited.add(nxt)
                queue.append((nxt, path + [nxt]))

    return None


def get_successor(start, cap1, cap2):
    x, y = start
    succ = []

    succ.append((cap1, y))        # Fill jug1
    succ.append((x, cap2))        # Fill jug2

    succ.append((0, y))           # Empty jug1
    succ.append((x, 0))           # Empty jug2

    pour = min(x, cap2 - y)       # Pour jug1 -> jug2
    succ.append((x - pour, y + pour))

    pour = min(cap1 - x, y)       # Pour jug2 -> jug1
    succ.append((x + pour, y - pour))

    return succ


cap1, cap2, target = 4, 3, 2
solution = bfs(cap1, cap2, target)

if solution:
    print("Solution found")
    for state in solution:
        print(f"jug1:{state[0]}, jug2:{state[1]}")
else:
    print("solution not found")
```

### **Output:**

- **Solution found**

      **jug1:0, jug2:0**  
      **jug1:0, jug2:3**  
      **jug1:3, jug2:0**  
      **jug1:3, jug2:3**  
      **jug1:4, jug2:2**

