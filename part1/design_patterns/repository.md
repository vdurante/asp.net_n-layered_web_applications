# Repository

The Repository Design Pattern is widely used in applications that work with any kind of persistence (e.g. a database). It is a part of Domain-Driven Design

It intends to create an abstraction for manipulating data present in the persistence of the application. It implements a collection of basic and commonly used Create, Read, Update and Delete (CRUD) operations. It also guarantees consistency across the application's access to persistence.

## Problem

* **High potential of programming errors.** Code is duplicate across the source code, breaking the Don't Repeat Yourself (DRY) principle.
* **Tight coupling.** Classes that access database become tightly coupled to database operations.
* **Lack of abstraction.** Without a repository, CRUD operations are not generic and very specific towards each table in the database.
* **Low testability.** CRUD operations are hard to be tested in isolation. Business logic is also hard to be tested in isolation due to its dependency.
* **Lack of consistency.** A change in the database schema implies a change in all classes that access that database to execute CRUD operations.
* **Non-centralized data-related policies.** Caching data becomes hard due to the lack of isolation.

## Solution

Using a repository to separate the database CRUD operations and map the results of these operations to a object (called Model).

## Consequence