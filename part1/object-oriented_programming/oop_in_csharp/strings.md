# Strings

A string is an object of type String whose value is text. The text is stored as a sequential collection of read-only Char objects.


## Declaration and Initialization

```csharp
// Declare without initializing.
string message1;

// Initialize to null.
string message2 = null;

// Initialize as an empty string.
// Use the Empty constant instead of the literal "".
string message3 = System.String.Empty;

//Initialize with a regular string literal.
string oldPath = "c:\\Program Files\\Microsoft Visual Studio 8.0";

// Initialize with a verbatim string literal.
string newPath = @"c:\Program Files\Microsoft Visual Studio 9.0";

// Implicit type
var temp = "I'm still a strongly-typed System.String!";

// Use a const string to prevent 'message4' from
// being used to store another string value.
const string message4 = "You can't get rid of me!";

// Use the String constructor only when creating
// a string from a char*, char[], or sbyte*. See
// System.String documentation for details.
char[] letters = { 'A', 'B', 'C' };
string alphabet = new string(letters);
```
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

## Regular String Literals

Regular string literals are used to embed escape characters.

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

## Verbatim String Literals

Are used for convenience and better readability.

```csharp
string filePath = @"C:\Users\scoleridge\Documents\";
//Output: C:\Users\scoleridge\Documents\

string text = @"My pensive SARA ! thy soft cheek reclined
    Thus on mine arm, most soothing sweet it is
    To sit beside our Cot,...";
/* Output:
My pensive SARA ! thy soft cheek reclined
   Thus on mine arm, most soothing sweet it is
   To sit beside our Cot,... 
*/

string quote = @"Her name was ""Sara.""";
//Output: Her name was "Sara."
```


## String Escape Sequences

| Escape Sequence | Character Name |
| - | - |
| \' | Single quote |
| \" | Double quote |
| \\ | Backslash |
| \0 | Null |
| \a | Alert |
| \b | Backspace |
| \f | Form feed |
| \n | New line |
| \r | Carriage return |
| \t | Horizontal tab |
| \U | Unicode escape sequence for surrogate pairs |
| \u | Unicode escape sequence |
| \v | Vertical tab |
| \x | Unicode escape sequence similar to "\u" except with variable length |



