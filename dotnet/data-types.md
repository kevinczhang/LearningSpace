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

![integral types](../.gitbook/assets/image%20%2818%29.png)

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

A string is an object of type [String](https://docs.microsoft.com/en-us/dotnet/api/system.string) whose value is text. Internally, the text is stored as a sequential read-only collection of [Char](https://docs.microsoft.com/en-us/dotnet/api/system.char) objects.  In C\#, the `string` keyword is an alias for [String](https://docs.microsoft.com/en-us/dotnet/api/system.string). Therefore, `String` and `string` are equivalent.

```csharp
// Declare without initializing.
string message1;

// Initialize to null.
string message2 = null;

// Initialize as an empty string.
// Use the Empty constant instead of the literal "".
string message3 = System.String.Empty;

// Initialize with a regular string literal.
string oldPath = "c:\\Program Files\\Microsoft Visual Studio 8.0";

// Initialize with a verbatim string literal.
string newPath = @"c:\Program Files\Microsoft Visual Studio 9.0";

// Use System.String if you prefer.
System.String greeting = "Hello World!";

// In local variables (i.e. within a method body)
// you can use implicit typing.
var temp = "I'm still a strongly-typed System.String!";

// Use a const string to prevent 'message4' from
// being used to store another string value.
const string message4 = "You can't get rid of me!";

// Use the String constructor only when creating
// a string from a char*, char[], or sbyte*. See
// System.String documentation for details.
char[] letters = { 'A', 'B', 'C' };
string alphabet = new string(letters);

// String methods
string s3 = "Visual C# Express";
System.Console.WriteLine(s3.Substring(7, 2));
// Output: "C#"

System.Console.WriteLine(s3.Replace("C#", "Basic"));
// Output: "Visual Basic Express"

// Index values are zero-based
int index = s3.IndexOf("C");
// index = 7
```

 String objects are _immutable_: they cannot be changed after they have been created. 

### Null Strings and Empty Strings <a id="null-strings-and-empty-strings"></a>

 An empty string is an instance of a [System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string) object that contains zero characters. You can call methods on empty strings because they are valid [System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string) objects.

### Number parsing

```csharp
string numString = "1287543"; //"1287543.0" will return false for a long
long number1 = 0;
bool canConvert = long.TryParse(numString, out number1);
if (canConvert == true)
  Console.WriteLine("number1 now = {0}", number1);
else
  Console.WriteLine("numString is not a valid long");

byte number2 = 0;
numString = "255"; // A value of 256 will return false
canConvert = byte.TryParse(numString, out number2);
if (canConvert == true)
  Console.WriteLine("number2 now = {0}", number2);
else
  Console.WriteLine("numString is not a valid byte");

decimal number3 = 0;
numString = "27.3"; //"27" is also a valid decimal
canConvert = decimal.TryParse(numString, out number3);
if (canConvert == true)
  Console.WriteLine("number3 now = {0}", number3);
else
  Console.WriteLine("number3 is not a valid decimal");
```

## Nullable

### By default value types are non nullable. To make them nullable use ? 

int i = 0 \(i is non nullable, so "i" cannot be set to null, i = null will generate compiler error\) int? j = 0 \(j is nullable int, so j=null is legal\)

### int AvailableTickets; int? TicketsOnSale = null;

//Using null coalesce operator ?? AvailableTickets = TicketsOnSale ?? 0;

## Operators

![](../.gitbook/assets/image%20%284%29.png)

 Assignment Operator **=**  
Arithmetic Operators like **+,-,\*,/,%**   
Comparison Operators like **==, !=,&gt;, &gt;=, &lt;, &lt;=**   
Conditional Operators like **&&, \|\|**  
Ternary Operator **?:**  
Null Coalescing Operator **??** 

