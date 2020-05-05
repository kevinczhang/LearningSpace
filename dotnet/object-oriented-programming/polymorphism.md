---
description: >-
  Polymorphism is a Greek word that means "many-shaped" and it has two distinct
  aspects
---

# Polymorphism

## Virtual members

When a derived class inherits from a base class, it gains all the methods, fields, properties, and events of the base class. The designer of the derived class can different choices for the behavior of virtual methods:

* The derived class may override virtual members in the base class, defining new behavior.
* The derived class inherit the closest base class method without overriding it, preserving the existing behavior but enabling further derived classes to override the method.
* The derived class may define new non-virtual implementation of those members that hide the base class implementations.

 A derived class can override a base class member only if the base class member is declared as [virtual](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/virtual) or [abstract](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/abstract).

```csharp
public class BaseClass
{
    public virtual void DoWork() { }
    public virtual int WorkProperty
    {
        get { return 0; }
    }
}
public class DerivedClass : BaseClass
{
    public override void DoWork() { }
    public override int WorkProperty
    {
        get { return 0; }
    }
}
```

Fields cannot be virtual; only methods, properties, events, and indexers can be virtual.

#### Hide base class members with new members <a id="hide-base-class-members-with-new-members"></a>

 If you want your derived class to have a member with the same name as a member in a base class, you can use the [new](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/new-modifier) keyword to hide the base class member. 

```csharp
public class BaseClass
{
    public void DoWork() { WorkField++; }
    public int WorkField;
    public int WorkProperty
    {
        get { return 0; }
    }
}

public class DerivedClass : BaseClass
{
    public new void DoWork() { WorkField++; }
    public new int WorkField;
    public new int WorkProperty
    {
        get { return 0; }
    }
}
```

