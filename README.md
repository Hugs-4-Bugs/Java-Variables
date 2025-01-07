# Java Variables – Types of Variables

A variable in Java can be thought of as a box that stores data values during the execution of a Java program. The box has a fixed size, defined by the type of the variable, but its contents can be changed. Variables are the basic unit of storage in a Java program, and each variable has a name representing its memory location.

---

## Types of Variables

1. **Local Variable**  
2. **Instance Variable**  
3. **Class/Static Variable**  

---

## Variable Declaration and Initialization

### 1. Declaration:  
Before using a variable, you must declare it by specifying its data type and name.  
**Example:**  
```java
int age; // Declaration of an integer variable named age
```

### 2. Initialization:  
After declaring a variable, you can optionally initialize it by assigning it an initial value. Uninitialized variables have default values depending on their type.  
**Example:**  
```java
int age = 25; // Initialization of the age variable with a value of 25
```

### 3. Data Types:  
Java supports various data types for variables, including:  
- Primitive types (e.g., `int`, `double`, `boolean`, `char`)  
- Reference types (e.g., objects and arrays)  

---

## 1. Local Variables

- Declared inside methods, constructors, or blocks.
- Created when the method, constructor, or block is entered and destroyed when it exits.
- Cannot have access modifiers (e.g., `private`, `public`).  
- Must be initialized before the first use as they do not have default values.  

### Example 1: Local variable with initialization  
```java
public class Test {
    public void pupAge() {
        int age = 0;
        age = age + 7;
        System.out.println("Puppy age is: " + age);
    }

    public static void main(String[] args) {
        Test test = new Test();
        test.pupAge();
    }
}
```
**Output:**  
```
Puppy age is: 7
```

### Example 2: Local variable without initialization  
```java
public class Test {
    public void pupAge() {
        int age;
        age = age + 7;
        System.out.println("Puppy age is: " + age);
    }

    public static void main(String[] args) {
        Test test = new Test();
        test.pupAge();
    }
}
```
**Output:**  
```
Error: variable 'age' might not have been initialized
```

---

## 2. Instance Variables

- Declared in a class but outside methods, constructors, or blocks.  
- Created when an object is instantiated and destroyed when the object is destroyed.  
- Typically made private but can have other access modifiers.  
- Have default values: `0` for numeric types, `false` for `boolean`, and `null` for object references.  

### Example: Instance variables
```java
public class Employee {
    public String name;  // Instance variable
    private double salary; // Instance variable

    public Employee(String empName) {
        name = empName;
    }

    public void setSalary(double empSal) {
        salary = empSal;
    }

    public void printEmp() {
        System.out.println("Name: " + name);
        System.out.println("Salary: " + salary);
    }

    public static void main(String[] args) {
        Employee empOne = new Employee("Ransika");
        empOne.setSalary(1000);
        empOne.printEmp();
    }
}
```
**Output:**  
```
Name: Ransika
Salary: 1000.0
```

---

## 3. Class/Static Variables

- Declared with the `static` keyword in a class but outside methods, constructors, or blocks.  
- Shared among all objects of the class.  
- Typically used for constants or class-wide properties.  
- Have default values similar to instance variables.  

### Example: Static variables
```java
public class Employee {
    private static double salary;  // Static variable
    public static final String DEPARTMENT = "Development"; // Constant

    public static void main(String[] args) {
        salary = 1000;
        System.out.println(DEPARTMENT + " average salary: " + salary);
    }
}
```
**Output:**  
```
Development average salary: 1000
```

---

## Difference Between Local, Static, and Instance Variables

| Feature           | Local Variables                                      | Static Variables                                      | Instance Variables                                     |
|--------------------|-----------------------------------------------------|------------------------------------------------------|------------------------------------------------------|
| Definition         | Variables declared inside a method, constructor, 
|                    | or block. | Variables declared with the `static` keyword, shared among all instances of a class. | Variables declared in a class but outside any method, specific to each instance. |
| Scope              | Limited to the method, constructor, or block.       | Throughout the class, accessible via class or instance. | Limited to the instance of the class.               |
| Lifetime           | Exists only during the method/block execution.      | Exists for the lifetime of the class.                | Exists as long as the object exists.                |
| Default Value      | None; must be explicitly initialized.               | 0 (numeric), `false` (boolean), `null` (object references). | 0 (numeric), `false` (boolean), `null` (object references). |
| Memory Allocation  | Stack memory.                                       | Static memory of the heap.                           | Heap memory (as part of the object).                |
| Access Modifiers   | Cannot have access modifiers.                       | Can have access modifiers.                           | Can have access modifiers.                          |
| Usage              | Temporary storage/calculations in methods.          | Class-wide fields, constants, utility methods.       | Attributes unique to each object.                   |
| Example Declaration| `int localVar = 10;`                                | `static int staticVar = 10;`                         | `int instanceVar = 10;`                              |
| Access             | Directly within the method.                         | `ClassName.staticVar` or `objectName.staticVar`      | `objectName.instanceVar`                             |

---

## Frequently Asked Questions


