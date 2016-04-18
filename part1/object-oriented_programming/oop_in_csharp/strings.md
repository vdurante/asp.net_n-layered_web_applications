# Strings

A string is an object of type String whose value is text. The text is stored as a sequential collection of read-only Char objects.

## Immutability

Strings are *immutable*: they cannot be changed after they have been created. String methods and C# operations that appear to modify a string actually return the results in a new string object.

```csharp
string s1 = "A string is more ";
string s2 = "than the sum of its chars.";

// Concatenate s1 and s2. This actually creates a new
// string object and stores it in s1, releasing the
// reference to the original object.
s1 += s2;

System.Console.WriteLine(s1);
// Output: A string is more than the sum of its chars.
```

## Regular and Verbatim String Literals

```csharp
string columns = "Column 1\tColumn 2\tColumn 3";
//Output: Column 1        Column 2        Column 3

string rows = "Row 1\r\nRow 2\r\nRow 3";
/* Output:
  Row 1
  Row 2
  Row 3
*/

string title = "\"The \u00C6olean Harp\", by Samuel Taylor Coleridge";
//Output: "The Æolean Harp", by Samuel Taylor Coleridge
```