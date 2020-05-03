---
description: 'This section explains programming concepts in the C# language.'
---

# Programming Concepts

## Covariance and Contravariance <a id="covariance-and-contravariance-c"></a>

In C\#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments. Covariance preserves assignment compatibility and contravariance reverses it. Covariance and contravariance allow us to be flexible when dealing with class hierarchy.

```csharp
// Assignment compatibility.
string str = "test";  
// An object of a more derived type assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
/* An object that is instantiated with a more derived type argument
 is assigned to an object instantiated with a less derived type argument.
 Assignment compatibility is preserved.*/
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;
```



