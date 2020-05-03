---
description: >-
  Covariance and contravariance allow us to be flexible when dealing with class
  hierarchy.
---

# Covariance and Contravariance

In C\#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments. Covariance preserves assignment compatibility and contravariance reverses it. 

## Covariance

Covariance enables you to pass a derived type where a base type is expected. Co-variance is like variance of the same kind. The base class and other derived classes are considered to be the same kind of class that adds extra functionalities to the base type.

Covariance can be applied on delegate, generic, array, interface, etc.

## Contravariance

 Contravariane is applied to **parameters**. Cotravariance allows a method with the parameter of a base class to be assigned to a delegate that expects the parameter of a derived class.

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

## Variance in Generic Interfaces <a id="variance-in-generic-interfaces-c"></a>

 Variance in generic interfaces is supported for reference types only. Value types do not support variance. For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.

Starting with .NET Framework 4, the following interfaces are variant:

* [IEnumerable&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerable-1) \(T is covariant\)
* [IEnumerator&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerator-1) \(T is covariant\)
* [IQueryable&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.linq.iqueryable-1) \(T is covariant\)
* [IGrouping&lt;TKey,TElement&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.linq.igrouping-2) \(`TKey` and `TElement` are covariant\)
* [IComparer&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.icomparer-1) \(T is contravariant\)
* [IEqualityComparer&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.iequalitycomparer-1) \(T is contravariant\)
* [IComparable&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.icomparable-1) \(T is contravariant\)

Starting with .NET Framework 4.5, the following interfaces are variant:

* [IReadOnlyList&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ireadonlylist-1) \(T is covariant\)
* [IReadOnlyCollection&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ireadonlycollection-1) \(T is covariant\)

**Covariance** permits a method to have a more derived return type than that defined by the generic type parameter of the interface.  

To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`. The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface. However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other. This is shown in the following code example.

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

**Contravariance** permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.

 To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class. The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface. Because the [IEqualityComparer&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.iequalitycomparer-1) interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class. 

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

 _Covariance_ allows interface methods to have more derived return types than that defined by the generic type parameters. _Contravariance_ allows interface methods to have argument types that are less derived than that specified by the generic parameters. A generic interface that has covariant or contravariant generic type parameters is called _variant_.

