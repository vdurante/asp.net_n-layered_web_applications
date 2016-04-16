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

* **Abstract Factory.** Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
* **Builder.** Separates the construction of a complex object from its representation so that the same construction process can create different representations. 
* **Factory Method.** Defines an interface for creating an object, but let subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.
* **Prototype.** Specifies the kinds of objects to create using a prototypical instance, and creates new objects by copying this prototype.
* **Singleton.** Ensures a class only has one instance, and provides a global point of access to it.

### Structural Design Patterns

* **Adapter.** Converts the interface of a class into another interface clients expect. Adapter lets classes work together that couldn't otherwise because of incompatible interfaces. 
* **Bridge.** Decouples an abstraction from its implementation so that the two can vary independently.
* **Composite.** Composes objects into tree structures to represent part-whole hierarchies. Composite lets clients treat individual objects and compositions of objects uniformly.
* **Decorator.** Attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.
* **Facade.** Provides an unified interface to a set of interfaces in a subsystem. Facade defines a higher-level interface that makes the subsystem easier to use.
* **Flyweight.** Uses sharing to support large numbers of fine-grained objects efficiently.
* **Proxy.** Provides a surrogate or placeholder for another object to control access to it.

### Behavioral Design Patterns

* **Chain of Responsibility.** Avoid coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. Chain the receiving objects and pass the request along the chain until an object handles it. 
* **Command.** Encapsulate a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations. 
* **Interpreter.** Given a language, define a represention for its grammar along with an interpreter that uses the representation to interpret sentences in the language.
* **Iterator.** Provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
* **Mediator.** Define an object that encapsulates how a set of objects interact. Mediator promotes loose coupling by keeping objects from referring to each other explicitly, and it lets you vary their interaction independently.
* **Memento.** Without violating encapsulation, capture and externalize an object's internal state so that the object can be restored to this state later. 
* **Observer.** Define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
* **State.** Allow an object to alter its behavior when its internal state changes. The object will appear to change its class.
* **Strategy.** Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from clients that use it.
* **Template Method.** Define the skeleton of an algorithm in an operation, deferring some steps to subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm's structure.
* **Visitor.** Represent an operation to be performed on the elements of an object structure. Visitor lets you define a new operation without changing the classes of the elements on which it operates.


