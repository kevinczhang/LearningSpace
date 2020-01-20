---
description: >-
  For different data types, a certain amount of memory space is reserved on our
  computer.
---

# Data Types

Data types that represent the whole numbers are expressed with a certain number of bits. 

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

![integral types](../.gitbook/assets/image%20%2815%29.png)

 Letter `u` in front of the type means that type can’t contain negative numbers, it is unsigned.

## Number Types with floating point

![Number types](../.gitbook/assets/image%20%287%29.png)



## char Type

* 16 bits

Examples:

```csharp
char a = 'a';
```

## String Type  

* reference type

Verbatim Literal is a string with an @ symbol prefix, as in @“Hello". Verbatim literals make escape sequences translate as normal printable characters to enhance readability.

Practical Example: Without Verbatim Literal : “C:\Pragim\DotNet\Training\Csharp” – Less Readable With Verbatim Literal : @“C:\Pragim\DotNet\Training\Csharp” – Better Readable

## Nullable

### By default value types are non nullable. To make them nullable use ? 

int i = 0 \(i is non nullable, so "i" cannot be set to null, i = null will generate compiler error\) int? j = 0 \(j is nullable int, so j=null is legal\)

### int AvailableTickets; int? TicketsOnSale = null;

//Using null coalesce operator ?? AvailableTickets = TicketsOnSale ?? 0;

## Operators

![](../.gitbook/assets/image%20%284%29.png)
