# Strings

A string is an object of type String whose value is text. The text is stored as a sequential collection of read-only Char objects.

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

## Format Strings

A format string is a string whose contents can be determined dynamically at runtime.

```csharp
static void Main()
{
    int i = 2;
    int j = 4;

    // A simple format string with no alignment formatting.
    string s = System.String.Format("{0} times {1} = {2}", i, j, (i * j));
    System.Console.WriteLine(s);

}
```

## Substrings

A substring is any sequence of characters that is contained in a string. Substrings can be separated as needed.

```csharp
string s3 = "Visual C# Express";
System.Console.WriteLine(s3.Substring(7, 2));
// Output: "C#"
```


## Accessing Individual Characters

Strings can be accessed as arrays.

```csharp
string s5 = "Printing backwards";

for (int i = 0; i < s5.Length; i++)
{
    System.Console.Write(s5[s5.Length - i - 1]);
}
// Output: "sdrawkcab gnitnirP"
```

## Null Strings and Empty Strings

A null string  does not refer to an instance of a System.String object. Any attempt to call a method on a null string causes a *NullReferenceException*.

An empty string is an instance of System.String object that contains zero characters.

```csharp
static void Main()
{
    string str = "hello";
    string nullStr = null;
    string emptyStr = String.Empty;

    if (!String.IsNullOrEmpty(str))
    {

        System.Console.WriteLine("str is not null nor empty");

    }

    if (nullStr == null)
    {
        System.Console.WriteLine("nullStr is null");
    }

    if (String.IsNullOrEmpty(emptyStr))
    {
        System.Console.WriteLine("emptyString is null or empty");
    }

}
```

## Using StringBuilder for Fast String Creation

Although string operations are optimized in C#, some scenarios may require even better perfomance. StringBuilder is advised in those cases.

```csharp
static void Main()
{
    System.Text.StringBuilder sb = new System.Text.StringBuilder();

    // Create a string composed of numbers 0 - 9
    for (int i = 0; i < 10; i++)
    {
        sb.Append(i.ToString());
    }
    System.Console.WriteLine(sb);  // displays 0123456789

    // Copy one character of the string (not possible with a System.String)
    sb[0] = sb[9];

    System.Console.WriteLine(sb);  // displays 9123456789
}
```
