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

Using a repository to separate the database CRUD operations and map the results of these operations to an object (called Model in this case).

![](./res/img/figure3.png)

The image above represents the general idea of a repository:

Whenever a Business Logic needs to perform a query, it calls a method from the Repository. This method builds a Query Object (such as a SQL statement) and invokes the Data Source to execute the desired operation. Once the operation is executed, a response is sent back to the Repository by the Data Source. The Data Mapper translates this response into a Model and sends the response back to the Business Logic.

If the Business Logic requires a user to be fetched:

1. Code calls the Repository's method FindById with the id of the desired user (desired_id) as argument.
2. Repository builds a Query Object, such as *SELECT * FROM Users WHERE Id=:desired_id*, and sends it to the Data Source, in this case a Database.
3. If found, Data Source fetches the user and sends a response containing the User's info.
4. Data Mapper receives this data and automatically maps it into a Model.
5. Repository sends the Model back to the method that required the user.

If the Business Logic requires this user to be deleted:

1. Code call the Repository's method Delete with the user Model as argument.
2. Data Mapper maps the user Model into a Query Object.
3. Query is executed in Data Source, response is sent to repository, then to the method that required the user to be deleted.

The implementation above is possible through the use of a Repository interface. The interface describes the structure of the repository and for each table in the database, a Repository and its methods are implemented.

There is also a more generic approach, using a Type of the database table. A example is present in the Examples section bellow.

## Consequence

* **Separation of Concerns.** Business logic separated from data access logic.
* **Least Knowledge Principle.** Business logic is unaware regarding how data is accessed.
* **Single Responsibility Principle.** Business logic is not responsible for data access.
* **Operations on data are centralized.** Repositories centralize all CRUD operations, guaranteeing maintainability, readability and consistency.
* **Increased testability.** Isolation promotes better unit testing.
* **Caching strategy.** Data can be easily cached and managed.
* **Business Entities are strongly typed.** Manipulating data from database is made through strongly-typed objects and repository methods. Errors are identified during compiling time, unlike using pure SQL that would result in errors at run time, during execution of the query.
* **Complex behavior.** Complex relationships and calculated fields can be enforced inside a repository, such as Polymorphism, that is not supported by databases, but can easily be implemented in a Repository, being transparent to the business logic.


## Examples


### Example 1: A Repository Interface

Suppose a User Manager which contains core business logic regarding user management.

#### The Bad Way

The bad way would run SQL straight from the User Manager Class.

{%ace edit=false, lang='csharp'%}
public class UserManager
{
    private ApplicationDbContext _dbContext;

    public UserManager()
    {
        this._dbContext = new ApplicationDbContext();
    }

    public void CreateUser(string name, int age)
    {
        // some business logic
        if (age < 18)
        {
            throw new UserTooYoungException();
        }
        
        // business logic mixed with data access logic
        
        var query = String.Format("INSERT INTO Users (Name, Age) VALUES ({0}, {1});", name, age);
        this._dbContext.SqlQuery(query);
    }
}
{%endace%}

**Usage**
{%ace edit=false, lang='csharp'%}
// usage

UserManager userManager = new UserManager();

userManager.CreateUser("Jonathan", 22);
{%endace%}

#### The Good Way

The good way would be creating a User Repository and use it as needed. The Business Logic and Data Access Logic become separate, solving the problems cited above.

{%ace edit=false, lang='csharp'%}
public class User
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

public class UserRepository
{

    private ApplicationDbContext _dbContext;

    public UserRepository()
    {
        this._dbContext = new ApplicationDbContext();
    }

    // User Model being passed as argument
    // Query Object can be built from the user data
    public void Create(User user)
    {
        // Data Mapping from User Model to build Query Object
        var query = String.Format("INSERT INTO Users (Name, Age) VALUES ({0}, {1});", user.Name, user.Age);

        this._dbContext.SqlQuery(query);
    }

    public User Read(int id)
    {
        // read logic

        // Data Mapper would map the response into a User object
    }

    public void Update(User user)
    {
        // update logic
    }

    public void Delete(User user)
    {
        // delete logic   
    }
}

public class UserManager
{
    private UserRepository _userRepository;

    public UserManager()
    {
        this._userRepository = new UserRepository();
    }

    public void CreateUser(string name, int age)
    {
        // some business logic
        if (age < 18)
        {
            throw new UserTooYoungException();
        }

        // User object (Model) is created using passed arguments
        User user = new User { Name = name, Age = age };

        this._userRepository.Create(user);
    }
}


// usage

UserManager userManager = new UserManager();

userManager.CreateUser("Jonathan", 22);
{%endace%}

#### The Great Way