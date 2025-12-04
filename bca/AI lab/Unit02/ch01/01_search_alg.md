## **07.Find the shortest path in 4\*4 grid using A\* search:**

```
import heapq

def heuristic(a, b):
    return abs(a[0] - b[0]) + abs(a[1] - b[1])

def astar(grid, start, goal):
    rows, cols = len(grid), len(grid[0])
    open_list = [(0, start, [start])]
    visited = set()

    while open_list:
        f, (x, y), path = heapq.heappop(open_list)

        if (x, y) == goal:
            return path

        if (x, y) in visited:
            continue

        visited.add((x, y))

        for dx, dy in [(1, 0), (-1, 0), (0, 1), (0, -1)]:
            nx = x + dx
            ny = y + dy

            if 0 <= nx < rows and 0 <= ny < cols and grid[nx][ny] == 0:
                heapq.heappush(open_list,
                               (len(path) + heuristic((nx, ny), goal),
                                (nx, ny),
                                path + [(nx, ny)]))

    return None

grid = [
    [0, 0, 0, 0],
    [0, 1, 1, 0],
    [0, 0, 0, 0],
    [0, 1, 0, 0]
]

path = astar(grid, (0, 0), (3, 3))
print(path)
```

### **Output:**

- **\[(0, 0), (1, 0), (2, 0), (2, 1), (2, 2), (3, 2), (3, 3)\]**

## **08.Implement the Min-max search algorithm for two player games, you may use game tree with three levels:**

```
def Minimax(node, is_max):
    if type(node) is int:
        return node

    if is_max:
        return max(Minimax(child, False) for child in node)
    else:
        return min(Minimax(child, True) for child in node)


node = [[3, 5], [2, 9], [12, 5]]
goal = Minimax(node, False)
print(goal)
```

### **Output:**

- **5**

## **09.Implement the rule-based expert system for whether classification:**

```
def weather(h, t, w):
    if h \== "high" and t \== "low" and w \== "low":
        print("Weather is Sunny")  
    elif h \== "high" and w \== "low":
        print("Weather is Rainy")  
    elif w \== "high" and t \== "low":  
        print("Weather is Windy") 
    elif h \== "high" and w \== "high":  
        print("Weather is Stormy") 
    else:  
        print("Weather is Uncertain") 
h \= input("Enter the Humidity: ")  
w \= input("Enter the Wind: ")
t \= input("Enter the Temperature: ")  
weather(h, t, w)
```

### **Output:**

- **Enter the Humidity: low**  
- **Enter the Wind: high**  
- **Enter the Temperature: low**

    **\> Weather is Windy**

- **Enter the Humidity: high**  
- **Enter the Wind: low**  
- **Enter the Temperature: low**

    **\> Weather is Sunny**

