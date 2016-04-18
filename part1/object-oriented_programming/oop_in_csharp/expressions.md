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