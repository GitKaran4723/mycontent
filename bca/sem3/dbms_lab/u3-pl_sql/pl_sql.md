# **PL SQL:**

### **01\. Write a PL/SQL Code to add two numbers:**

>DELIMITER //  
 CREATE PROCEDURE add_num()  
    BEGIN  
    DECLARE a INT DEFAULT 10;  
    DECLARE b INT DEFAULT 20;  
    SELECT a \+ b AS sum;  
    END //  
DELIMITER ;  
CALL add_num();

**Output:**

| sum |
| ----- |
| 30 |

### **02\. Write a PL/SQL code for Fibonacci series:**

> DELIMITER //  
CREATE PROCEDURE fibo(IN n INT)  
BEGIN  
    DECLARE a INT DEFAULT 0;  
    DECLARE b INT DEFAULT 1;  
    DECLARE c INT;  
    DECLARE i INT DEFAULT 3;
    SELECT a AS fibo;  
    SELECT b AS fibo;
    WHILE i <= n DO  
        SET c = a + b;  
        SELECT c AS fibo;  
        SET a = b;  
        SET b = c;  
        SET i = i + 1;  
    END WHILE;  
END //  
DELIMITER ;  
CALL FIBO(7);

**Output:**

| fibo |
| ----- |
| 0 |
| 1 |
| 1 |
| 2 |
| 3 |
| 5 |
| 8 |

### **03\.  Write a PL/SQL Code for greatest of 3 numbers** 

> DELIMITER //  
CREATE PROCEDURE got(a INT, b INT, c INT)  
BEGIN  
    DECLARE greatest INT;
    IF a >= b AND a >= c THEN  
        SET greatest = a;  
    ELSEIF b >= c THEN  
        SET greatest = b;  
    ELSE  
        SET greatest = c;  
    END IF;
    SELECT greatest AS 'Greatest Number';  
END //
DELIMITER ;  
CALL got(25, 42, 17);

**Output:**

| Greatest Number |
| ----- |
| 42 |

### **04\. Write a PL/SQL code for area and circumference of a circle** 

> DELIMITER //  
CREATE PROCEDURE ac(IN r FLOAT)  
BEGIN  
    DECLARE pi FLOAT DEFAULT 3.14;  
    SELECT pi * r * r AS Area;  
    SELECT 2 * pi * r AS Circumference;  
END //  
DELIMITER ;  
CALL ac(7);

**Output:**

| Area |
| ----- |
| 153.86000514030457 |

| Circumference |
| ----- |
| 43.9600014686584 |

### **05\. Write a PL/SQL code for factorial of a number:**

> DELIMITER //  
CREATE PROCEDURE fact(IN n INT)  
BEGIN  
    DECLARE i INT DEFAULT 1;  
    DECLARE f INT DEFAULT 1;
    WHILE i <= n DO  
        SET f = f * i;  
        SET i = i + 1;  
    END WHILE;
    SELECT f AS factorial;  
END //
DELIMITER;  
CALL fact(5);

**Output:**

| Factorial |
| ----- |
|        120 |

