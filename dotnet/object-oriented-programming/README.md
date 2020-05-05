# Object-Oriented programming

## OOP principles

* _Encapsulation_ means that a group of related properties, methods, and other members are treated as a single unit or object.
* _Inheritance_ describes the ability to create new classes based on an existing class.
* _Polymorphism_ means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.

## Classes vs Structs <a id="classes-and-structs-c-programming-guide"></a>

A class or struct declaration is like a blueprint that is used to create instances or objects at run time.

A class is a reference type. When an object of the class is created, the variable to which the object is assigned holds only a reference to that memory. When the object reference is assigned to a new variable, the new variable refers to the original object. Changes made through one variable are reflected in the other variable because they both refer to the same data.

A struct is a value type. When a struct is created, the variable to which the struct is assigned holds the struct's actual data. When the struct is assigned to a new variable, it is copied. The new variable and the original variable therefore contain two separate copies of the same data. Changes made to one copy do not affect the other copy.

✔️ CONSIDER defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.

❌ AVOID defining a struct unless the type has all of the following characteristics:

* It logically represents a single value, similar to primitive types \(`int`, `double`, etc.\).
* It has an instance size under 16 bytes.
* It is immutable.
* It will not have to be boxed frequently.

In all other cases, you should define your types as classes.



