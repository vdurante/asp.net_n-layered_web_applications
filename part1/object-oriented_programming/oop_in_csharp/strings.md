# Strings

A string is an object of type String whose value is text. The text is stored as a sequential collection of read-only Char objects.

## Immutability

Strings are *immutable*: they cannot be changed after they have been created. String methods and C# operations that appear to modify a string actually return the results in a new string object.

```csharp
string s1 = "Hello ";
string s2 = s1;
s1 += "World";

System.Console.WriteLine(s2);
//Output: Hello
```

## Regular and Verbatim String Literals

```csharp
```