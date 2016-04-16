# What Is A Design Pattern?


> "Each pattern describes a problem which occurs over
and over again in our environment, and then describes the core of the solution
to that problem, in such a way that you can use this solution a million times
over, without ever doing it the same way twice"
>  -- <cite>Christopher Alexander</cite>

A design pattern is a description or template for how to solve a problem that can be used in many different situations. It is a general repeatable solution to a commonly occurring problem in software design.

The Gang of Four describes four essential elements:

* **Pattern name.** A word or two used to describe a design problem, its solutions and consequences.
* **Problem.** When to apply the pattern. Explains the problem and its context.
* **Solution.** The elements that make up the design, their relationships, responsibilities, and collaborations.
* **Consequences.** Results and trade-offs of applying the pattern.

## The Gang Of Four's patterns.

The Gang of Four describes 23 classic design patterns, divided into 3 categories: creational, structural, and behavioral.

### Creational Design Patterns

The creational design patterns are all about class instantiation, being divided into class-creation patterns and object-creation patterns.

* **Abstract Factory.** Provide an interface for creating families of related or dependent objects without specifying their concrete classes.
* **Builder.** Separate the construction of a complex object from its representation so that the same construction process can create different representations. 
* **Factory Method.** Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.
* **Prototype.**
* **Singleton.**

### Structural Design Patterns

* **Adapter.** Convert the interface of a class into another interface clients expect. Adapter lets classes work together that couldn't otherwise because of incompatible interfaces. 
* **Bridge.** Decouple an abstraction from its implementation so that the two can vary independently.
* **Composite.** Compose objects into tree structures to represent part-whole hierarchies. Composite lets clients treat individual objects and compositions of objects uniformly.
* **Decorator.** Attach additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.
* **Facade.** Provide a unified interface to a set of interfaces in a subsystem. Facade defines a higher-level interface that makes the subsystem easier to use.
* **Flyweight.**
* **Proxy.**

### Behavioral Design Patterns

* **Chain of Responsibility.** Avoid coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. Chain the receiving objects and pass the request along the chain until an object handles it. 
* **Command.** Encapsulate a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations. 
* **Interpreter.**
* **Iterator.**
* **Mediator.**
* **Memento.**
* **Observer.**
* **State.**
* **Strategy.**
* **Template Method.**
* **Visitor.**


