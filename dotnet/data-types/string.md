# String

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

## StringBuilder

StringBuilder is a dynamic object that allows you to expand the number of characters in the string. It doesn't create a new object in the memory but dynamically expands memory to accommodate the modified string.

### Important Methods of StringBuilder

| Method Name | Description |
| :--- | :--- |
| [StringBuilder.Append\(valueToAppend\)](https://www.tutorialsteacher.com/csharp/csharp-stringbuilder#append) | Appends the passed values to the end of the current StringBuilder object. |
| [StringBuilder.AppendFormat\(\)](https://www.tutorialsteacher.com/csharp/csharp-stringbuilder#appendformat) | Replaces a format specifier passed in a string with formatted text. |
| [StringBuilder.Insert\(index, valueToAppend\)](https://www.tutorialsteacher.com/csharp/csharp-stringbuilder#insert) | Inserts a string at the specified index of the current StringBuilder object. |
| [StringBuilder.Remove\(int startIndex, int length\)](https://www.tutorialsteacher.com/csharp/csharp-stringbuilder#remove) | Removes the specified number of characters from the given starting position of the current StringBuilder object. |
| [StringBuilder.Replace\(oldValue, newValue\)](https://www.tutorialsteacher.com/csharp/csharp-stringbuilder#replace) | Replaces characters with new characters. |