<details>  
<summary>**Q1. What are Java variables?**</summary>  
**Ans:** Java variables are containers that hold data values. They are used to store and manipulate data within a Java program.  
```java
int number = 10;  // 'number' is a variable storing an integer value 10
String name = "John";  // 'name' is a variable storing a string
```  
</details>  

<details>  
<summary>**Q2. How do you declare a variable in Java?**</summary>  
**Ans:** Variables in Java are declared by specifying the data type followed by the variable name.  
```java
int age;  // Declaration
double price;  // Declaration of double type
```  
</details>  

<details>  
<summary>**Q3. What are the different types of variables in Java?**</summary>  
**Ans:** Java variables can be classified into three main types:  
1. **Local variables:** Declared within a method, constructor, or block.  
2. **Instance variables:** Associated with objects (instances) of a class.  
3. **Static variables:** Associated with the class rather than any object.  
```java
class Example {
    int instanceVar = 5;  // Instance variable
    static int staticVar = 10;  // Static variable
    
    void method() {
        int localVar = 20;  // Local variable
    }
}
```  
</details>  

<details>  
<summary>**Q4. What is the scope of a variable in Java?**</summary>  
**Ans:** In Java, the scope of a variable determines where programmers can access it in the code. Local variables confine their scope within the block of code where developers declare them, whereas instance and static variables offer broader scopes.  
```java
class ScopeExample {
    int x = 10;  // Instance variable (accessible across the class)
    
    void print() {
        int y = 5;  // Local variable (accessible only within this method)
        System.out.println(x + y);
    }
}
```  
</details>  

<details>  
<summary>**Q5. Can variable names start with a digit in Java?**</summary>  
**Ans:** No, variable names in Java cannot start with a digit. They must begin with a letter (A-Z, a-z), dollar sign (`$`), or underscore (`_`). After the first character, variable names can contain digits (0-9).  
```java
int _value = 30;  // Valid
int $price = 100;  // Valid
int 1number = 10;  // Invalid (Cannot start with digit)
```  
</details>  

<details>  
<summary>**Q6. Can Java variables be redeclared within the same scope?**</summary>  
**Ans:** No, Java does not allow redeclaration of variables within the same scope. Each variable name must be unique within its scope.  
```java
int x = 10;
// int x = 20;  // Compilation error (redeclaration in same scope)
```  
</details>  

<details>  
<summary>**Q7. What is the difference between instance and static variables?**</summary>  
**Ans:** Instance variables associate with objects (instances) of a class, creating separate copies for each instance. On the other hand, static variables associate with the class itself, maintaining only one shared copy among all instances of the class.  
```java
class Counter {
    int count = 0;  // Instance variable
    static int total = 0;  // Static variable
}
```  
</details>  

<details>  
<summary>**Q8. Can final variables be modified in Java?**</summary>  
**Ans:** In Java, you cannot modify final variables once you initialize them. They function as constants, and their values remain unchanged after initialization.  
```java
final int MAX = 100;
// MAX = 200;  // Compilation error (Cannot modify final variable)
```  
</details>  

<details>  
<summary>**Q9. What are the naming conventions for Java variables?**</summary>  
**Ans:** Variable names in Java should follow certain naming conventions for readability and consistency. It is recommended to use meaningful names that describe the purpose of the variable, with the first letter lowercase and subsequent words capitalized (camelCase).  
```java
int totalAmount = 500;  // camelCase naming convention
String userName = "Alice";
```  
</details>  

<details>  
<summary>**Q10. Do Java variables have default values?**</summary>  
**Ans:** Yes, Java variables have default values if not explicitly initialized. The default value depends on the variable’s data type.  
```java
class DefaultValues {
    int num;  // Default value is 0
    boolean flag;  // Default value is false
    String text;  // Default value is null
}
```  
</details>  

<details>  
<summary>**Q11. What is the difference between instance variable and class variable?**</summary>  
**Ans:** Instance variables hold unique data for each object, while class variables share a single value across all objects.  
```java
class Data {
    int instanceVar = 5;
    static int classVar = 10;
}
```  
</details>  

<details>  
<summary>**Q12. Where are instance variables stored in Java?**</summary>  
**Ans:** Instance variables in Java are stored in the heap memory, which is allocated to each individual object created from a class.  
```java
class Memory {
    int data = 20;
}
```  
</details>  

<details>  
<summary>**Q13. Can instance variables be declared as static?**</summary>  
**Ans:** No, instance variables cannot be declared as static. Static variables belong to the class, not to specific instances.  
```java
class Test {
    int instanceVar = 50;
    static int staticVar = 100;
}
```  
</details>  

<details>  
<summary>**Q14. When are instance variables created and destroyed?**</summary>  
**Ans:** Instance variables are created when an object is instantiated (in the constructor). They are destroyed when the object is eligible for garbage collection.  
```java
public class Employee {
    private static double salary;  // Static variable
    public static final String DEPARTMENT = "Development"; // Constant
    
    public static void main(String[] args) {
        salary = 1000;
        System.out.println(DEPARTMENT + " average salary: " + salary);
    }
}
```  
</details>  
```

---

This document provides a comprehensive understanding of Java variables, their types, and how to use them effectively.
