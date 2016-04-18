# Types

C# is a strongly-typed language. This means that every variable and constant has a type, as does every expression (i.e. method, or function) that evaluates to a type. Every method specifies a type for each input argument, as well as for the return value.
  
There is also a *var* type, which declares a implicit type. It is strongly-typed as well, but the compiler determines the type.

## Nullable Types

Some types are nullable by default. Some others need a special declaration, using the *?* operator.

**String.**  Nullable by default.

```csharp
// allowed
string MyString = null;
```

**Bool.** Not-nullable by default.

```csharp
// ERROR: non-nullable
bool MyBool = null;

// allowed
bool? MyNullableBool = null;
```

## Built-In Types

The following table shows the built-in C# types:

| C# Type | Description | Range | Size
| -- | -- |
| bool | Boolean (*true* or *false*) |
| byte | integral type that stores from 0 to 255 range |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |



