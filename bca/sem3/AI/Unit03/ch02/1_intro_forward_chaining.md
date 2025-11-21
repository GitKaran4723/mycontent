# **FORWARD CHAINING:**  

## **Inference Engine:** 

* It is important to understand about inference engine before learning about forward and backward chaining.   
* An inference engine is a system which applies logical reasoning to draw conclusions and solve a problem based on given facts.   
* It consists of algorithms that bring useful info from the knowledge base and use it to conclude new facts to the user's issues.   
* The inference engine uses two mechanisms, forward and backward chaining, in order to extract data from the knowledge base. 

## **Forward Chaining:**

* Forward chaining is a data-driven reasoning approach used by inference engines.   
* It starts with given facts and applies rules to derive new conclusions or facts from them.   
* The engine keeps applying the rules until it reaches a conclusion or cannot apply any more rules. It is based on logical prediction methodology.   
* One of its examples is the prediction of trends in the stock market. 

## **Characteristics:** 

* It is a bottom-up approach.   
* It starts with the initial state and progresses toward the end state to reach a conclusion.   
* It is a data-driven approach which utilizes given data.   
* It derives conclusions without any need for explicit guidance. 

Example:  
Given below are some facts and some rules:   
### **Facts:**   
1\. Sohail is a coder.   
2\. Sohail studies computer science. 

### **Rules:**   
1\. If a person is a coder, it means he enrolled in a college.   
2\. If a person is enrolled in a college and studies computer science, it means he learned DSA.   
Now, we will use forward chaining to derive a conclusion based on given facts and rules. 

**Step 1:** If a person is a coder, it means he enrolled in a college. 

* FOL: ∀ x (coder(x) → Enrolled\_IN(x, college))   
* Applying rule 1 to the fact: Enrolled\_IN(Sohail, college) 

**Step 2:** If a person is enrolled in a college and studied computer science, it means he learned DSA. 

* FOL: ∀ x,y (Enrolled\_In(x, college) רstudies(x, computer science) → Learned\_DSA(x))   
* Applying rule 2 to the fact: Learned\_DSA(Sohail) 

Final conclusion: Learned\_DSA(Sohail)   
In the above example, we used forward chaining to derive a conclusion based on given facts and rules. We converted facts and rules into FOL and reached the final conclusion. 

* Note: The FOL (First Order Logic) representation helps the inference engine to reach a conclusion effectively. 

##**Disadvantages:** 

* The inference engine generates information without knowing which data is more relevant and useful to reach the final result.   
* The inference engine may fire many unnecessary rules to reach the goal state.   
* The user may need to enter a lot of information to reach the goal state.   
* It can result in a high cost for the chaining process. 

