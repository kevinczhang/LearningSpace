---
description: >-
  Array is the data structure that stores fixed number of literal values of the
  same data type.
---

# Array

Array Declaration & Initialization

```csharp
int[] nums = { 10, 15, 16, 8, 6 };

foreach(var item in nums)
    Console.WriteLine(item);   

string[] names = { "Steve", "Bill", "Ram", "Mohan" };

foreach(var name in names)
    Console.WriteLine(name);  
```

### Array Class

```csharp
int[] nums = new int[5]{ 10, 15, 16, 8, 6 };

Array.Sort(nums); // sorts array in ascending order
Array.Reverse(nums); // sorts array in descending order
ArrayForEach(nums, n => Console.WriteLine(n)); // iterates array using foreach loop
Array.BinarySearch(nums, 5);// search element using binary search algorithm
```

## Multidimensional Arrays

C\# supports multidimensional arrays up to 32 dimensions.

```csharp
int[,] arr2d; // two-dimensional array
int[, ,] arr3d; // three-dimensional array
int[, , ,] arr4d ; // four-dimensional array
int[, , , ,] arr5d; // five-dimensional array
```

![](../../.gitbook/assets/image%20%2822%29.png)

## Jagged Arrays

A jagged array is an array of array. Jagged arrays store arrays instead of literal values.

```csharp
int[][] jArray = new int[2][]{
                new int[3]{1, 2, 3},

                new int[4]{4, 5, 6, 7}
            };

for(int i=0; i<jArray.Length; i++)
{
	for(int j=0; j < (jArray[i]).Length; j++)
		Console.WriteLine(jArray[i][j]);
}
```



