# Hashtable and Dictionary

## Dictionary&lt;TKey, TValue&gt;

 The `Dictionary<TKey, TValue>` class is a generic collection class in the System.Collection.Generics namespace. TKey denotes the type of key and TValue is the type of TValue.

 A Dictionary object can be assigned to a variable of `IDictionary<Tkey, TValue>` or `Dictionary<TKey, Tvalue>` class.

```csharp
IDictionary<int, string> dict = new Dictionary<int, string>();
        
//or

Dictionary<int, string> dict = new Dictionary<int, string>();
```

Dictionary cannot include duplicate or null keys, where as values can be duplicated or set as null. Keys must be unique otherwise it will throw a runtime exception.

### Important Properties and Methods of IDictionary

| Property | Description |
| :--- | :--- |
| Count | Gets the total number of elements exists in the Dictionary&lt;TKey,TValue&gt;. |
| IsReadOnly | Returns a boolean indicating whether the Dictionary&lt;TKey,TValue&gt; is read-only. |
| Item | Gets or sets the element with the specified key in the Dictionary&lt;TKey,TValue&gt;. |
| Keys | Returns collection of keys of Dictionary&lt;TKey,TValue&gt;. |
| Values | Returns collection of values in Dictionary&lt;TKey,TValue&gt;. |

| Method | Description |
| :--- | :--- |
| Add | Adds an item to the Dictionary collection. |
| Add | Add key-value pairs in Dictionary&lt;TKey, TValue&gt; collection. |
| Remove | Removes the first occurrence of specified item from the Dictionary&lt;TKey, TValue&gt;. |
| Remove | Removes the element with the specified key. |
| ContainsKey | Checks whether the specified key exists in Dictionary&lt;TKey, TValue&gt;. |
| ContainsValue | Checks whether the specified key exists in Dictionary&lt;TKey, TValue&gt;. |
| Clear | Removes all the elements from Dictionary&lt;TKey, TValue&gt;. |
| TryGetValue | Returns true and assigns the value with specified key, if key does not exists then return false. |

## Hashtable

 Hashtable collection in System.Collections namespace, which is similar to generic [Dictionary](https://www.tutorialsteacher.com/csharp/csharp-dictionary) collection. The Hashtable collection stores key-value pairs. It optimizes lookups by computing the hash code of each key and stores it in a different bucket internally and then matches the hash code of the specified key at the time of accessing values.

### Important Propertis and Methods of Hashtable

| Property | Description |
| :--- | :--- |
| Count | Gets the total count of key/value pairs in the Hashtable. |
| IsReadOnly | Gets boolean value indicating whether the Hashtable is read-only. |
| Item | Gets or sets the value associated with the specified key. |
| Keys | Gets an ICollection of keys in the Hashtable. |
| Values | Gets an ICollection of values in the Hashtable. |

| Methods | Usage |
| :--- | :--- |
| [Add](https://www.tutorialsteacher.com/csharp/csharp-hashtable#add) | Adds an item with a key and value into the hashtable. |
| [Remove](https://www.tutorialsteacher.com/csharp/csharp-hashtable#remove) | Removes the item with the specified key from the hashtable. |
| Clear | Removes all the items from the hashtable. |
| [Contains](https://www.tutorialsteacher.com/csharp/csharp-hashtable#contains) | Checks whether the hashtable contains a specific key. |
| [ContainsKey](https://www.tutorialsteacher.com/csharp/csharp-hashtable#contains) | Checks whether the hashtable contains a specific key. |
| [ContainsValue](https://www.tutorialsteacher.com/csharp/csharp-hashtable#contains) | Checks whether the hashtable contains a specific value. |
| GetHash | Returns the hash code for the specified key. |

```csharp
Hashtable ht = new Hashtable()
                {
                    { 1, "One" },
                    { 2, "Two" },
                    { 3, "Three" },
                    { 4, "Four" },
                    { 5, null },
                    { "Fv", "Five" },
                    { 8.5F, 8.5 }
                };

foreach (DictionaryEntry item in ht)
                Console.WriteLine("key:{0}, value:{1}",item.Key, item.Value);
```

