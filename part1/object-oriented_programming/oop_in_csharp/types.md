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

| C# Type | Description | Range | Precision | Size
| -- | -- | -- | -- | -- | -- |
| bool | Boolean | (*true* or *false*) | - | |
| byte | Integral | 0 to 255 | - | Unsigned 8-bit integer |
| sbyte | Integral | -128 to 127 | - | Signed 8-bit integer |
| char | Unicode character | U+0000 to U+FFFF | - | 16-bit numeric (ordinal) value |
| decimal | High precision, small range floating-point (great for financial and monetary calculations) | $$-7.9 * 10^{28}\ \text{to}\ 7.9 * 10^{28}$$| 28-29 significant digits | 128-bit |
| double | Simple floating-point | $$\pm5.0 * 10^{-324}\ \text{to}\ \pm1.7 * 10^{308}$$ | 15-16 digitis | 64-bit |
| float | Simple floating-point | $$-3.4*10^{38}\ \text{to}\ +3.4*10^{38}$$ | 7 digits | 32-bit |
| int | Integral | -2,147,483,648 to 2,147,483,647 | - | Signed 32-bit
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |



