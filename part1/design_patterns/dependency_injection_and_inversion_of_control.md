# Dependency Injection And Inversion Of Control

> Inversion of Control, or IoC, is an abstract principle describing an aspect of some software architecture designs in which the flow of control of a system is inverted in comparison to procedural programming.

To understand the explanation above, it is important to address what is procedural programming.

In procedural programming, a chunk of code that uses, or consumes, another chunk of code is in control of the process. This chunk of code knows exactly what piece of code, what method in what class, it uses.

![](./res/img/figure1.png)

The image above illustrates the procedural programming well. Class A, the consumer, needs the consumed classes (Services Y and Z), to run. Therefore, Class A instantiates both Y and Z classes before using those services.

The approach presented above induces a tight coupling and high dependency of Class A in relation to Classes Y and Z.
 
## Problems

* **Thigh Coupling. ** When a group of classes is highly dependent on one another.
* **Break of the Single Responsibility principle.** Class A assumes too many responsibilities.
* **Break of the Principle of Least Knowledge.** Class A knows too much about Classes Y and Z.
* **Lack of abstraction.** Class A uses concrete Classes Y and Z.
* **Low testability.** The high dependency between these classes decreases testability. It becomes hard to test Class A in isolation from Class Y or Z.

The procedural approach induces some unwanted constraints:

* If it becomes necessary to replace or modify Class A's dependencies (Y and Z), a change in the source code of A is mandatory.
* Class A is difficult to test in isolation. It depends on Y and Z success as well.
* The concrete implementations of the 
* All classes contain repetitive code for creating, locating, and managing their dependencies.

A clear example in a practical problem would be:

Imagine a developer is implementing Class A, and it accesses a database, represented by Class DB. For testing purposes, the developer is not interested in setting up a database in the testing environment. The smart developer implements a mock database instead, called Class MockDB.

The problem arises when the high dependency of Class A on Class DB becomes clear. To test Class A with a mock database, the developer must change the source code of A to instantiate Class MockDB every time this person tests Class A.

This clearly becomes impractical over time and complexity.

## Solution

The most common solutions presented are Dependency Injection and Service Locator. The former seems more interesting, therefore the latter won't be explained in details.

The Dependency Injection pattern dictates that whenever a class has a dependency, it should be passed (or injected) as a parameter into it. It is a matter of not instantiating the dependencies explicitly. Just declare the dependencies and let whoever is using this class to pass the dependency.

On the example above, the database object dependency would be passed inside Class A as a parameter. Therefore, Class A becomes blind towards the implementation of the database class. Whether it is a mock database or a real database is not important, as long as Class A is able to access its methods and attributes.

But how is Class A able to use an object if it is blind towards the object's class? The answer is simple: interfaces. As far as the real database class and the mock database class implements the same interface, Class A will be able to access its methods and attributes.



## Consequence




## Examples

### Example 1: 