---
description: >-
  An Indexer is a special type of property that allows a class or structure to
  be accessed like an array for its private collection.
---

# Indexers

 An indexer can be defined the same way as property with **this** keyword and square brackets \[\].

```csharp
class DataStore<T>
{
    private T[] store; 

    public DataStore()
    {
        store = new T[10];
    }

    public DataStore(int length)
    {
        store = new T[length];
    }

    public T this[int index]
    {
        get
        {
            if (index < 0 &&  index >= store.Length)
                throw new IndexOutOfRangeException("Index out of range");

                return store[index];
        }

        set
        {
            if (index < 0 ||  index >= store.Length)
                throw new IndexOutOfRangeException("Index out of range");

            store[index] = value;
        }
    }

    public int Length
    {
        get
        {
            return store.Length;
        }
    }
}
```

```csharp
DataStore<int> grades = new DataStore<int>();
grades[0] = 100;
grades[1] = 25;
grades[2] = 34;
grades[3] = 42;
grades[4] = 12;
grades[5] = 18;
grades[6] = 2;
grades[7] = 95;
grades[8] = 75;
grades[9] = 53;

for (int i = 0; i < grades.Length;i++)
    Console.WriteLine(grades[i]);

DataStore<string> names = new DataStore<string>(5);
names[0] = "Steve";
names[1] = "Bill";
names[2] = "James";
names[3] = "Ram";
names[4] = "Andy";

for (int i = 0; i < names.Length;i++)
    Console.WriteLine(names[i]);
```

