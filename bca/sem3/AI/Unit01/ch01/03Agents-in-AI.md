## 4\.  Understanding Agents:-

### **4.1   What is an Agent?**

An agent is any entity that can:

* Perceive (observe) its environment through sensors.  
* Act upon the environment using actuators.

***“An AI agent is a system that perceives its environment and takes actions to achieve a goal.”***

Examples of agents can be:

| Agent type  | Sensors | Actuators | Task |
| :---- | :---- | :---- | :---- |
| Robot Vacuum | Camera,Dust sensor | Wheels,Brushes | Clean the floor |
| Self-driving Car | Camera,GPS, Lidar | Steering, Accelerator | Drive safely on  roads |

### **4.2   List of Agents :-** 

* **Human-Agent:** A human agent has eyes, ears, and other organs which work for sensors and hand, legs, vocal tract work for actuators.

* **Robotic Agent:** A robotic agent can have cameras, infrared range finder, NLP for sensors and various motors for actuators.

* **Software Agent:** Software agent can have keystrokes, file contents as sensory input and act on those inputs and display output on the screen.

* **Gaming agents:** These are agents that are designed to play games, either against human opponents or other agents.  
 Examples:  chess-playing agents and poker-playing agents.

* **Fraud detection agents:** These are agents that are designed to detect fraudulent behavior in financial transactions.   
 Examples: those used by banks and credit card companies

* **Traffic management agents:** These are agents that are designed to manage traffic flow in cities. They can monitor traffic patterns, adjust traffic lights, and reroute vehicles to minimize congestion. 

### **4.3   Types Of Agents:**  
- **Reactive agents:** are those that respond to immediate stimuli from their environment and take actions based on those stimuli.

- **Proactive agents :**on the other hand, take initiative and plan ahead to achieve their goals.

> The environment in which agent operates can also be fixed or dynamic. Fixed environments have a static set of rules that do not change, while dynamic environments are constantly changing and require agents to adapt to new situations.

- **Multi-agent:** systems involve multiple agents working together to achieve a common goal. These agents may have to coordinate their actions and communicate with each other to achieve their objectives.

### **4.4   Components of an Agent:-** 

* **Sensors:**
  Devices that receive input from the environment  
  Example: Eyes, cameras, microphones  
* **Actuators:**  
  Devices that perform actions  
  Example: Motors, speakers, screen displays  
* **Perception:**  
  The data received through sensors  
  Example: Reading a traffic signal  
* **Agent Program:**  
  The brain of the agent  
  It decides what action to take based on the current perception.

## **5\. Rationality in AI:-**

### **5.1  The Concept of Rationality.**

**Rational Agent:**  
A rational agent chooses actions that maximize its expected performance, given:

* What it perceives (percept sequence)  
* What it knows  
* What actions it can take

**Rational ≠ Perfect:**

* Rational agents may make mistakes.  
* They do not require omniscience or infinite computation.  
* They aim to do the right thing based on current knowledge.

### **5.2   PEAS Representation of AI agent**

PEAS stands for performance measure, environment, actuators and sensors. It is a framework that is used to describe an AI agent. It's a structured approach to design and understand AI systems.  
1. **Performance measure:** Performance measure is a criterion that measures the success of the agent. It is used to evaluate how well the agent is achieving its goal.  
  For example, in a spam filter system, the performance measure could be minimizing the number of spam emails reaching the inbox.  

2. **Environment:** The environment represents the domain or context in which the agent operates and interacts. This can range from physical spaces like rooms to virtual environments such as game worlds or online platforms like the internet.  

3. **Actuators:** Actuators are the mechanisms through which the AI agent performs actions or interacts with its environment to achieve its goals. These can include physical actuators like motors and robotic hands, as well as digital actuators like computer screens and text-to-speech converters.  

4. **Sensors:** Sensors enable the AI agent to gather information from its environment, providing data that informs its decision-making process and actions. These sensors can capture various environmental parameters such as temperature, sound, movement, or visual input. 
  Examples of sensors include cameras, microphones, temperature sensors, and motion sensors.  


## **6\.   Environments:-**

An **environment** is the world in which an agent operates. It includes everything outside the agent that the agent can sense and interact with.  
Example: For a self-driving car, the environment includes: Roads, Traffic lights, Other vehicles, Pedestrians

### **6.1  The Nature of Environments :**

Environments differ in complexity. They are classified based on,

* **Observable vs. Partially Observable**  
- **Fully Observable:**  
  The agent has complete access to the environment's state.  
  Example: Chess (you can see the full board).  
- **Partially Observable:**  
  The agent has limited or incomplete information.  
  Example: Driving in fog (you can't see everything around).  
* **Deterministic vs. Stochastic**  
- **Deterministic:**  
  The next state of the environment is completely determined by the current state and the agent’s action.  
  Example: Solving a math puzzle.  
- **Stochastic:**  
  The environment has random elements, and outcomes are not predictable.  
  Example: Stock market prediction.  
* **Episodic vs. Sequential**  
- **Episodic:**  
  Each action is independent of the previous actions.  
  Example: Image classification (each image is separate).  
- **Sequential:**  
  Current actions affect future decisions.  
  Example: Playing a game (each move matters later).  
* **Static vs. Dynamic**  
- **Static:**  
  The environment does not change while the agent is thinking.  
  Example: Crossword puzzles.  
- **Dynamic:**  
  The environment changes while the agent is deciding.  
  Example: Real-time traffic navigation.  
* **Single-Agent vs. Multi-Agent**  
- **Single-Agent:**  
  Only one agent is operating in the environment.  
  Example: Puzzle solving.  
- **Multi-Agent:**  
  Multiple agents interact and may cooperate or compete.  
  Example: Soccer game with many players.