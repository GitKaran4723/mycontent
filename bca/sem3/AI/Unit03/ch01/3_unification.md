# **Unification**

## **What is Unification?** 

* Unification is a process of making two different logical atomic expressions identical by finding a substitution. Unification depends on the substitution process. 

It takes two literals as input and makes them identical using substitution.

## **Conditions for Unification:** 

* Following are some basic conditions for unification: Predicate symbol must be same, atoms or expression with different predicate symbol can never be unified.   
* Number of Arguments in both expressions must be identical.   
* Unification will fail if there are two similar variables present in the same expression. function unify(expression1, expression2): if expression1 is the same as expression2:

- return "SUCCESS“ if expression1 is a variable:   
    
- return substitute(expression1, expression2) 

- if expression2 is a variable: return substitute(expression2, expression1) 

- if both expressions are terms and not equal: 

- return "FAILURE“ if both expressions are functions or predicates with matching name and arity: 

- for each corresponding argument (arg1, arg2): 

- result \<- unify(arg1, arg2) 

- if result is "FAILURE": 

- return "FAILURE" return "SUCCESS“ 

- function substitute(variable, expression): 

- if variable occurs in expression: return "FAILURE“ 

- else: return {variable / expression} 

Example:   
“Eats(X, Apple)” is an expression 

“Eats(Riya, Y)” is an expression 

Comparison: 

Expression A(“Eats(X, Apple)”) is compared to Expression B (Eats (Riya, Y)”) Substitution Variable   
We can see that Expression A's first parameter is a variable "x," and the second argument is a constant “Apple.” 

The first parameter in Expression B is a constant "Riya," while the second argument is a variable “y.’’ 

## **Unifying Variables:**   
We unify the variable "x" in Expression A with "Riya" in Expression B. 

This results in the substitution: x \= Riya. 

We also unify the variable "y" in Expression B with the constant "Apple." 

This gives us the substitution: y \= Apple 

Applying Substitutions 

After substitutions, Expression A becomes "Eats(Riya, Apple).“ 

Expression B remains the same: "Eats(Riya, Apple).“ 

Unified Expression  
   
Both expressions are now identical: "Eats(John, Apple)."   
Unification is successful, and the unified expression is "Eats(Riya, Apple). 

## **Conditions for Unification:**  
The following are some fundamental requirements for unification: 

* Atoms or expressions with various predicate symbols can never be united.   
* Both phrases must have the same number of arguments.   
* If two comparable variables appear in the same expression, unification will fail.