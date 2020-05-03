---
description: A method is a code block that contains a series of statements.
---

# Methods

### Passing by reference vs. passing by value <a id="passing-by-reference-vs-passing-by-value"></a>

 By default, when an instance of a [value type](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types) is passed to a method, its copy is passed instead of the instance itself. Therefore, changes to the argument have no effect on the original instance in the calling method. To pass a value-type instance by reference, use the `ref` keyword. 

