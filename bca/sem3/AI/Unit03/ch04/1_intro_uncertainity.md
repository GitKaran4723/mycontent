# **Uncertainty in Artificial Intelligence:**

→ Uncertainty is when there’s not enough information or ambiguity in data or decision-making. It is a fundamental concept in AI, as real-world data is often noisy and incomplete. AI systems must account for uncertainty to make informed decisions. 

## **Reasons for Uncertainty in Artificial Intelligence:**   
**1\. Partially Observable Environment:**   
The entire environment is not always in reach of the agent. There are some parts of the environment which are out of the reach of the agent and hence they are left unobserved. 

**2\. Dynamic Environment:**   
As we all know that the environment is dynamic, i.e. there are always some changes that keep taking place in the environment. 

**3\. Incomplete Knowledge of the Agent:**   
If the agent has incomplete knowledge or insufficient knowledge about anything, then it cannot produce correct results because the agent itself does not know about the situation and the way in which the situation is to be handled. 

**4\. Inaccessible Areas in the Environment:**   
There are areas in the environment which are observable, but not in reach of the agent to access. In such situations. The observation made is correct, but the as an agent cannot act on these parts of the environment, these parts will remain unchanged by the actions of the agent. 

## **Techniques for Addressing Uncertainty in AI:**  \>Nonmonotonic Logic Programming   
\> Probabilistic Logic Programming   
\> Fuzzy Logic Programming 

## **Nonmonotonic Logics:**   
A reasoning system is monotonic if the truthfulness of a conclusion does not change when new Information is added to the system the set of theorem can only monotonically grows when new axioms are added. In contrast, in a system doing non-monotonic reasoning the set of conclusions may either grow or shrink when new information is obtained.   
Example:  
\> Birds typically fly.   
\> Tweety is a bird.   
\> Tweety (presumably) flies. Such reasoning is characteristic of commonsense reasoning, where default rules are applied when case-specific information is not available. 

## **Probabilistic Reasoning in AI:**   
We know that there are many cases where the answer to the problem is neither completely true nor completely false. For example, the statement "Student will pass in the board exams.” We cannot say anything about a student's result before the results are declared. However, we can draw some predictions based on the student's past performances in academics.   
To extend the basic Boolean connectives to probability **functions:** negation: P( neg A)= 1 \- P(A)   
**conjunction: P**(A ^ B) \=P(A) \* P(B) if A and B are independent of each other   
**disjunction:** P(A v B)= P(A) \+ P(B) if A and B never happen at the same time 

## **Bayes Theorem in AI:**   
Bayes theorem is a method to find the probability of an event whose occurrence is dependent on some other event's occurrence.   
P(A|B) \= P(B|A)P(A)/ P(B)   
Where, A and B are events and P (B) not equal 0   
Here, **P( A|B):** Conditional probability of occurrence of event A when event B has already occurred.   
**P( B|A):** Conditional probability of occurrence of event B when event A has already occurred.   
**P(A):** Probability of occurrence of event A alone without any dependence on other events.   
**P(B):** Probability of occurrence of event B alone without any dependence on other events.

## **Challenges to probabilistic approaches:**   
Unknown probability values.   
Inconsistent probability assignments.   
Computational expense.