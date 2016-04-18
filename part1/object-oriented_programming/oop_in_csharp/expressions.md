# Expressions

> An expression is a sequence of one or more operands and zero or more operators that can be evaluated to a single value, object, method, or namespace.
> -- <cite>Microsoft's C# Programming Guide</cite>

## LINQ Query Expressions

Language-Integrated Query (LINQ) integrates query capabilities directly into the C# language. Although it is commonly used by Entity Framework, its usage applies to a variety of cases.

```csharp
static void Main()
{

    // Specify the data source.
    int[] scores = new int[] { 97, 92, 81, 60 };

    // Define the query expression.
    IEnumerable<int> scoreQuery =
        from score in scores
        where score > 80
        select score;

    // Execute the query.
    foreach (int i in scoreQuery)
    {
        Console.Write(i + " ");
    }
}
```


### Query Expression Overview

* Can be used to query and to transform data from any LINQ-enabled data source, such as SQL databases.
* Easy to master.
* The variables in a query expression are strongly typed, although they can inferred by the compiler.
* The query is not executed until iterated through a *foreach* loop
* Queries are translated to Standard Query Operator method calls.
* Query expressions are preferred over method calls, due to its readability.
* Some query operations, such as Count or Max, have no equivalent query expression claus and must be expressed as a method call.
* Query expressions can be compiled to expression trees or to delegates.

## Lambda Expressions

A lambda expression is an anonymous function used to create delegates or expression tree types. They are often used in Entity Framework.

**Delegate.**
```csharp
delegate int del(int i);
static void Main(string[] args)
{
    del myDelegate = x => x * x;
    int j = myDelegate(5); //j = 25
}
```

**Expression Tree.**
```csharp
static void Main(string[] args)
{
    Expression<del> myET = x => x * x;
}
```

**Entity Framework.**
```csharp
var adultUserList = db.Users.Where(u => u.Age >= 18).ToList();
```

### Expression Lambdas

Lambda expressions with an expression on the right side of the => operator.

```
(input parameters) => expression
```

```csharp
(int x, string s) => s.Length > x
```

### Statement Lambdas

Statement(s) is enclosed in braces

```
(input parameters) => {statement;}
```

```csharp
delegate void TestDelegate(string s);

TestDelegate myDel = n => { string s = n + " " + "World"; Console.WriteLine(s); };
myDel("Hello");
```

### Async Lambdas

Lambda expressions and statements that incorporate asynchronous processing