---
description: >-
  For different data types, a certain amount of memory space is reserved on our
  computer.
---

# Data Types

Data types that represent the whole numbers are expressed with a certain number of bits. 

C\# 3.0 introduced the implicit typed local variable "var". Var can only be defined in a method as a local variable. The compiler will infer its type based on the value to the right of the "=" operator.

C\# mainly categorized data types in two types: **Value types** and **Reference types**. Value types include simple types \(e.g. int, float, bool, and char\), enum types, struct types, and Nullable value types. Reference types include class types, interface types, delegate types, and array types.

![](../../.gitbook/assets/image%20%2818%29.png)

## Predefined Data Types

| Type | Description | Range | Suffix |
| :--- | :--- | :--- | :--- |
| byte | 8-bit unsigned integer | 0 to 255 |  |
| sbyte | 8-bit signed integer | -128 to 127 |  |
| short | 16-bit signed integer | -32,768 to 32,767 |  |
| ushort | 16-bit unsigned integer | 0 to 65,535 |  |
| int | 32-bit signed integer | -2,147,483,648 to 2,147,483,647 |  |
| uint | 32-bit unsigned integer | 0 to 4,294,967,295 | u |
| long | 64-bit signed integer | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | l |
| ulong | 64-bit unsigned integer | 0 to 18,446,744,073,709,551,615 | ul |
| float | 32-bit Single-precision floating point type | -3.402823e38 to 3.402823e38 | f |
| double | 64-bit double-precision floating point type | -1.79769313486232e308 to 1.79769313486232e308 | d |
| decimal | 128-bit decimal type for financial and monetary calculations | \(+ or -\)1.0 x 10e-28 to 7.9 x 10e28 | m |
| char | 16-bit single Unicode character | Any valid character, e.g. a,\*, \x0058 \(hex\), or\u0058 \(Unicode\) |  |
| bool | 8-bit logical true/false value | True or False |  |
| object | Base type of all other types. |  |  |
| string | A sequence of Unicode characters |  |  |
| DateTime | Represents date and time | 0:00:00am 1/1/01 to 11:59:59pm 12/31/9999 |  |

### Alias vs .Net Type

The above table of predefined data types are actually alias to their .NET type \(CLR class\) name. The following table lists alias for predefined data types and related .NET class name.

## Boolean type 

* value type
* true or false \(default: false\)
* 8 bits

Examples:

```csharp
bool a = true;
```

## Integral Types

sbyte \(8\), byte \(8\), short \(16\), ushort \(16\), int \(32\), uint \(32\), long \(64\), ulong \(64\)

For unsigned numbers, the range is from 0 to 2N-1, and signed numbers range is from -2N-1 to 2N-1-1.

![integral types](../../.gitbook/assets/image%20%2819%29.png)

 Letter `u` in front of the type means that type can’t contain negative numbers, it is unsigned.

## Number Types with floating point

![Number types](../../.gitbook/assets/image%20%287%29.png)



## char Type

* 16 bits

Examples:

```csharp
char a = 'a';
```

## Nullable

### By default value types are non nullable. To make them nullable use ? 

int i = 0 \(i is non nullable, so "i" cannot be set to null, i = null will generate compiler error\) int? j = 0 \(j is nullable int, so j=null is legal\)

### int AvailableTickets; int? TicketsOnSale = null;

//Using null coalesce operator ?? AvailableTickets = TicketsOnSale ?? 0;

## Operators

![](../../.gitbook/assets/image%20%284%29.png)

 Assignment Operator **=**  
Arithmetic Operators like **+,-,\*,/,%**   
Comparison Operators like **==, !=,&gt;, &gt;=, &lt;, &lt;=**   
Conditional Operators like **&&, \|\|**  
Ternary Operator **?:**  
Null Coalescing Operator **??** 

