# What Is Object-Oriented Programming?

Opposed to classic procedural programming, which describes a program as a composition of actions organized in a logical flow, object-oriented programming organizes code around classes and objects. An object is the instantiation of a class: self-contained components of an application that have private functionality as well as public functionality that can be exposed to the user.

## Important Concepts

* **Class.** A template or set of instructions (methods) and data (attributes) to build a specific object.
* **Methods.** The capabilities (or functions) of a class.
* **Attribute.** The properties of a class, such as variables.
* **Object.** An instance of a class. The concretization of the template of a class into a concrete object.
* **Encapsulation.** A group of methods and attributes that are encapsulated, meaning that are treated as a single unit or object.
* **Inheritance.** The ability to create new classes based on existing ones, inheriting methods, attributes, strucutre.
* **Polymorphism.** Multiple classes that implement the same properties and methods, but in different ways. Due to this fact, they can be used interchangeably.


## What are Software Design Principles?

Software Design principles represent a set of guidelines to help a developer avoid having a bad design. There are 3 important characteristics of a bad design:

* **Rigidity.** A code is hard to change because every change affects too many other parts of the system.
* **Fragility.** When making a change, unexpected parts of the system break.
* **Immobility.** The is hard to reuse in another application because it is heavily tangled (or couple) to the current application.

## The SOLID Design

Robert C. Martin proposed the "first five principles" of object-oriented design. Then, Michael Feathers introduced the SOLID acronym to describe them:

* **Single Responsibility Principle.** A class should only have a single responsibility.
* **Open/Closed Principle.** Classes, modules, functions, etc. should be open for extension, but closed for modification.
* **Liskov Substitution Principle.** If class D is derived from base class B, class D must be completely substitutable for the base class B. 
* **Interface Segregation Principle.** No client should be forced to depend on interfaces that it does not use. In other words, segregating one big general-purpose interface in multiple specific ones is peferable.
* **Dependency Inversion Principle.** One should depend upon abstractions and not upon concretions. High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.

