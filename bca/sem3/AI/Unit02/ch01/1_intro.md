# Chapter 1: Uninformed & Informed Search

## Introduction to Search in Artificial Intelligence

Search is a fundamental problem-solving technique used in Artificial Intelligence.
An **AI agent** explores different possible actions and states to reach the desired goal.
Search algorithms help the agent decide **which path to follow** from the initial state to the goal state.

### What is a Search Problem?

A search problem consists of:

* **Initial State** → Where the agent starts
* **Goal State** → Desired objective
* **Actions** → Possible moves
* **Transition Model** → Rules that describe the results of actions
* **Path Cost** → Cost of moving from one state to another

The collection of all possible states and transitions forms the **Search Space**.

---

## Types of Search Techniques

Search methods are broadly classified into **Uninformed Search** and **Informed Search**.

---

## Uninformed (Blind) Search

### Definition

Uninformed search algorithms **have no additional information** about the goal other than the definition of the initial and goal states.
They **blindly explore** the search space.

### Characteristics

* No prior knowledge about goal direction
* Simple and easy to implement
* Often explores unnecessary paths
* May take more time and memory

### Common Uninformed Search Algorithms

* **Depth First Search (DFS)**
* **Breadth First Search (BFS)**
* **Uniform Cost Search (UCS)**
* **Iterative Deepening Search (IDS)**

---

## Informed (Heuristic) Search

### Definition

Informed search algorithms use **extra knowledge or heuristics** (estimated cost to reach the goal) to guide the search efficiently.

### Characteristics

* Uses heuristic function **h(n)**
* Faster and more efficient than uninformed search
* Reduces search space
* Suitable for complex problems

### Common Informed Search Algorithms

* **Best First Search**
* **A* Search Algorithm**
* **Greedy Search**
* **AO* Algorithm**

---

## Heuristics in Search

A **heuristic** is a rule-of-thumb or estimate that helps decide which path is more promising.
Examples:

* Straight-line distance between two cities
* Number of misplaced tiles in an 8-puzzle

Better heuristics lead to **faster search and better solutions**.

---

## Importance of Search in AI

* Helps solve complex real-world problems
* Used in **navigation, robotics, decision-making, games, planning**
* Provides a structured method for exploring possibilities
* Forms the foundation for many advanced AI techniques

---
