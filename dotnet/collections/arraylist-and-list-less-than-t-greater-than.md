# ArrayList and List&lt;T&gt;

## ArrayList

ArrayList is a non-generic type of collection in C\#. It can contain elements of any data types.

```csharp
ArrayList myArryList = new ArrayList();// Recommended
// or - with some limitations
IList myArryList = new ArrayList();
// or - with some limitations
ICollection myArryList = new ArrayList();
// or - with some limitations
IEnumerable myArryList = new ArrayList();
```

### Important Properties and Methods of ArrayList

| Properties | Description |
| :--- | :--- |
| Capacity | Gets or sets the number of elements that the ArrayList can contain. |
| Count | Gets the number of elements actually contained in the ArrayList. |
| IsFixedSize | Gets a value indicating whether the ArrayList has a fixed size. |
| IsReadOnly | Gets a value indicating whether the ArrayList is read-only. |
| Item | Gets or sets the element at the specified index. |

| Methods | Description |
| :--- | :--- |
| [Add\(\)/AddRange\(\)](https://www.tutorialsteacher.com/csharp/csharp-arraylist#add) | Add\(\) method adds single elements at the end of ArrayList. AddRange\(\) method adds all the elements from the specified collection into ArrayList. |
| [Insert\(\)/InsertRange\(\)](https://www.tutorialsteacher.com/csharp/csharp-arraylist#insert) | Insert\(\) method insert a single elements at the specified index in ArrayList. InsertRange\(\) method insert all the elements of the specified collection starting from specified index in ArrayList. |
| [Remove\(\)/RemoveRange\(\)](https://www.tutorialsteacher.com/csharp/csharp-arraylist#remove) | Remove\(\) method removes the specified element from the ArrayList. RemoveRange\(\) method removes a range of elements from the ArrayList. |
| [RemoveAt\(\)](https://www.tutorialsteacher.com/csharp/csharp-arraylist#removeat) | Removes the element at the specified index from the ArrayList. |
| [Sort\(\)](https://www.tutorialsteacher.com/csharp/csharp-arraylist#sort) | Sorts entire elements of the ArrayList. |
| [Reverse\(\)](https://www.tutorialsteacher.com/csharp/csharp-arraylist#sort) | Reverses the order of the elements in the entire ArrayList. |
| [Contains](https://www.tutorialsteacher.com/csharp/csharp-arraylist#contains) | Checks whether specified element exists in the ArrayList or not. Returns true if exists otherwise false. |
| Clear | Removes all the elements in ArrayList. |
| CopyTo | Copies all the elements or range of elements to compitible Array. |
| GetRange | Returns specified number of elements from specified index from ArrayList. |
| IndexOf | Search specified element and returns zero based index if found. Returns -1 if element not found. |
| ToArray | Returns compitible array from an ArrayList. |

```csharp
ArrayList myArryList = new ArrayList();
myArryList.Add(1);
myArryList.Add("Two");
myArryList.Add(3);
myArryList.Add(4.5f);

//Access individual item using indexer
int firstElement = (int) myArryList[0]; //returns 1
string secondElement = (string) myArryList[1]; //returns "Two"
int thirdElement = (int) myArryList[2]; //returns 3
float fourthElement = (float) myArryList[3]; //returns 4.5

//use var keyword
var firstElement = myArryList[0]; //returns 1
```

## List&lt;T&gt;

The List collection is the same as an ArrayList except that List is a generic collection whereas ArrayList is a non-generic collection.

```csharp
List<int> intList = new List<int>();

//Or

IList<int> intList = new List<int>();
```

### Important Properties and Methods:

| Property | Usage |
| :--- | :--- |
| Items | Gets or sets the element at the specified index |
| Count | Returns the total number of elements exists in the List&lt;T&gt; |

| Method | Usage |
| :--- | :--- |
| Add | Adds an element at the end of a List&lt;T&gt;. |
| AddRange | Adds elements of the specified collection at the end of a List&lt;T&gt;. |
| BinarySearch | Search the element and returns an index of the element. |
| Clear | Removes all the elements from a List&lt;T&gt;. |
| Contains | Checks whether the speciied element exists or not in a List&lt;T&gt;. |
| Find | Finds the first element based on the specified predicate function. |
| Foreach | Iterates through a List&lt;T&gt;. |
| Insert | Inserts an element at the specified index in a List&lt;T&gt;. |
| InsertRange | Inserts elements of another collection at the specified index. |
| Remove | Removes the first occurence of the specified element. |
| RemoveAt | Removes the element at the specified index. |
| RemoveRange | Removes all the elements that match with the supplied predicate function. |
| Sort | Sorts all the elements. |
| TrimExcess | Sets the capacity to the actual number of elements. |
| TrueForAll | Determines whether every element in theÂ List&lt;T&gt; matches the conditions defined by the specified predicate. |

