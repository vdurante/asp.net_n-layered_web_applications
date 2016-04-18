# Arrays

Arrays store multiple variables of the same type. They can be multidimensional.

## Overview

An array has the following properties:

* Single-Dimensional, Multidimensional, or Jagged.
* Number of dimensions and length are established when the array instance is created. These values can't be changed during the lifetime of the instance.
* Default values of numeric array elements are set to zero. Reference elements (such as strings) are set to null.

## Example

```csharp
class TestArraysClass
{
    static void Main()
    {
        // Declare a single-dimensional array 
        int[] array1 = new int[5];

        // Declare and set array element values
        int[] array2 = new int[] { 1, 3, 5, 7, 9 };

        // Alternative syntax
        int[] array3 = { 1, 2, 3, 4, 5, 6 };

        // Declare a two dimensional array
        int[,] multiDimensionalArray1 = new int[2, 3];

        // Declare and set array element values
        int[,] multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

        // Declare a jagged array
        int[][] jaggedArray = new int[6][];

        // Set the values of the first array in the jagged array structure
        jaggedArray[0] = new int[4] { 1, 2, 3, 4 };
    }
}
```