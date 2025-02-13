## Java Technical Interview Questions
---
### Core Java Concepts 
1. What is the difference between JDK and JRE? 
2. Why is Java a platform independent language? 
3. What is the difference between an abstract class and an interface? 
4. What is the difference between final, finally, and finalize? 
5. What is the difference between stack and heap memory? 
6. What is the difference between method overloading and method overriding? 
7. What is the difference between an abstract class and an interface? 
8. What is the difference between a private and a protected modifier? 
9. What is constructor overloading in Java? 
10. What is the use of super keyword in Java? 
11. What is the difference between static methods, static variables, and static classes in Java? 
12. What exactly is System.out.println in Java? 
13. What part of memory - Stack or Heap - is cleaned in the garbage collection process?

__Ans.1__
JDK stands for Java Development Kit, which is a software development environment for building Java applications. JRE stands for Java Runtime Environment, which is required to run Java programs. 

__Ans.2__ 
By relying on a virtual machine, Java achieves platform independence. In practice, this means that both the Java programming language and its associated APIs are first compiled into bytecodes that can run on multiple platforms. Then, the virtual machine handles any variations in how these bytecodes are executed across different platforms. 

__Ans.3__ 
An abstract class is a class that cannot be instantiated and can only be inherited. An interface is a blueprint of a class that contains only abstract methods and constants. 

__Ans.4__
Final is used to make a variable or method constant and cannot be changed later. finally is used in try-catch blocks to execute a block of code regardless of whether an exception is thrown or not. finalise is a method that is called by the garbage collector when an object is no longer in use. 

**Ans.5** 
Stack memory is used for storing local variables and function call, while heap memory is used for storing objects and their instance variables. 

**Ans.6** 
Method overloading is creating multiple methods in a class with the same name but different parameters, while method overriding is creating a method in a subclass with the same name and parameters as a method in its superclass. 

**Ans.7** 
An abstract class can have both abstract and concrete methods, while an interface can only have abstract methods. A class can extend only one abstract class, but it can implement multiple interfaces. 

**Ans.8** 
A private modifier makes a member accessible only within the same class, while a protected modifier makes a member accessible within the same class and its subclasses. 

**Ans.9** 
Constructor overloading is a concept in object oriented programming where a class can have multiple constructors with different parameter lists. Each constructor provides a different way to initialise objects of that class. 

**Ans.10** 
The super keyword is used to access data members of the parent class when the data members names of the parent class and its child subclasses are the same, to call the default and parameterized constructor of the parent class inside the child subclass and to access parent class methods when the child subclasses have overridden them. 

**Ans.11** 
Static Methods and Static variables are those methods and variables that belong to the class of the java program, not to the object of the class. They are allocated memory when the class is loaded and can directly be called with the help of the class names. A class in the java program cannot be static except if it is the inner class. If it is an inner static class, then it exactly works like other static members of the class. 

**Ans.12** 
System.out.println() is a method to print a message on the console. System - It is a class present in java.lang package. Out is the static variable of type PrintStream class present in the System class. println() is the method present in the PrintStream class. 

Ans.13 Garbage Collection is done on heap memory to free the memory used by objects that don't have any reference. Any object created in the heap space has global access and can be referenced from anywhere in the application.

### Object-Oriented Programming
1. What are the Object Oriented Features supported by Java? 
2. What are the different access specifiers used in Java? 
3. What is the difference between composition and inheritance? 
4. What is the purpose of an abstract class? 
5. What are the differences between constructor and method of a class in Java? 
6. What is the diamond problem in Java and how is it solved? 
7. What is the difference between local and instance variables in Java? 
8. What is a Marker interface in Java?