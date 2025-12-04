## **01.Write a Python program which accepts a number and prints its prime factors.**

```
def primefactors(n):  
    factors=[]  
    while n % 2 == 0:  
        factors.append(2)  
        n//=2  
    i=3  
    while i*i <= n:  
        while n % i ==0:  
            factors.append(i)  
            n //=i  
        i += 2  
    if n>2:  
        factors.append(n)  
    return factors  
num=int(input("Enter a number: "))  
if num <= 1 :  
    print("Prime factors are not defined for numbers less than 2")  
else:  
    print("Prime numbers are", num,"are",primefactors(num))
``` 


### **Output:**

- **Enter a number: 789**

      **Prime numbers are 789 are \[3, 263\]**

- **Enter a number: 666**

      **Prime numbers are 666 are \[2, 3, 3, 37\]**

## **02.Write a python that checks whether a given password is valid.**  
## **An acceptable password:**

1)  **Should have minimum 8 characters.**  
2)  **Must have atleast one digit and one special character.**  
3)  **Must contain atleast one alphabet which is in uppercase.**

```
def is_valid_password(password):  
    if len(password) < 8:  
        return "Must have atleast 8 characters"  
    if not any(ch.isdigit() for ch in password):  
        return " must have atleast 1 digit"  
    if not any(ch.isupper() for ch in password):  
        return "must have atleast 1 uppercase letter"  
    if not any(not ch.isalnum() for ch in password):  
        return "must have atleast 1 special character"  
    return "valid password"  
password=input("Enter a password: ")  
msg=is_valid_password(password)  
print(msg)  
```   

### **Output:**

- **Enter a password: Computer@123**

      **valid password**

- **Enter a password: computer@123**

      **must have atleast 1 uppercase letter**

- **Enter a password: Computer12**

      **must have atleast 1 special character**

- **Enter a password: Computer@@**

      **must have atleast 1 digit**

## **03.Write a program that creates a list and performs the following operations on the list.**

1)  **Mean,median and mode.**  
2)  **Maximum and minimum values in the list.**  
3)  **Sort the list.**  
4)  **Remove duplicate values from the list.**  
   
```
from collections import Counter 
def list_operations(): 
    try:
        numbers=list(map(int,input("Enter a number seperated by space: ").split()))  
    except ValueError:  
        print("Invalid input! Please enter only interger")
        return
    if not numbers:
        print("List is empty")  
        return
    print("Original list: ",numbers)
    mean=sum(numbers)/len(numbers)  
    print("Mean :",mean)  
    sorted_numbers=sorted(numbers)  
    n=len(sorted_numbers)  
    if n % 2 == 1:  
        median=sorted_numbers[n//2]
    else:
        median=(sorted_numbers[n//2-1]+sorted_numbers[n//2])/2  
    counts=Counter(numbers)  
    max_freq=max(counts.values()) 
    mode=[num for num,freq in counts.items() if freq==max_freq]  
    if max_freq==1:  
        print("Mode: No mode(all values occurs only once."))
    else: 
        print("Mode: ",mode if len(mode)>1 else mode[0])  
        print("Median: ",median)  
        print("Mode: ",mode)  
        print("Maximum: ",max(numbers)) 
        print("Minimun: ",min(numbers))  
        print("Sorted list is: ",sorted_numbers) 
        unique_list=sorted(set(numbers))  
        print("List without duplicate: ",unique_list) 
list_operations()
```

### **Output:**

- **Enter a number seperated by space: 45 56 76 12 34 45**

      **\> Original list:  \[45, 56, 76, 12, 34, 45\]**  
      **\> Mean : 44.666666666666664**  
      **\> Mode:  45**  
      **\> Median:  45.0**  
      **\> Mode:  \[45\]**  
      **\> Maximum:  76**  
      **\> Minimum:  12**  
      **\> Sorted list is:  \[12, 34, 45, 45, 56, 76\]**  
      **\> List without duplicate:  \[12, 34, 45, 56, 76\]**

