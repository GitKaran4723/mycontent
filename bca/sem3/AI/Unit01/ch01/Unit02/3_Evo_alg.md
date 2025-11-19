# **Evolutionary Algorithm (EA):**  
An EA is a class of optimization algorithms inspired by biological evolution. It searches for solutions by evolving a population of candidate solutions over time.  
   
## **Key Concepts:** 

* Population: A set of candidate solutions   
* Fitness function: Measures the quality of a solution   
* Selection: Chooses which individuals get to reproduce   
* Crossover (Recombination): Combines parts of two solutions   
* Mutation: Introduces small random changes   
* Generations: Iterative refinement over time 

Examples: 

- Genetic Algorithms (GAs)   
- Evolution Strategies (ES)   
- Genetic Programming (GP) 

## **Applications:** 

* Optimization problems (traveling salesman, design, tuning).


## **Genetic Algorithm:**   
A Genetic Algorithm (GA) is a type of Evolutionary Algorithm (EA) inspired by the process of natural selection. It is used to find approximate solutions to optimization and search problems, especially when the solution space is large, complex, or poorly understood. 

## **Genetic Algorithm: Step-by-Step** 

* Initialize a random population of individuals.   
* Evaluate fitness of each individual.   
* Repeat until termination condition (e.g., max generations):   
* Select parents based on fitness (e.g., tournament, roulette wheel)   
* Crossover selected parents to produce children   
* Mutate some children with low probability   
* Evaluate new individuals  
* Replace old population with new one (or use elitism to keep best) 


## **Advantages:**

* Works well for complex or nonlinear problems   
* Doesn’t need gradient or derivative information   
* Easily parallelizable   
* Robust to local minima.

## **Disadvantages:**

* No guarantee of optimality   
* May require many evaluations (computationally expensive)   
* Parameter tuning (population size, mutation rate) is tricky   
* Poor performance on simple or well-structured problems (compared to CSP methods) 


## **Applications of Evolutionary Search in AI:**  
### **1\. Neural Network Optimization (Neuro evolution)**

- **What it does:** Evolves neural network weights, architectures, or hyper parameters.   
- **Why use it:** Traditional training (like backpropagation) struggles with complex architectures or non-differentiable components. 

### **2\. Reinforcement Learning (RL)**

- **Evolutionary Role:** Learn policies without gradient information.   
- **Use Case:** When rewards are sparse or delayed, evolutionary methods can evolve entire policy networks.   
- **Example:** Evolving policy parameters for agents in environments like OpenAI Gym.


### **3\. Game Playing and Strategy Evolution** 

- **What it does:** Evolves strategies, agents, or game-playing logic.   
- **Examples:**   
* Genetic Programming for evolving chess strategies 


### **4\. Robotics (Control and Morphology Evolution)** 

- **Controller Evolution:** Evolve motion behaviors (e.g., walking, balancing).   
- **Morphology Evolution:** Co-evolve both the body and brain of robots.   
- **Examples:**   
* Legged robot gait optimization 


### **5\. Feature Selection & Extraction** 

- **Goal:** Select or evolve optimal subsets of features from high-dimensional data.   
- **Used in:** Preprocessing for machine learning tasks (classification, clustering,regression)  
- **Why:** Reduces overfitting,improves model accuracy.