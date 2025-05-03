---
title: "Oops Concepts"
date: 2019-03-06T03:17:00+05:30
lastmod: 2019-03-06T03:17:00+05:30
tags:
  - java
categories:
  - java
url: /oops-concepts.html
---

### Termiologies

1. Class
2. Object
3. Inheritence
4. Polymorphism
5. Abstraction
6. Encapsulation


**What is a class?**  
A class is a collection of methods and variables. It defines the data and the behaviour of a type. It is like a blueprint or template from which objects are created. A class is declared once. A class doesn't allocated memory when it is created.

**What is an object?**  
An object is an instance of a class. An object is created many times per requirement. Object allocates memory when it is created. An object consists of :

* State : It is represented by attributes of an object. It also reflects the properties of an object.
* Behavior : It is represented by methods of an object. It also reflects the response of an object with other objects.
* Identity : It gives a unique name to an object and enables one object to interact with other objects.

**What is inheritance?**  
Inheritance is a feature which allows code reusability. In inheritance one class includes properties of another class. It provides code reusability. It is used to achieve runtime polymorphism.

**What is polymorphism?**  
In polymorphosm a task is performed in different ways. In Java we use overloading and overriding to achieve polymorphism

**What is abstraction?**  
Abstraction means hiding internal details and showing only the required functionality to the outside world. In Java we use abstact class and interface to achieve abstaction.

**What is encapsulation?**  
In encapsulation we bind code and data together in a single unit. In java we use classes to achieve encapsulation

**What are the advantages of OOPs?**  
* It makes development and maintenance easier.
* Provides data hiding

**What are anonymous objects?**  
Anonymous objects are the objects that are instantiated but are not stored in a reference variable.

* They are used for immediate method calling.
* They will be destroyed after method calling.
* They are widely used in different libraries. For example, in AWT libraries, they are used to perform some action on capturing an event(eg a key press).

**What are access modifiers (specifiers)?**  
Access modifiers are keywords that are used for data hiding in object oriented programming. In Java  - public, private, protected and default

**What are abstract class?**  
Abstract classes are created by placing abstract keyword before class name. Abstract classes are classes that contains both abstract and non abstact methods.Abstract classes/methods are generally used when a class provides some high level functionality but leaves out certain details to be implemented by derived classes. Making the class/method abstract ensures that it cannot be used on its own, but must be specialized to define the details that have been left out of the high level implementation.

