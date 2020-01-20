# Enum

An enum is a value type with a set of related named constants often referred to as an enumerator list. The enum keyword is used to declare an enumeration. It is a primitive data type, which is user defined.

An enum type can be an integer \(float, int, byte, double etc.\). But if you used beside int it has to be cast.

An enum is used to create numeric constants in .NET framework. All the members of enum are of enum type. Their must be a numeric value for each enum type.

The default underlying type of the enumeration element is int. By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.

```csharp
public enum DaysInWeek
{
    Monday=10,
    Tuesday=20,
    Wednesday=35,
    Thursday=48,
    Friday=74,
    Saturday=12,
    Sunday=154
}
```

* Enums are enumerated data type in c\#. 
* Enums are not for end-user, they are meant for developers.
* Enums are strongly typed constant. They are strongly typed, i.e. an enum of one type may not be implicitly assigned to an enum of another type even though the underlying value of their members are the same. 
* Enumerations \(enums\) make your code much more readable and understandable. 
* Enum values are fixed. Enum can be displayed as a string and processed as an integer. 
* The default type is int, and the approved types are byte, sbyte, short, ushort, uint, long, and ulong. 
* Every enum type automatically derives from System.Enum and thus we can use System.
* Enum methods on enums. Enums are value types and are created on the stack and not on the heap.

