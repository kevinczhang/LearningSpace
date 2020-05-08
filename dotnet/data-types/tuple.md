---
description: >-
  A tuple is a data structure that contains a sequence of elements of different
  data types.
---

# Tuple

## Tuple creation and access

```csharp
Tuple<int, string, string> person = 
                        new Tuple <int, string, string>(1, "Steve", "Jobs");

var person = Tuple.Create(1, "Steve", "Jobs");
person.Item1; // returns 1
person.Item2; // returns "Steve"
person.Item3; // returns "Jobs"
```

## Nested Tuples

```csharp
var numbers = Tuple.Create(1, 2, 3, 4, 5, 6, 7, 
                                Tuple.Create(8, 9, 10, 11, 12, 13));
numbers.Item1; // returns 1
numbers.Item7; // returns 7
numbers.Rest.Item1; //returns (8, 9, 10, 11, 12, 13)
numbers.Rest.Item1.Item1; //returns 8
numbers.Rest.Item1.Item2; //returns 9
```

