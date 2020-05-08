# Collections

##  Non-generic collections

![](../../.gitbook/assets/image%20%2819%29.png)

| Non-generic Collections | Usage |
| :--- | :--- |
| ArrayList | ArrayList stores objects of any type like an array. However, there is no need to specify the size of the ArrayList like with an array as it grows automatically. |
| SortedList | SortedList stores key and value pairs. It automatically arranges elements in ascending order of key by default. C\# includes both, generic and non-generic SortedList collection. |
| Stack | Stack stores the values in LIFO style \(Last In First Out\). It provides a Push\(\) method to add a value and Pop\(\) & Peek\(\) methods to retrieve values. C\# includes both, generic and non-generic Stack. |
| Queue | Queue stores the values in FIFO style \(First In First Out\). It keeps the order in which the values were added. It provides an Enqueue\(\) method to add values and a Dequeue\(\) method to retrieve values from the collection. C\# includes generic and non-generic Queue. |
| Hashtable | Hashtable stores key and value pairs. It retrieves the values by comparing the hash value of the keys. |
| BitArray | BitArray manages a compact array of bit values, which are represented as Booleans, where true indicates that the bit is on \(1\) and false indicates the bit is off \(0\). |

## Generic collections

The limitation of these collections is that while retrieving items, you need to cast into the appropriate data type, otherwise the program will throw a runtime exception. It also affects on performance, because of boxing and unboxing.

To overcome this problem, C\# includes generic collection classes in the **System.Collections.Generic** namespace.

The following are widely used generic collections:

| Generic Collections | Description |
| :--- | :--- |
| [List&lt;T&gt;](https://www.tutorialsteacher.com/csharp/csharp-list) | Generic List&lt;T&gt; contains elements of specified type. It grows automatically as you add elements in it. |
| [Dictionary&lt;TKey,TValue&gt;](https://www.tutorialsteacher.com/csharp/csharp-dictionary) | Dictionary&lt;TKey,TValue&gt; contains key-value pairs. |
| [SortedList&lt;TKey,TValue&gt;](https://www.tutorialsteacher.com/csharp/csharp-generic-sortedlist) | SortedList stores key and value pairs. It automatically adds the elements in ascending order of key by default. |
| Hashset&lt;T&gt; | Hashset&lt;T&gt; contains non-duplicate elements. It eliminates duplicate elements. |
| Queue&lt;T&gt; | Queue&lt;T&gt; stores the values in FIFO style \(First In First Out\). It keeps the order in which the values were added. It provides an Enqueue\(\) method to add values and a Dequeue\(\) method to retrieve values from the collection. |
| Stack&lt;T&gt; | Stack&lt;T&gt; stores the values as LIFO \(Last In First Out\). It provides a Push\(\) method to add a value and Pop\(\) & Peek\(\) methods to retrieve values. |

