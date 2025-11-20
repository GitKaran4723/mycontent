# **Adversarial Search:**

Adversarial search is a search, where we examine the problem which arises when we try to plan ahead of the world and other agents are planning against us. 

* We studied search strategies which are only associated with a single  agent that aims to find the solution which often expressed in the form of a sequence of actions.   
* But, there might be some situations where more than one agent is searching for the solution in the same search space, and this situation usually occurs in game playing.   
* The environment with more than one agent is termed as multi-agent environment, in which each agent is an opponent of other agent and playing against each other. Each agent needs to consider the action of  other agent and effect of that action on their performance.   
* So, Searches in which two or more players with conflicting goals are trying to explore the same search space for the solution, are called adversarial searches, often known as Games.   
* Games are modeled as a Search problem and heuristic evaluation function, and these are the two main factors which help to model and  solve games in AI. 


## **Types of Games in AI:** 

* **Perfect  information:** A game with the perfect information is that in which agents can look into the complete board. Agents have all the information about the game, and they can see each other moves also. Example: Chess.   
* **Imperfect  information:** If in a game agents do not have all information about the game and not aware with what's going on, such type of games are called the game with imperfect information, such as tic-tac-toe, blind, etc.   
* **Deterministic games**: Deterministic games are those games which follow a strict pattern and set of rules for the games, and there is no randomness associated with them. Example:chess.   
* **Non-deterministic games:** Non-deterministic are those games which have various unpredictable events and has a factor  of  chance  or  luck.  This  factor of  chance  or  luck  is introduced by either dice or cards. These are random, and each action response is not fixed. Such games are also called as stochastic games. Example: Poker, etc. 


## **Zero-Sum Games:**

* Zero-sum games are adversarial search which involves pure competition   
* In Zero-sum game each agent's gain or loss of utility is exactly balanced by the losses or gains of utility of another agent.   
* One player of the game try to maximize one single value, while other player tries to minimize it.   
* Each move by one player in the game is called as ply.   
* Chess and tic-tac-toe are examples of a Zero-sum game.  
   

## **Zero-sum game: Embedded thinking** 

* The Zero-sum game involved embedded thinking in which one agent or player is trying to figure out: 

• What to do.   
• How to decide the move   
• Needs to think about his opponent as well   
• The opponent also thinks what to do 

* Each of the players is trying to find out the response of  his  opponent  to  their actions. This  requires embedded thinking or backward reasoning to solve the game problems in AI.  
   

