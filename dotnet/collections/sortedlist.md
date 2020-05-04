---
description: >-
  The SortedList collection stores key-value pairs in the ascending order of key
  by default.
---

# SortedList

SortedList class implements IDictionary & ICollection interfaces, so elements can be accessed both by key and index.

### Important Properties and Methods of SortedList

| Property | Description |
| :--- | :--- |
| Capacity | Gets or sets the number of elements that the SortedList instance can store. |
| Count | Gets the number of elements actually contained in the SortedList. |
| IsFixedSize | Gets a value indicating whether the SortedList has a fixed size. |
| IsReadOnly | Gets a value indicating whether the SortedList is read-only. |
| Item | Gets or sets the element at the specified key in the SortedList. |
| Keys | Get list of keys of SortedList. |
| Values | Get list of values in SortedList. |

| Method | Description |
| :--- | :--- |
| Add\(object key, object value\) | Add key-value pairs into SortedList. |
| Remove\(object key\) | Removes element with the specified key. |
| RemoveAt\(int index\) | Removes element at the specified index. |
| Contains\(object key\) | Checks whether specified key exists in SortedList. |
| Clear\(\) | Removes all the elements from SortedList. |
| GetByIndex\(int index\) | Returns the value by index stored in internal array |
| GetKey\(int index\) | Returns the key stored at specified index in internal array |
| IndexOfKey\(object key\) | Returns an index of specified key stored in internal array |
| IndexOfValue\(object value\) | Returns an index of specified value stored in internal array |

## SortedList&lt;TKey, TValue&gt;

 The generic SortedList `SortedList<TKey, TValue>` represents a collection of key-value pairs that are sorted by key based on associated IComparer&lt;T&gt;. 

```csharp
SortedList<int, string> mySortedList = new SortedList<int,string>();
```

### Important Properties and Methods of Generic SortedList

| Property | Description |
| :--- | :--- |
| Capacity | Gets or sets the number of elements that the SortedList&lt;TKey,TValue&gt; can store. |
| Count | Gets the total number of elements exists in the SortedList&lt;TKey,TValue&gt;. |
| IsReadOnly | Returns a boolean indicating whether the SortedList&lt;TKey,TValue&gt; is read-only. |
| Item | Gets or sets the element with the specified key in the SortedList&lt;TKey,TValue&gt;. |
| Keys | Get list of keys of SortedList&lt;TKey,TValue&gt;. |
| Values | Get list of values in SortedList&lt;TKey,TValue&gt;. |

| Method | Description |
| :--- | :--- |
| Add | Add key-value pairs into SortedList&lt;TKey, TValue&gt;. |
| Remove | Removes element with the specified key. |
| RemoveAt | Removes element at the specified index. |
| ContainsKey | Checks whether the specified key exists in SortedList&lt;TKey, TValue&gt;. |
| ContainsValue | Checks whether the specified key exists in SortedList&lt;TKey, TValue&gt;. |
| Clear | Removes all the elements from SortedList&lt;TKey, TValue&gt;. |
| IndexOfKey | Returns an index of specified key stored in internal array of SortedList&lt;TKey, TValue&gt;. |
| IndexOfValue | Returns an index of specified value stored in internal array of SortedList&lt;TKey, TValue&gt; |
| TryGetValue | Returns true and assigns the value with specified key, if key does not exists then return false. |

